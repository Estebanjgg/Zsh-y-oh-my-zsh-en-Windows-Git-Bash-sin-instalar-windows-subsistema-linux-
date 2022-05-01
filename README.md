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

NOTA: para acceder al archivo ~/.bashrc nos dirigimos hacia la  carperta donde tenemos instalado nuestro Git bash si anteriormente ya accedimos a ella cuando tuvimos que pegar aquellas carpetas para instalar nuestro zsh dentro de ella vamos hacia la carpeta  **etc**  luego buscamos nuestro archivo  **bash.bashrc** 

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

Si ejecutastes el comando y te sale asi felicidades ya acabas de instalar oh-my-zsh en tu maquina 

<img src="https://res.cloudinary.com/practicaldev/image/fetch/s--vDzT7ynT--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/i/tmv66ab3fvka73a0uyms.png" width="600px" />


------------


# Instalación de complementos y temas 😁 💻🎉

Aora ya tenemos instalado oh-my-zsh vamos a mi parte favorita instalar los complementos y temas unos de los plugins mas populares que nos trae este maravilloso framework es el terminación automática de comandos, directorios, opciones y argumentos de  corrección de ortográfica que estos nos va ayudar a simplificar mucho nuestro trabajo para 

##  Instalando zsh-autosuggestions y zsh-syntax-highlighting 🤟

Primero para poder instalar nuestros plugins  nos dirigimos hacia la carperta origen oh-my-zsh ,esta se encuentra en nuestro directorio c:\Users\NombreDeTuMaquina, estando hay accedemos a la carpeta **.oh-my-zsh**  vamos a la siguiente caperta **custom**  despues a **plugins** ejemplo del directorio C:\Users\NombreDeTuMaquina\.oh-my-zsh\custom\plugins , 

<img src="https://i.postimg.cc/g0D0RSkV/Screenshot-7.png" />

Abrimos el terminal dentro de la carpeta plugins y instalamos los siguientes repositorios 


- Descargando zsh-autosuggestions

```shell
git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions
```
- Descargar zsh-syntax-highlighting

```shell
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
```
despues de instalarlo te va a quedar como se ve en la imagen

<img src="https://i.postimg.cc/SxxFJ1pc/Screenshot-18.png" width="500px" />


Ya instalado nuestros plugins aora tenemos que activarlos  para hacer eso vamos al archivo .zshrc que esta en  C:\Users\NombreDeTuMaquina 

<img src="https://i.postimg.cc/XNykKddZ/Screenshot-10.png" width="600px"  />

Lo abrimos con nuestro editos preferido  nos dirigimos donde dice **plugins=( git )** posiblemente este en la linea 80 estando en en copiamos los siguiente ` sh-autosuggestions zsh-syntax-highlighting`  guardamos los cambios en nuestro editor lo cerramos reiniciamos nuestro terminal y listo 

<img src="https://i.postimg.cc/Sxwy90hY/Screenshot-14.png"  />

Ya nuestro plugins deven estar funcionando perfectamente el autosuggestions funciona cada ves que usamos un linea de comando por ejemplo `git init` y ejecutamos el inmediantemente lo guarda en su historial y ya la proxima vez que uses ese comando ya el te va aparecer automaticamente , y el  zsh-syntax-highlighting  el te va a corregir si escrives una linea de comando errada el aparece en rojo si esta correcta la linea de comando el aparece en verde

<img src="https://i.postimg.cc/SxzB4fxL/ejemplo2.gif"  />

# Instalando temas

Para la instalacion de temas es muy sencillo vamos al siguiente enlase [Theme](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes) hay un sin fin de temas escojes el que te guste  copia el nombre por ejemplo el que viene como por defecto es **robbyrussell** escoje el que guste solo copias el nombre aora  para instalarlo te diriges a tu archivo ` ~/.zshrc`  donde anteriormente copiamos nuestro codigos de zsh-autosuggestions & zsh-syntax-highlighting busca la parte donde dice `ZSH_THEME=""` solo borra donde el tema que tenga hay copia el que te guste guardas los cambios reinia tu terminal y listo

<img src="https://i.postimg.cc/QdksTZRY/Screenshot-17.png"  />

------------


------------

# Referencias

- https://github.com/ohmyzsh/ohmyzsh/wiki/Themes
- https://github.com/zsh-users/zsh-autosuggestions
- https://github.com/zsh-users/zsh-syntax-highlighting
- https://github.com/ohmyzsh/ohmyzsh 
