# 🚀 SOLID Principles - Platzi Course

![Python](https://img.shields.io/badge/Python-3.12-blue?style=for-the-badge&logo=python&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Learning-orange?style=for-the-badge)

## 📋 Descripción del Proyecto

Este proyecto es una demostración práctica de cómo aplicar los **principios SOLID** en Python. Contiene un sistema de procesamiento de pagos que inicialmente viola estos principios y sirve como base para ejercicios de refactorización.

## 🎯 Objetivos de Aprendizaje

- ✅ Comprender los 5 principios SOLID
- 🔧 Identificar violaciones en código existente
- 🏗️ Refactorizar código aplicando buenas prácticas
- 📝 Implementar type hints modernos de Python 3.12
- 🧪 Escribir código testeable y mantenible

## 🛠️ Tecnologías Utilizadas

| Tecnología | Propósito |
|------------|-----------|
| 🐍 **Python 3.12** | Lenguaje principal |
| 💳 **Stripe** | Procesamiento de pagos |
| 📧 **SMTP** | Envío de emails |
| 📱 **SMS Gateway** | Notificaciones SMS |
| 🔧 **MyPy** | Verificación de tipos |
| ⚡ **Ruff** | Linting rápido |
| 🧪 **Pytest** | Testing framework |

## 🚀 Configuración del Entorno

### 1️⃣ Clonar el Repositorio
```bash
git clone https://github.com/daecazu/solid_platzi.git
cd solid_platzi
```

### 2️⃣ Crear Entorno Virtual
```bash
python3 -m venv venv
source venv/bin/activate  # En Windows: venv\Scripts\activate
```

### 3️⃣ Instalar Dependencias
```bash
pip install -r requirements.txt
```

### 4️⃣ Configurar Variables de Entorno
```bash
cp .env.example .env
# Editar .env con tus credenciales
```

## 🏃‍♂️ Ejecutar el Proyecto

```bash
source venv/bin/activate
python initial_code.py
```

## 📊 Estado Actual del Código

### ❌ Problemas Identificados

- 🔴 **SRP Violation**: `PaymentProcessor` maneja múltiples responsabilidades
- 🔴 **OCP Violation**: Modificación de código para nuevas funcionalidades
- 🔴 **DIP Violation**: Dependencias hardcodeadas en lugar de inyección

### 🎯 Objetivos de Refactorización

1. **Single Responsibility**: Separar validación, procesamiento y notificaciones
2. **Open/Closed**: Crear interfaces para extensibilidad
3. **Liskov Substitution**: Implementar jerarquías correctas
4. **Interface Segregation**: Crear interfaces específicas
5. **Dependency Inversion**: Implementar inyección de dependencias

## 🧪 Herramientas de Desarrollo

### 🔍 Análisis de Código
```bash
mypy initial_code.py          # Verificación de tipos
ruff check .                  # Linting
black --check .               # Formato de código
```

### 🧪 Ejecutar Tests
```bash
pytest                        # Ejecutar todos los tests
pytest --cov                  # Con cobertura de código
```

## 📁 Estructura del Proyecto

```
📦 solid_platzi/
├── 📄 initial_code.py      # Código inicial (viola SOLID)
├── 📄 requirements.txt     # Dependencias del proyecto
├── 📄 .env                 # Variables de entorno
├── 📄 .gitignore          # Archivos ignorados por git
├── 📄 CLAUDE.md           # Guía para desarrollo
├── 📄 README.md           # Este archivo
└── 📁 venv/               # Entorno virtual
```

## 🎓 Principios SOLID

| Principio | Descripción | Estado |
|-----------|-------------|---------|
| **S**ingle Responsibility | Una clase debe tener una sola razón para cambiar | ❌ |
| **O**pen/Closed | Abierto para extensión, cerrado para modificación | ❌ |
| **L**iskov Substitution | Los objetos derivados deben ser sustituibles por sus bases | ⚠️ |
| **I**nterface Segregation | Los clientes no deben depender de interfaces que no usan | ❌ |
| **D**ependency Inversion | Depender de abstracciones, no de concreciones | ❌ |

## 🤝 Contribuir

1. 🍴 Fork el proyecto
2. 🌿 Crear una rama feature (`git checkout -b feature/nueva-funcionalidad`)
3. 💾 Commit tus cambios (`git commit -m 'feat: add nueva funcionalidad'`)
4. 📤 Push a la rama (`git push origin feature/nueva-funcionalidad`)
5. 🔄 Abrir un Pull Request

## 📜 Licencia

Este proyecto está bajo la Licencia MIT - ver el archivo [LICENSE](LICENSE) para más detalles.

## 👨‍💻 Autor

**Daniel Cañón** - [GitHub](https://github.com/daecazu)

---

⭐ ¡Dale una estrella al proyecto si te ayudó a aprender sobre SOLID!