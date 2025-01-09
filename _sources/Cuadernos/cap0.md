# Instalación y configuración previa

En este apartado se describen los pasos necesarios para instalar y configurar las herramientas que se utilizarán en el curso. Asegúrate de seguir las instrucciones correspondientes a tu sistema operativo.

Instalaremos las siguientes herramientas:

- **Visual Studio Code**: Editor de código fuente con soporte para múltiples lenguajes de programación.
- **Conda**: Gestor de paquetes y entornos virtuales para Python.
- **Git**: Sistema de control de versiones distribuido.

## Instalación de Visual Studio Code

[![img](../static/vscode.png)](https://code.visualstudio.com/Download)

### En Windows

1. **Descarga**: Visita la página oficial de descargas de Visual Studio Code: [https://code.visualstudio.com/Download](https://code.visualstudio.com/Download).

2. **Selecciona la versión adecuada**: Elige el instalador que corresponda a tu sistema:
   - **User Installer** para instalaciones sin privilegios de administrador.
   - **System Installer** si tienes privilegios de administrador y deseas que VS Code esté disponible para todos los usuarios del sistema.

3. **Instalación**:
   - Ejecuta el archivo descargado (`VSCodeUserSetup-{versión}.exe` o `VSCodeSetup-{versión}.exe`).
   - Sigue las indicaciones del asistente de instalación.
   - Durante la instalación, puedes seleccionar opciones adicionales, como:
     - Agregar VS Code al **PATH** para acceder al comando `code` desde la terminal.
     - Asociar VS Code con ciertos tipos de archivos.

4. **Verificación**:
   - Una vez completada la instalación, abre una terminal (`cmd` o PowerShell) y ejecuta:
     ```bash
     code --version
     ```
   - Esto debería mostrar la versión instalada de VS Code, confirmando que la instalación fue exitosa.

5. **Instalación de extensiones recomendadas**:
   - Abre VS Code.
   - Navega a la sección de extensiones (ícono de cuadrados en la barra lateral izquierda) y busca e instala las siguientes extensiones:
     - **Python**: Proporciona soporte para desarrollo en Python.
     - **GitLens**: Mejora la funcionalidad de Git integrada.
     - **Markdown All in One**: Ofrece herramientas para trabajar con archivos Markdown.

### En macOS

1. **Descarga**: Accede a la página oficial de descargas de Visual Studio Code: [https://code.visualstudio.com/Download](https://code.visualstudio.com/Download).

2. **Selecciona la versión adecuada**: Descarga el archivo `.zip` correspondiente a tu arquitectura:
   - **Intel chip** para Macs con procesadores Intel.
   - **Apple silicon** para Macs con procesadores M1 o M2.
   - **Universal** para compatibilidad con ambas arquitecturas.

3. **Instalación**:
   - Descomprime el archivo `.zip` descargado.
   - Mueve la aplicación "Visual Studio Code" a la carpeta **Aplicaciones**.

4. **Configuración del comando `code`**:
   - Abre VS Code.
   - Presiona `Cmd+Shift+P` para abrir la paleta de comandos.
   - Escribe `Shell Command: Install 'code' command in PATH` y selecciona la opción que aparece.
   - Esto permitirá abrir VS Code desde la terminal usando el comando `code`.

5. **Verificación**:
   - Abre la aplicación **Terminal** y ejecuta:
     ```bash
     code --version
     ```
   - Deberías ver la versión instalada de VS Code, confirmando que la instalación fue exitosa.

6. **Instalación de extensiones recomendadas**:
   - Abre VS Code.
   - Dirígete a la sección de extensiones (ícono de cuadrados en la barra lateral izquierda) y busca e instala las siguientes extensiones:
     - **Python**: Proporciona soporte para desarrollo en Python.
     - **GitLens**: Mejora la funcionalidad de Git integrada.
     - **Markdown All in One**: Ofrece herramientas para trabajar con archivos Markdown.

## Instalación de Conda (Miniconda o Anaconda)

Conda es un gestor de paquetes y entornos virtuales para Python que facilita la instalación y administración de librerías y dependencias. Puedes instalar Miniconda, una versión ligera de Conda, o Anaconda, que incluye un conjunto de paquetes científicos preinstalados.

[![img](../static/anaconda.png)](https://www.anaconda.com/)

### **En Windows**



1. **Descarga**:
   - Visita la página oficial de [Miniconda](https://docs.anaconda.com/miniconda/) o [Anaconda](https://www.anaconda.com/).
   - Selecciona la versión para Windows que corresponda a tu sistema operativo (32 o 64 bits).

2. **Instalación**:
   - Ejecuta el instalador descargado (`Miniconda3-latest-Windows-x86_64.exe` o el de Anaconda).
   - Acepta los términos de licencia.
   - Selecciona la opción "Instalar solo para mí" o "Instalar para todos los usuarios".
   - **Importante**: Activa la casilla **"Add Miniconda/Anaconda to my PATH environment variable"** para acceder a `conda` desde cualquier terminal.
   - Completa la instalación.

3. **Verificación**:
   - Abre una terminal (`cmd` o `PowerShell`).
   - Ejecuta el siguiente comando para verificar que `conda` está instalado correctamente:
     ```bash
     conda --version
     ```
   - Esto debería mostrar la versión de Conda instalada.

4. **Configuración inicial**:
   - Actualiza Conda ejecutando:
     ```bash
     conda update conda
     ```

---

### **En macOS**

1. **Descarga**:
   - Ve a [Miniconda](https://docs.conda.io/en/latest/miniconda.html) o [Anaconda](https://www.anaconda.com/).
   - Descarga el archivo para macOS (Intel o Apple Silicon).

2. **Instalación**:
   - Abre la terminal y ejecuta el archivo descargado. Por ejemplo:
     ```bash
     bash Miniconda3-latest-MacOSX-x86_64.sh
     ```
   - Sigue las instrucciones en pantalla:
     - Acepta los términos de licencia.
     - Elige la ubicación de instalación predeterminada o personaliza la ruta.

3. **Configuración de PATH**:
   - Una vez finalizada la instalación, reinicia la terminal o ejecuta:
     ```bash
     source ~/.bashrc
     ```
     Si usas Zsh (predeterminado en macOS desde Catalina):
     ```bash
     source ~/.zshrc
     ```

4. **Verificación**:
   - Ejecuta:
     ```bash
     conda --version
     ```
   - Esto debería mostrar la versión instalada.

5. **Configuración inicial**:
   - Actualiza Conda:
     ```bash
     conda update conda
     ```

---

## **Configuración de Entornos Conda**

1. **Crear un nuevo entorno**:
   ```bash
   conda create -n mi_entorno python=3.10
   ```
   - Esto crea un entorno llamado `mi_entorno` con Python 3.10.

2. **Activar el entorno**:
   ```bash
   conda activate mi_entorno
   ```

3. **Desactivar el entorno**:
   ```bash
   conda deactivate
   ```

4. **Listar entornos disponibles**:
   ```bash
   conda env list
   ```

5. **Eliminar un entorno**:
   ```bash
   conda remove --name mi_entorno --all
   ```
    - Esto elimina el entorno `mi_entorno` y todos sus paquetes.

---

## Instalación de Git

Git es un sistema de control de versiones distribuido que permite llevar un registro de los cambios en el código fuente de un proyecto. A continuación, se describen los pasos para instalar Git en Windows, macOS y Linux.

[![img](../static/git.png)](https://git-scm.com/)

### **En Windows**

1. **Descarga**:
   - Visita la página oficial de [Git](https://git-scm.com/).
   - Descarga el instalador correspondiente a tu sistema operativo (32 o 64 bits).

2. **Instala Git**:
   - Ejecuta el instalador descargado (`Git-{versión}-64-bit.exe`).
   - Acepta los términos de licencia.
   - Selecciona la ubicación de instalación y componentes adicionales.
   - **Importante**: Selecciona la opción **"Use Git from the Windows Command Prompt"** para acceder a Git desde la terminal.
   - Completa la instalación.

3. **Verificación**:

    - Abre una terminal (`cmd` o `PowerShell`).
    - Ejecuta el siguiente comando para verificar que Git está instalado correctamente:
      ```bash
      git --version
      ```
    - Deberías ver la versión de Git instalada.

---

### **En macOS**

1. **Instalación con Homebrew**:
   - Abre la terminal y ejecuta:
     ```bash
     brew install git
     ```
    - Si no tienes Homebrew instalado, sigue las instrucciones en [brew.sh](https://brew.sh/).

2. **Verificación**:
    - Ejecuta:
      ```bash
      git --version
      ```
    - Deberías ver la versión de Git instalada.