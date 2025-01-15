# Gestión de Versiones y Dependencias con Poetry

Este capítulo aborda la gestión de dependencias y versiones utilizando **Poetry**, junto con entornos de Python manejados por **Anaconda**. El repositorio base disponible en [https://github.com/SPMINE-2425/primer_repo_izainea](https://github.com/SPMINE-2425/primer_repo_izainea) sirve como punto de partida para proyectos organizados y reproducibles.

---

## **1. Repositorio Base**

El repositorio plantilla incluye una estructura básica organizada para proyectos de ciencia de datos. Su estructura contempla carpetas dedicadas para datos, cuadernos, código y documentación.

🔗 **Repositorio base**: [primer_repo_izainea](https://github.com/SPMINE-2425/primer_repo_izainea)

Estructura del proyecto:
- **Cuadernos**: Notebooks destinados a la exploración, visualización y modelos.
- **Código**: Scripts principales, APIs y aplicaciones de Streamlit.
- **Datos**: Conjuntos de datos necesarios para el análisis.
- **Documentación**: Información detallada sobre el proyecto.

```{important}
El uso de una estructura bien definida y el repositorio plantilla facilita la colaboración y mantiene un flujo de trabajo organizado.
```

---

## **2. Instalación de Dependencias**

La gestión de dependencias y versiones del proyecto se realiza con **Poetry**, mientras que **Poetry** e **IPython Kernel** se instalan inicialmente con `pip`.

### **Paso 1: Uso de Anaconda Prompt en Windows**
La **Anaconda Prompt** es recomendada para usuarios de Windows, ya que simplifica la gestión de entornos virtuales y asegura compatibilidad con dependencias.

```{tip}
En Windows, ejecutar todos los comandos desde Anaconda Prompt garantiza la correcta configuración del entorno.
```

### **Paso 2: Creación de un Entorno Virtual**
La creación de entornos virtuales permite aislar las dependencias del proyecto. Con Anaconda, se puede ejecutar:
```bash
conda create -n mi_proyecto python=3.12
conda activate mi_proyecto
```

```{caution}
La activación del entorno virtual antes de instalar dependencias o realizar configuraciones asegura que estas se apliquen únicamente al proyecto.
```

### **Paso 3: Instalación de Poetry e IPython Kernel**
Con el entorno virtual activado, se instalan **Poetry** e **IPython Kernel**:
```bash
pip install poetry ipykernel
```

Esta configuración permite gestionar las dependencias con Poetry y habilitar el entorno virtual para su uso en Jupyter Notebook.

---

## **3. Configuración del Proyecto con Poetry**

Poetry ofrece herramientas avanzadas para gestionar las dependencias del proyecto y garantizar su reproducibilidad.

### **Inicialización del Proyecto**
La inicialización del proyecto con Poetry se realiza desde la carpeta del proyecto:
```bash
poetry init
```

Durante el proceso, se solicita:
- Nombre del proyecto.
- Versión inicial (por ejemplo, `0.1.0`).
- Descripción breve.
- Configuraciones predeterminadas para dependencias.

```{important}
El archivo `pyproject.toml` generado centraliza la configuración del proyecto y define las dependencias requeridas.
```

### **Adición de Dependencias**
Para instalar librerías necesarias, se utiliza:
```bash
poetry add pandas tqdm
```

Este comando actualiza el archivo `pyproject.toml` y asegura que las dependencias queden registradas.

### **Instalación de Dependencias Existentes**
Si el repositorio ya incluye un archivo `pyproject.toml`, la instalación de dependencias se realiza con:
```bash
poetry install
```

```{danger}
Modificar dependencias directamente con `pip` en proyectos gestionados por Poetry puede causar inconsistencias y no se recomienda.
```

---

## **4. Opciones para Usar Jupyter Notebook**

Se presentan dos opciones para trabajar con Jupyter Notebook: a través de la selección de ambientes en **VS Code** o mediante la creación de un kernel específico.

### **Opción 1: Selección de Ambientes en VS Code**
Al abrir un cuaderno Jupyter (`.ipynb`) en VS Code, la extensión de **Jupyter** detecta automáticamente los entornos virtuales que tienen instalado `ipykernel`. El ambiente correspondiente se selecciona desde la esquina superior derecha.

```{tip}
Configurar ambientes directamente en VS Code es ideal para mantener un flujo de trabajo rápido y sencillo.
```

### **Opción 2: Creación de un Kernel de Jupyter (Opcional)**
La creación de un kernel dedicado es útil para organizar múltiples proyectos o trabajar fuera de VS Code:
1. Registrar el entorno virtual como un kernel:
   ```bash
   poetry run python -m ipykernel install --user --name=mi_proyecto --display-name "Python (mi_proyecto)"
   ```
   - `--name`: Nombre interno del kernel.
   - `--display-name`: Nombre visible en las interfaces de Jupyter.

2. Seleccionar el kernel en Jupyter Notebook o en VS Code.

```{caution}
La creación de kernels puede ser opcional, pero ofrece una solución flexible para proyectos complejos que requieren entornos dedicados.
```

---

## **5. Ejecución de Scripts con Poetry**

Poetry permite ejecutar scripts en el entorno virtual sin necesidad de activarlo previamente:
```bash
poetry run python src/tu_script.py
```

```{important}
El uso de `poetry run` asegura que las dependencias definidas en `pyproject.toml` sean respetadas durante la ejecución.
```

---

## **6. Buenas Prácticas con Poetry**

1. **Mantenimiento del archivo `pyproject.toml`**:
   - Este archivo centraliza la configuración y define las dependencias del proyecto.

2. **Uso del archivo `poetry.lock`**:
   - Este archivo bloquea las versiones específicas de las dependencias, asegurando consistencia entre diferentes máquinas.

3. **Actualización de Dependencias**:
   - Para instalar las versiones más recientes permitidas por `pyproject.toml`, se utiliza:
     ```bash
     poetry update
     ```

4. **Documentación en el `README.md`**:
   - Describir claramente el proceso de instalación y uso facilita la colaboración en equipo.

```{danger}
Modificar manualmente el archivo `poetry.lock` puede generar problemas de compatibilidad. Este archivo debe ser gestionado exclusivamente por Poetry.
```

---

## **7. Colaboración en el Repositorio**

El flujo de trabajo recomendado para colaborar en el repositorio incluye:

1. Clonar el repositorio:
   ```bash
   git clone https://github.com/SPMINE-2425/primer_repo_izainea.git
   cd primer_repo_izainea
   ```

2. Instalar las dependencias registradas:
   ```bash
   poetry install
   ```

3. Realizar cambios y confirmarlos:
   ```bash
   git add .
   git commit -m "Progreso en el proyecto"
   git push origin main
   ```

```{tip}
Mantener un flujo de trabajo estructurado y sincronizado con el repositorio remoto mejora la colaboración y evita conflictos.
```

---


```{important} 
- Los usuarios de Windows deben trabajar con la **Anaconda Prompt** para simplificar la configuración de entornos.
- Poetry gestiona todas las dependencias, mientras que `ipykernel` garantiza la integración con Jupyter.
- Puedes usar el selector de ambientes de Python en VS Code o registrar un kernel dedicado para Jupyter Notebook.

Este enfoque asegura reproducibilidad y facilita el trabajo en equipo. ¡A programar! 🚀
```