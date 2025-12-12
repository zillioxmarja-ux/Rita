import random

def get_random_hex_color():
    """Генерирует случайный шестнадцатеричный код цвета, например, '#A3C1F4'."""
    # Генерируем случайное целое число от 0 до 16777215 (FFFFF F - белый)
    random_int = random.randint(0, 16777215)
    # Преобразуем его в HEX-строку и удаляем префикс '0x', заполняем нулями до 6 символов
    hex_color = hex(random_int)[2:].zfill(6).upper()
    return f"#{hex_color}"

def hex_to_rgb(hex_code):
    """Преобразует HEX-код цвета ('#RRGGBB') в кортеж RGB (r, g, b)."""
    # Убираем '#'
    hex_code = hex_code.lstrip('#')
    # Преобразуем каждую пару символов в целое число (0-255)
    r = int(hex_code[0:2], 16)
    g = int(hex_code[2:4], 16)
    b = int(hex_code[4:6], 16)
    return (r, g, b)

def calculate_average_color(palette):
    """Вычисляет усредненный цвет из палитры."""
    total_r, total_g, total_b = 0, 0, 0
    num_colors = len(palette)
    
    if num_colors == 0:
        return "#000000", (0, 0, 0)

    # Суммируем все значения RGB
    for hex_code in palette:
        r, g, b = hex_to_rgb(hex_code)
        total_r += r
        total_g += g
        total_b += b
        
    # Находим среднее
    avg_r = total_r // num_colors
    avg_g = total_g // num_colors
    avg_b = total_b // num_colors
    
    # Преобразуем обратно в HEX
    avg_hex = f"#{avg_r:02X}{avg_g:02X}{avg_b:02X}"
    
    return avg_hex, (avg_r, avg_g, avg_b)

# --- Основная часть программы ---

PALETTE_SIZE = 5
color_palette = []

# Генерируем палитру
for _ in range(PALETTE_SIZE):
    color_palette.append(get_random_hex_color())

# Вычисляем средний цвет
avg_hex, avg_rgb = calculate_average_color(color_palette)

# --- Вывод результатов ---

print("--- 🎨 СЛУЧАЙНЫЙ ГЕНЕРАТОР ЦВЕТОВЫХ ПАЛИТР ---")
print(f"Сгенерировано {PALETTE_SIZE} цветов:")
print("-" * 40)

for i, hex_code in enumerate(color_palette):
    rgb = hex_to_rgb(hex_code)
    # Используем формат вывода с двумя системами: HEX и RGB
    print(f"Цвет {i+1}: {hex_code} (RGB: {rgb})")
    
print("-" * 40)
print("📊 АНАЛИЗ ПАЛИТРЫ:")
print(f"Усредненный цвет палитры (HEX): {avg_hex}")
print(f"
