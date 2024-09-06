## Hacer binarios Python


### Herramientas..
1. Instala herramientas.

```bash
pkg install binutils 

pkg install ldd

```

### Biblioteca

```bash
pip install pyinstaller
```

2. Luego, crea una versión ejecutable de tu script de Python utilizando PyInstaller:

```
pyinstaller --onefile nombre_de_tu_script.py
```

Esto generará un directorio "dist" en la ubicación actual con un archivo ejecutable que puedes mover y ejecutar en cualquier lugar. Por ejemplo, si tu script se llama "mi_script.py", encontrarás un archivo ejecutable llamado "mi_script" dentro del directorio "dist".

3. Copia el archivo ejecutable a tu dispositivo Android en la ubicación que desees.

4. Abre Termux en tu dispositivo Android.

5. Navega hasta el directorio donde copiaste el archivo ejecutable. Puedes usar el comando `cd` para cambiar de directorio.

6. Ejecuta el archivo binario:

```
./nombre_de_tu_script
```


### Contexto

1. Asegúrate de que tu script de Python "encryp_files.py" tenga el shebang adecuado en la parte superior del archivo. El shebang le indicará a Termux que debe usar Python para ejecutar el script. El shebang debe ser algo como:

```python
#!/data/data/com.termux/files/usr/bin/python
```

Asegúrate de que la ruta al intérprete de Python de Termux sea correcta.

2. Dale permisos de ejecución a tu script:

```bash
chmod +x encryp_files.py
```

3. Crea un directorio bin en tu directorio de inicio de Termux si aún no existe:

```bash
mkdir -p ~/bin
```

4. Mueve tu script al directorio bin:

```bash
mv encryp_files.py ~/bin/
```

5. Asegúrate de que el directorio bin esté en tu variable de entorno PATH. Puedes agregarlo al archivo .bashrc o .zshrc (según la shell que utilices) si aún no está configurado:

```bash
echo 'export PATH="$HOME/bin:$PATH"' >> ~/.bashrc  # O ~/.zshrc si usas zsh
```

6. Recarga la configuración de la shell:

```bash
source ~/.bashrc  # O source ~/.zshrc si usas zsh
```

Ahora, podrás ejecutar tu script "encryp_files.py" desde cualquier lugar en Termux como una herramienta binaria personalizada simplemente escribiendo el nombre del archivo sin la extensión, por ejemplo:

```bash
encryp_files.py
```

Esto hará que el script se ejecute como si fuera una herramienta binaria en Termux. Asegúrate de que el script tenga permisos de ejecución y que la variable de entorno PATH esté configurada correctamente para que Termux pueda encontrarlo.
