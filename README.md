import random
import colorsys # Встроенный модуль для преобразования цветовых пространств (RGB, HSL, HSV)

def hex_to_rgb(hex_code):
    """Преобразует HEX-код ('#RRGGBB') в кортеж RGB (0-255)."""
    hex_code = hex_code.lstrip('#')
    return tuple(int(hex_code[i:i+2], 16) for i in (0, 2, 4))

def rgb_to_hex(rgb):
    """Преобразует кортеж RGB (0-255) в HEX-код ('#RRGGBB')."""
    return f'#{rgb[0]:02X}{rgb[1]:02X}{rgb[2]:02X}'

def rgb_to_hsl(rgb):
    """Преобразует RGB (0-255) в HSL (0-1.0)."""
    # Нормализуем RGB к диапазону 0.0 - 1.0
    r, g, b = [x / 255.0 for x in rgb]
    # Используем colorsys для преобразования
    h, l, s = colorsys.rgb_to_hls(r, g, b)
    # Возвращаем HSL в диапазоне: H (0-360), S (0-100), L (0-100)
    return (round(h * 360), round(s * 100), round(l * 100))

def generate_shades_and_tints(base_hex, num_steps=5, lightness_range=40):
    """
    Генерирует тональную палитру вокруг базового цвета.
    
    Сначала преобразует HEX в HSL, затем изменяет яркость (Lightness).
    """
    base_rgb = hex_to_rgb(base_hex)
    base_h, base_s, base_l = rgb_to_hsl(base_rgb)
    
    palette = []
    
    # Определяем диапазон яркости для палитры
    start_l = max(10, base_l - lightness_range // 2)
    end_l = min(90, base_l + lightness_range // 2)
    
    # Создаем равномерно распределенные уровни яркости
    lightness_values = [start_l + i * (end_l - start_l) / (num_steps - 1) for i in range(num_steps)]
    
    for l in lightness_values:
        # H и S остаются неизменными, меняется только L (яркость)
        # HSL должен быть в диапазоне 0.0 - 1.0 для colorsys
        h_norm = base_h / 360.0
        s_norm = base_s / 100.0
        l_norm = l / 100.0
        
        # Обратное преобразование HSL в RGB
        r_norm, g_norm, b_norm = colorsys.hls_to_rgb(h_norm, l_norm, s_norm)
        
        # RGB в диапазоне 0-255
        new_rgb = (int(r_norm * 255), int(g_norm * 255), int(b_norm * 255))
        new_hex = rgb_to_hex(new_rgb)
        
        palette.append({
            "HEX": new_hex,
            "RGB": new_rgb,
            "HSL": rgb_to_hsl(new_rgb),
            "L_value": round(l)
        })
        
    return palette

# --- Основная часть программы ---

# Генерируем случайный базовый HEX-цвет
def get_random_hex_color():
    return f"#{random.randint(0, 0xFFFFFF):06X}"

BASE_COLOR = get_random_hex_color()
PALETTE_STEPS = 5
LIGHTNESS_RANGE = 60 # Насколько сильно будет меняться яркость

final_palette = generate_shades_and_tints(BASE_COLOR, PALETTE_STEPS, LIGHTNESS_RANGE)

# --- Вывод результатов ---

print("--- 💎 ГЕНЕРАТОР ГАРМОНИЧНОЙ ТОНАЛЬНОЙ ПАЛИТРЫ ---")
print(f"Базовый цвет (HEX): {BASE_COLOR}")
print(f"Палитра: {PALETTE_STEPS} шагов яркости (L) в диапазоне {LIGHTNESS_RANGE}%")
print("-" * 75)

print(f"| {'#':<2} | {'Яркость':<7} | {'HEX':<7} | {'RGB':<15} | {'HSL (H, S, L)':<15} |")
print("-" * 75)

for i, color in enumerate(final_palette):
    print(f"| {i+1:<2} | {color['L_value']:<7} | {color['HEX']:<7} | {color['RGB']!s:<15} | {color['HSL']!s:<15} |")

print("-" * 75)
