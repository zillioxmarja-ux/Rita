# --- 1. Подготовка локальной среды ---

PROJECT_NAME="ultra-enhanced-repo-2025" 

# Создание и переход в новую директорию
mkdir $PROJECT_NAME
cd $PROJECT_NAME

# Инициализация Git
git init

# --- 2. Улучшенные метаданные и документация ---

# 2.1. README.md (с секцией для установки)
echo "# $PROJECT_NAME" > README.md
echo "\n[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)" >> README.md
echo "\n## 🚀 Установка\n\n1. Склонируйте репозиторий:\n\`\`\`bash\ngit clone <URL_РЕПОЗИТОРИЯ>\n\`\`\`\n2. Установите зависимости (если применимо):\n\`\`\`bash\npip install -r requirements.txt\n\`\`\`" >> README.md

# 2.2. .gitignore
echo "# Игнорируем файлы Python" > .gitignore
echo "__pycache__/" >> .gitignore
echo "*.pyc" >> .gitignore
echo "*.log" >> .gitignore
echo ".DS_Store" >> .gitignore
echo "# Игнорируем файлы IDE и среды" >> .gitignore
echo ".vscode/" >> .gitignore
echo "venv/" >> .gitignore
echo ".env" >> .gitignore

# 2.3. LICENSE (только заголовок, полный текст лицензии обычно копируется)
echo "MIT License" > LICENSE
echo "" >> LICENSE
echo "Copyright (c) 2025 <ВАШЕ_ИМЯ_ПОЛЬЗОВАТЕЛЯ>" >> LICENSE

# 2.4. CONTRIBUTING.md (Руководство для контрибьюторов)
echo "# Руководство по внесению вклада (Contributing)" > CONTRIBUTING.md
echo "\nМы приветствуем вклад в этот проект! Пожалуйста, следуйте этим рекомендациям:" >> CONTRIBUTING.md
echo "\n## 📜 Правила\n\n* Используйте ветку \`main\` для отправки pull requests (PRs)." >> CONTRIBUTING.md
echo "* Подробно описывайте свои изменения и тестируйте код перед отправкой." >> CONTRIBUTING.md

# 2.5. requirements.txt (Пример файла для зависимостей Python)
echo "# Зависимости проекта" > requirements.txt
echo "requests>=2.28.1" >> requirements.txt
echo "numpy>=1.23.5" >> requirements.txt

# --- 3. Коммит и отправка на GitHub ---

# Добавление всех файлов
git add .

# Создание первого коммита (используем стандарты Conventional Commits)
git commit -m "chore: Initial project setup with full documentation"

# Установка главной ветки
git branch -M main

# Привязка к удаленному репозиторию на GitHub
# !!! ОБЯЗАТЕЛЬНО ЗАМЕНИТЕ ЭТУ СТРОКУ !!!
# Замените <ВАШЕ_ИМЯ_ПОЛЬЗОВАТЕЛЯ>
REPO_URL="https://github.com/<ВАШЕ_ИМЯ_ПОЛЬЗОВАТЕЛЯ>/$PROJECT_NAME.git"
git remote add origin $REPO_URL

# Отправка кода на GitHub
git push -u origin main
