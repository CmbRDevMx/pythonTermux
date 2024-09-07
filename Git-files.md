Git LFS (Large File Storage) es una extensión de Git diseñada para manejar archivos grandes que no son adecuados para el seguimiento directo en un repositorio Git tradicional debido a su tamaño. En lugar de almacenar el archivo completo en el repositorio, Git LFS guarda un puntero al archivo en el repositorio, y el archivo real se almacena en un servidor separado.

Aquí te dejo una guía básica para usar Git LFS en GitHub:

### 1. **Instalar Git LFS**
Primero, debes instalar Git LFS en tu sistema. Dependiendo de tu sistema operativo, sigue las instrucciones correspondientes:

- **Linux**:
  ```bash
  sudo apt-get install git-lfs
  ```
- **MacOS**:
  ```bash
  brew install git-lfs
  ```
- **Windows**:
  Descarga e instala desde [git-lfs.github.com](https://git-lfs.github.com/).

### 2. **Inicializar Git LFS en tu repositorio**
Después de la instalación, necesitas inicializar Git LFS en tu repositorio:

```bash
git lfs install
```

### 3. **Rastrear archivos grandes con Git LFS**
Debes indicar a Git LFS qué archivos grandes deseas rastrear. Por ejemplo, si tienes un archivo grande llamado `archivo-grande.zip`, puedes hacerlo de la siguiente manera:

```bash
git lfs track "archivo-grande.zip"
```

Este comando crea un archivo llamado `.gitattributes` en tu repositorio que contiene las reglas para Git LFS.

### 4. **Agregar y confirmar los cambios**
Después de rastrear los archivos grandes con Git LFS, agrégalos y confírmalos en tu repositorio de la forma habitual:

```bash
git add archivo-grande.zip
git commit -m "Añadir archivo grande con Git LFS"
```

### 5. **Subir el repositorio a GitHub**
Finalmente, sube tu repositorio a GitHub. Git LFS se encargará de gestionar los archivos grandes automáticamente:

```bash
git push origin main
```

### 6. **Verificar que Git LFS esté funcionando**
Puedes verificar que Git LFS está funcionando correctamente usando el siguiente comando para ver qué archivos están siendo rastreados por Git LFS:

```bash
git lfs ls-files
```

### **Limitaciones de GitHub con Git LFS**
- **Almacenamiento LFS**: GitHub proporciona 1 GB de almacenamiento gratuito para Git LFS y 1 GB de ancho de banda de transferencia por mes. Si excedes esto, puedes adquirir más almacenamiento o ancho de banda.
- **Archivo individual**: GitHub permite almacenar archivos individuales de hasta 2 GB usando Git LFS.

### **Consideraciones finales**
Usar Git LFS es una excelente manera de mantener tu repositorio limpio y manejable, especialmente cuando trabajas con archivos grandes que no cambian con frecuencia. Esto es muy útil en proyectos que requieren almacenar binarios, imágenes, videos, modelos de aprendizaje automático, entre otros archivos pesados.

Si estás utilizando GitHub como plataforma, Git LFS es una herramienta eficaz para mantener el rendimiento del repositorio mientras se gestionan archivos de gran tamaño
