# --- 1. Подготовка локальной среды (используем то же имя проекта) ---

PROJECT_NAME="hyper-enhanced-repo-2025" 

mkdir $PROJECT_NAME
cd $PROJECT_NAME
git init

# --- 2. Добавление файлов высокого уровня стандартизации ---

# 2.1. Создание каталога для GitHub Actions
mkdir -p .github/workflows

# 2.2. Конфигурация GitHub Actions для CI (Continuous Integration)
# Этот файл будет запускать тесты при каждом пуше
echo "name: Python CI Pipeline" > .github/workflows/python_ci.yml
echo "on:" >> .github/workflows/python_ci.yml
echo "  push:" >> .github/workflows/python_ci.yml
echo "    branches: [ main ]" >> .github/workflows/python_ci.yml
echo "  pull_request:" >> .github/workflows/python_ci.yml
echo "    branches: [ main ]" >> .github/workflows/python_ci.yml
echo "jobs:" >> .github/workflows/python_ci.yml
echo "  build:" >> .github/workflows/python_ci.yml
echo "    runs-on: ubuntu-latest" >> .github/workflows/python_ci.yml
echo "    steps:" >> .github/workflows/python_ci.yml
echo "    - uses: actions/checkout@v4" >> .github/workflows/python_ci.yml
echo "    - name: Set up Python" >> .github/workflows/python_ci.yml
echo "      uses: actions/setup-python@v5" >> .github/workflows/python_ci.yml
echo "      with:" >> .github/workflows/python_ci.yml
echo "        python-version: '3.11'" >> .github/workflows/python_ci.yml
echo "    - name: Install dependencies" >> .github/workflows/python_ci.yml
echo "      run: pip install -r requirements.txt" >> .github/workflows/python_ci.yml
echo "    - name: Run linter (Flake8 Check)" >> .github/workflows/python_ci.yml
echo "      run: pip install flake8 && flake8 ." >> .github/workflows/python_ci.yml
echo "    - name: Run tests" >> .github/workflows/python_ci.yml
echo "      run: echo 'Place your test command here, e.g., pytest'" >> .github/workflows/python_ci.yml

# 2.3. CODE_OF_CONDUCT.md (Кодекс поведения для сообщества)
echo "# Кодекс поведения (Code of Conduct)" > CODE_OF_CONDUCT.md
echo "\nМы стремимся сделать участие в этом проекте приятным для всех, независимо от уровня опыта, пола или происхождения." >> CODE_OF_CONDUCT.md
echo "## 🤝 Наши стандарты" >> CODE_OF_CONDUCT.md
echo "* У
