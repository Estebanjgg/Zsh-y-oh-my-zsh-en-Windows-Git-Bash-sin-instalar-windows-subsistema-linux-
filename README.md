#   Zsh y oh-my-zsh en Windows Git Bash (sin instalar windows subsistema linux) 😮

<img src="https://i.postimg.cc/C5WqnBPW/descarga-1.png"/>

------------

Para un programador tener una buena personalizada en nuestro terminal git bash es muy importante para windows tener esos plugins y temas muy locos que vemos en otros terminales alternativos es un poco limitada ya que unos de los  terminal alternativo como  lo es ZSH  pero que es que lo hace muy famosa entonces decimos que es un terminal alternativo para sistemas operativos Unix que recopila funcionalidades de distintos terminales como Bash, ksh y tcsh.

Es quizás la línea de comandos más flexible y poderosa que hay, ofreciendo numerosas ventajas sobre todo en cuanto escritura de scripts e interpretación de comandos.

Algunas de las ventajas que ofrece ZSH:
- Terminación automática de comandos, directorios, opciones y argumentos.
- Edición de comandos de múltiples líneas.
- Edición de variables.
- Pila buffer de comandos.
- Mayor englobamiento de archivos.
- Mejor manejo de arreglos y variables.
- Corrección ortográfica.
- Altamente personalizable.

Aunque ese terminal alternativo solo lo conseguimos de manera nativa en ubuntu y adoptado por macOS , tiene maneras  de poder instalarlo en windows Por supuesto, podría configurar el shell como quiero bajo WSL, pero WSL no siempre funciona bien con las aplicaciones y herramientas nativas de Windows. Para remediar esto, investigué cómo podía configurar Zsh para que se ejecutara en lugar de Bash en Git Bash. 

# Instalar Zsh en Git Bash

1.  Primero Descargue el paquete zsh de MSYS2 más reciente del repositorio de paquetes de  [MSYS2](https://packages.msys2.org/package/zsh?repo=msys&variant=x86_64) . El archivo tendrá un nombre similar a zsh-5.8-5-x86_64.pkg.tar.zst. 
2. Instale un extractor que pueda abrir archivos ZST como [PeaZip](https://peazip.github.io/) o   [7-Zip Beta](https://www.7-zip.org/).
3. O puedes Descargalo directo [zsh-5.8-5-x86_64](https://github.com/Estebanjgg/Zsh-y-oh-my-zsh-en-Windows-Git-Bash-sin-instalar-windows-subsistema-linux-/files/8598125/zsh-5.8-5-x86_64.pkg.zip)

4. Extraiga el contenido del archivo (que debe incluir carpetas etc y usr ) en su directorio de instalación de Git Bash. Es probable que esté bajo C:\Program Files\Git. Combine el contenido de la carpeta si se le solicita (no se deben anular archivos).


5. Abre Git Bash y ejecuta:
`zsh`

6. IMPORTANTE: configure la finalización de pestañas y el historial en el asistente de primer uso de Zsh. Si por alguna razón no aparece, o lo saltas, vuelve a ejecutarlo:

```shell
#copiar todo junto y pegar en tu terminal si el codigo anterior (zsh) no te sirvio 

autoload -U zsh-newuser-install
zsh-newuser-install -f
```
<img src="https://i.postimg.cc/nztZrvty/Screenshot-2.png" width="400px" />

- Para configurar el historial, presione 1, cambie los valores si lo desea presionando 1-3 y luego presione 0.
- Para configurar la finalización, presione 2 para “Use the new completion system”, y luego presione 0.
- Pulse 0 para guardar la configuración.
<img src="https://i.postimg.cc/HLSMws6s/como-configurar-zsh.gif"  />

Configure Zsh como shell predeterminado agregando lo siguiente a su ~/.bashrc ,

NOTA: para acceder al archivo ~/.bashrc nos dirigimos hacia la  carperta donde tenemos instalado nuestro Git bash si anteriormente ya accedimos a ella cuando tuvimos que pegar aquellas carpetas para instalar nuestro zsh , cuanto estemos dentro de la carpeta vamos hacia la carpeta  **etc**  luego buscamos nuestro archivo  **bash.bashrc** 

<img src="https://i.postimg.cc/8P3CDfjS/Screenshot-3.png"  />

Abrimos el archivos con nuestro editos de texto favorito copiamos y pegamos lo siguiente 

```shell
if [ -t 1 ]; then
  exec zsh
fi
```
Te quedara asi en el editor guardas tu cambios y listo 

<img src="https://i.postimg.cc/zBy4GwJF/Screenshot-15.png"  />
# Instalando oh-my-zsh

Antes de instalar oh-my-zsh vamos haver un poco que es ? 

	Es un framework mantenido por la comunidad de código abierto que permite manejar fácilmente la configuración del terminal ZSH, es altamente personalizable y un gran complemento para usuarios que trabajan constantemente en el terminal ofreciéndoles un ambiente agradable a la vista, con muchas ayudas visuales, facilidad de ubicación y optimización de tareas gracias al la gama de funcionalidades que ofrece la librería de complementos.	


Desde este punto, su Git Bash se comportará esencialmente como un shell Unix Zsh. Para instalar oh-my-zsh, ejecute el comando habitual que ejecutaría en cualquier shell Zsh:

```shell
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
