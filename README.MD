# Proyecto de Ciencia de Datos

![Banner del Proyecto](https://via.placeholder.com/800x200.png?text=Proyecto+Ciencia+de+Datos)

![Python](https://img.shields.io/badge/Python-3.10-blue)
![pandas](https://img.shields.io/badge/pandas-2.2.3-orange)
![tqdm](https://img.shields.io/badge/tqdm-4.67.0-lightgrey)


**Versión:** 0.0.0
**Autor:** [IZAINEA](mailto:cizaineam@gmail.com)  


## Descripción

Este proyecto tiene como objetivo [inserta aquí la descripción de tu proyecto]. En este repositorio encontrarás los cuadernos de Jupyter, código fuente, datos y documentación necesarios para reproducir y entender los análisis y modelos desarrollados.

## Estructura del Proyecto

- **Cuadernos**: Exploración de datos, análisis, visualización y desarrollo de modelos.
- **Código**: APIs, Apps de Streamlit y cálculos batch.
- **Datos**: Conjuntos de datos utilizados en el proyecto.
- **Documentación**: Información relevante y explicaciones detalladas del proyecto.

## Instalación

Para instalar todas las dependencias necesarias, puedes usar los siguientes comandos. Asegúrate de tener Python 3.12 instalado:

```bash
pip install pandas==2.2.2
pip install [otros paquetes necesarios]
```

## Uso

A continuación, se muestra cómo puedes ejecutar algunos de los scripts principales del proyecto:

```bash
python src/tu_script.py
```

## Requisitos

![Python](https://img.shields.io/badge/Python-3.12-blue)
![pandas](https://img.shields.io/badge/pandas-2.2.2-orange)

## Acceso al Repositorio

Puedes acceder al repositorio completo [aquí](https://github.com/tu_usuario/tu_repositorio).

## Contacto

Para cualquier duda o sugerencia, no dudes en contactarme a través de [tu_correo@ejemplo.com](mailto:tu_correo@ejemplo.com).


## Manual de Instalación y Configuración

Este manual explica cómo instalar **Visual Studio Code**, **Git**, y **Miniconda** en sistemas operativos Windows, Linux y macOS. Además, se incluye una guía sobre el uso de WSL en Windows y cómo conectar WSL a Git mediante SSH.

---

## 1. Instalación de Visual Studio Code (VS Code)

### **Windows**
1. Descarga el instalador desde [VS Code](https://code.visualstudio.com/Download).
2. Ejecuta el archivo `.exe` descargado.
3. Sigue las instrucciones del instalador. Asegúrate de:
   - Marcar **"Agregar al PATH"**.
   - Seleccionar las integraciones opcionales como **"Registrar como editor de texto por defecto"**.

### **Linux**
1. Abre la terminal.
2. Ejecuta los siguientes comandos:
   ```bash
   sudo apt update
   sudo apt install wget gpg
   wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
   sudo install -o root -g root -m 644 packages.microsoft.gpg /usr/share/keyrings/
   sudo sh -c 'echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/packages.microsoft.gpg] https://packages.microsoft.com/repos/vscode stable main" > /etc/apt/sources.list.d/vscode.list'
   sudo apt update
   sudo apt install code

3. Abre VS Code escribiendo code en la terminal.



macOS

1. Descarga el instalador desde VS Code.


2. Arrastra el archivo descargado a la carpeta Aplicaciones.


3. Para añadir code al terminal, abre VS Code y presiona Ctrl+Shift+P. Escribe Shell Command: Install 'code' command in PATH y presiona Enter.




---

2. Instalación de Git

Windows

1. Descarga Git desde git-scm.com.


2. Ejecuta el instalador y selecciona:

Usar Git desde la línea de comandos y software de terceros.

Selecciona el editor por defecto (ej. VS Code).

Configura las opciones de línea de comandos según tus preferencias.




Linux

1. Abre la terminal y ejecuta:

sudo apt update
sudo apt install git


2. Verifica la instalación:

git --version



macOS

1. Abre la terminal y ejecuta:

brew install git

(Si no tienes Homebrew, instálalo desde brew.sh).


2. Verifica la instalación:

git --version




---

3. Instalación de Miniconda

Windows

1. Descarga Miniconda desde Miniconda.


2. Ejecuta el instalador y selecciona:

Agregar Miniconda al PATH (opcional).

Configurar como el gestor de paquetes por defecto.




Linux

1. Descarga Miniconda:

wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh


2. Ejecuta el instalador:

bash Miniconda3-latest-Linux-x86_64.sh


3. Sigue las instrucciones en pantalla.



macOS

1. Descarga Miniconda desde el sitio oficial.


2. Ejecuta el archivo descargado en la terminal:

bash Miniconda3-latest-MacOSX-x86_64.sh


3. Sigue las instrucciones en pantalla.




---

4. Instalación y Configuración de WSL (Windows Subsystem for Linux)

1. Habilitar WSL:

Abre PowerShell como administrador y ejecuta:

wsl --install

Esto instalará WSL2 y Ubuntu como distribución por defecto.



2. Actualizar a WSL2 (si es necesario):

wsl --set-default-version 2


3. Abrir y configurar WSL:

Escribe wsl en el terminal o abre Ubuntu desde el menú Inicio.

Configura tu usuario y contraseña.



4. Conectar WSL con VS Code:

Instala la extensión Remote - WSL desde el Marketplace de VS Code.

Abre una terminal en WSL ejecutando code . dentro de la terminal de WSL.





---

5. Conectar WSL a Git mediante SSH

Generar una clave SSH

1. En WSL, genera una clave SSH:

ssh-keygen -t rsa -b 4096 -C "tu-email@example.com"


2. Presiona Enter para aceptar las ubicaciones predeterminadas y asignar una contraseña (opcional).


3. Agrega la clave SSH al agente:

eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa



Agregar la clave SSH a GitHub

1. Copia la clave pública:

cat ~/.ssh/id_rsa.pub


2. Ve a GitHub > SSH and GPG keys > New SSH Key.


3. Pega la clave pública en el campo proporcionado y guárdala.



Configurar Git en WSL

1. Configura tu nombre y correo en Git:

git config --global user.name "Tu Nombre"
git config --global user.email "tu-email@example.com"


2. Prueba la conexión con SSH:

ssh -T git@github.com

Si ves un mensaje como "Hi <username>! You've successfully authenticated.", todo está funcionando correctamente.




---




# Manual de Creación de Ambientes con Conda y Gestión de Dependencias con Poetry

Este manual explica cómo crear y administrar ambientes en **Conda**, instalar **Poetry** con `pip`, y gestionar dependencias para tus proyectos.

---

## 1. Crear y Administrar Ambientes con Conda

### **1.1. Crear un Ambiente Nuevo**
1. Abre la terminal.
2. Crea un ambiente con el siguiente comando:
   ```bash
   conda create --name <nombre_del_ambiente> python=<versión>

Ejemplo:

conda create --name mi_ambiente python=3.10

3. Activa el ambiente:

conda activate <nombre_del_ambiente>

Ejemplo:

conda activate mi_ambiente



1.2. Instalar Dependencias Iniciales

1. Dentro del ambiente recién activado, instala ipykernel y poetry usando pip:

pip install ipykernel
pip install poetry


2. Verifica que Poetry se haya instalado correctamente:

poetry --version




---

2. Gestión de Dependencias con Poetry

2.1. Inicializar un Proyecto con Poetry

1. Dentro del ambiente Conda y en la carpeta de tu proyecto, inicializa Poetry:

poetry init

Sigue las instrucciones para configurar el archivo pyproject.toml.



2. Alternativamente, puedes crear un proyecto completo con:

poetry new <nombre_del_proyecto>

Esto creará una estructura de carpetas organizada para tu proyecto.



2.2. Instalar Dependencias

1. Agrega dependencias con Poetry:

poetry add <nombre_del_paquete>

Ejemplo:

poetry add pandas numpy


2. Agrega dependencias solo para desarrollo:

poetry add --dev <nombre_del_paquete>

Ejemplo:

poetry add --dev pytest black



2.3. Crear el Ambiente Virtual

1. Activa el ambiente virtual gestionado por Poetry:

poetry shell


2. Instala todas las dependencias registradas en pyproject.toml:

poetry install




---

3. Integración entre Conda y Poetry

Aunque Conda y Poetry pueden trabajar por separado, puedes combinarlos fácilmente para aprovechar lo mejor de ambos.

1. Instala dependencias específicas con Conda: Si necesitas una dependencia que solo está disponible en Conda (ejemplo: tensorflow o cudatoolkit), instálala directamente:

conda install -c conda-forge <nombre_del_paquete>


2. Continúa gestionando otras dependencias con Poetry: Una vez instalado el paquete con Conda, utiliza Poetry para manejar el resto de las dependencias del proyecto.




---

4. Buenas Prácticas

1. Siempre trabaja en ambientes virtuales aislados: Esto evita conflictos de dependencias.


2. Mantén actualizado tu pyproject.toml y poetry.lock: Estos archivos son clave para la reproducibilidad del proyecto.


3. Documenta tus dependencias: Usa el comando poetry export para generar un archivo requirements.txt en caso de compartir el proyecto:

poetry export --without-hashes -f requirements.txt -o requirements.txt





