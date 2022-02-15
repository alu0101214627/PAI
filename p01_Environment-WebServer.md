# Práctica 1. El entorno de desarrollo de PAI. Node Express Static Web Server. Exercism
### Factor de ponderación: 3

### Objetivos
Los objetivos de esta práctica son:
* Realiar algunas tareas administrativas previas para facilitar el trabajo en la asignatura
* Conocer y configurar el entorno de trabajo de la asignatura en el sistema Linux del IaaS
* Configurar y practicar el uso del Visual Studio Code para editar ficheros en la máquina IaaS de la asignatura
* Instalar un servidor web estático en la máquina virtual de la asignatura
* Conocer y configurar el entorno de trabajo de Exercism

### Rúbrica de evaluacion del ejercicio
Se señalan a continuación los aspectos más relevantes (la lista no es exhaustiva)
que se tendrán en cuenta a la hora de evaluar esta práctica:
* Se valorará la realización de las diferentes tareas que se proponen
* El alumnado ha de acreditar que es capaz de editar ficheros de forma remota en su VM usando VSC
* El alumnado ha de ser capaz de instalar y mantener ejecutando un servidor web estático
* El alumnado debe ser capaz de subir la solución a un problema de Exercism a esa plataforma

Para la realización de las prácticas de PAI
debe Ud. estudiar los documentos que se enlazan desde
éste así como realizar todas las tareas que en este documento se proponen.

**Avise al profesor** al finalizar la realización de cada una de las tareas que se indican a continuación. No inicie una nueva tarea sin haber revisado la anterior.

### Entorno de trabajo exterior a la ULL
1. Para el trabajo en las prácticas de la asignatura se utilizará intensivamente el Sistema Operativo Linux,
trabajando fundamentalmente en una máquina virtual disponible a través de la infraestructura [IaaS de la
ULL](https://www.ull.es/servicios/stic/2015/10/27/nuevo-servicio-iaas/).
Es por ello que resulta muy conveniente que el alumnado tenga instalado Linux en el ordenador personal con el que
trabaje desde casa. Optaremos preferentemente por la distribución Ubuntu para que sea la misma que tiene la
máquina virtual de la asignatura.  
Hay al menos dos opciones para ello:

  * Si dispone Ud. de un ordenador propio que pueda formatear (borrando por tanto toda la información)
  instale directamente Ubuntu en él siguiendo (por ejemplo) 
  [estas instrucciones](https://ubuntu.com/tutorials/install-ubuntu-desktop#1-overview). 
  Para esta instalación necesitará Ud. crear un pendrive desde el que pueda arrancar el ordenador. 
  Siga para ello (por ejemplo) 
  [estas otras instrucciones](https://ubuntu.com/tutorials/create-a-usb-stick-on-windows#1-overview).

  * Otra posibilidad es instalar Ubuntu como un sistema "invitado" dentro de Windows usando para ello un
  software de virtualización como VirtualBox. 
  La página [Install Ubuntu on Oracle VirtualBox](https://brb.nci.nih.gov/seqtools/installUbuntu.html)
  contiene las instrucciones a seguir para instalar Ubuntu como sistema invitado en Windows.

Una opción alternativa que se considera menos adecuada consite en no instalar un sistema Linux sino acceder 
a la máquina virtual IaaS de la asignatura desde Windows usando para ello un cliente ssh. 
Se recomienda para este caso instalar en Windows [el cliente ssh PuTTY](https://www.putty.org/) que puede Ud. descargar libremente.  
[Esta imagen](https://raw.githubusercontent.com/fsande/IB-P01-EntornoIaaS/3b0223eef4fff02835108ac59ea8d2f2f26c43cc/img/Putty-connection.PNG)
muestra los parámetros para establecer una conexión con una máquina IaaS usando PuTTY y 
[esta otra](https://raw.githubusercontent.com/fsande/IB-P01-EntornoIaaS/3b0223eef4fff02835108ac59ea8d2f2f26c43cc/img/Putty-login.PNG)
muestra la conexión ya establecida.

En todo caso recuerde que si desea acceder a las máquinas de la Universidad desde fuera del campus
universitario necesitará Ud. configurar una conexión usando VPN.
Para configurar la conexión VPN siga las instrucciones de la página [Servicio de VPN de la ULL](https://www.ull.es/servicios/stic/2016/05/10/servicio-de-vpn-de-la-ull/).  
Para conexiones VPN usando Windows ha de instalar la aplicación Global Protect.
[Esta imagen](https://raw.githubusercontent.com/fsande/IB-P01-EntornoIaaS/3b0223eef4fff02835108ac59ea8d2f2f26c43cc/img/GlobalProtect.PNG)
muestra el establecimiento de la conexión VPN con la red de la ULL,
[esta otra](https://raw.githubusercontent.com/fsande/IB-P01-EntornoIaaS/3b0223eef4fff02835108ac59ea8d2f2f26c43cc/img/GlobalProtect_InicioSesi%C3%B3n.PNG)
muestra el inicio de sesión y finalmente
[esta última](https://raw.githubusercontent.com/fsande/IB-P01-EntornoIaaS/3b0223eef4fff02835108ac59ea8d2f2f26c43cc/img/GlobalProtect_Conectado.PNG)
muestra la conexión ya establecida. 

2. Estudie el documento 
[Manual de administración de Máquinas](https://docs.google.com/document/d/1nj-dxu7LXrNhj3ewCdfaPSc8OV4e_TYpGTQdK78YExY/edit).
Tenga en cuenta que el acceso a la infraestructura IaaS está ligado a que esté Ud. registrada/o en el Aula
Virtual de la Asignatura.
Siga las instrucciones de ese documento para acceder a la [interfaz web de las máquinas IaaS](https://iaas.ull.es)
(necesitará establecer una conexión VPN).

3. TAREA #01
Acceda al [portal de gestión de usuarios](https://usuarios.ull.es/autogestion/cambio_alias/)
del Servicio TIC de la ULL y configure allí una dirección de correo electrónico alternativa a su dirección
`aluXXXX@ull.edu.es`.
Las direcciones (alias) alternativas que el sistema le ofrece han de incluir necesariamente dos dígitos
numéricos (sin significado específico alguno) y permiten que su dirección de correo sea más legible y fácil de
recordar, sobre todo para otras personas.
Podrá utilizar indistintamente las direcciones `aluXXXX@ull.edu.es` y el alias que configure.

4. TAREA #02 
[GitHub](https://github.com/) es una plataforma de desarrollo colaborativo para alojar proyectos utilizando el sistema de control de versiones Git.
Si no dispone ya de una, cree una cuenta en [GitHub](https://github.com/join?ref_cta=Sign+up&ref_loc=header+logged+out&ref_page=%2F&source=header-home). 
Configure el perfil de esa cuenta de modo que incluya una imagen (fotografía) en la que se le reconozca y haga que la cuenta de e-mail asociada sea la dirección institucional o su alias.
Para la configuración de esa cuenta se le recomienda usar su nombre real, puesto que sus repositorios de código en GitHub
pasarán a formar parte de su curriculum profesional.

5. Para editar algunos ficheros en esta sesión se usará el editor [vim](https://www.vim.org/).
Estudie los primeros pasos de [este tutorial](https://blog.desdelinux.net/usando-vim-tutorial-basico/) para que
aprenda lo básico sobre cómo modificar un fichero usando vi.
Con el estudio de este otro [tutorial interactivo on-line](https://www.openvim.com/) debe aprender lo mínimo que necesita
para usar vi en esta sesión.
Si está Ud. interesada/o en aprender vim (es un editor muy potente pero los comienzos son difíciles) dispone
de muchos tutoriales en la web. 
[Este tutorial](https://github.com/Izaird/Vim-primeros-pasos) explica lo básico de vim a través de ejemplos concretos con ficheros de texto.

Para editar algunas líneas concretas de un fichero de texto usando vi siga estas indicaciones:
* Use las teclas con flechas arriba/abajo para mover el cursor a la línea que desee editar.
* Antes de modificar el texto ha de presionar `i` para acceder al modo de inserción de vim.
* Cuando acabe de modificar el texto, pulse ESC (para salir del modo de inserción)
* Ahora escriba `:wq!` y presione ENTER para guardar los cambios en disco. W es para escribir (Write), Q para salir (Quit) y ! se usa para forzar la escritura.

### El Entorno ULL-IaaS

Deje constancia en ficheros locales de la máquina IaaS-ULL en la que trabaja de todos los cambios que realice. 
Estos ficheros ha de subirlos al repositorio que ha de entregar con la práctica. Así, p. ej. si edita Ud. el fichero `/.ssh/config` 
deje una copia de ese fichero el su directorio de trabajo src y nombre ese fichero de modo que se sepa de qué se trata (use por ejemplo el nombre `ssh-config.txt` para ese fichero que ha de entregar. 
Recuerde dejar en el directorio src de su repositorio **copia de todos** los ficheros que edite en el sistema.

Desarrolle en secuencia cada una de las tareas que se describen en los siguientes puntos, pero ocúpese no solo de “ejecutar comandos” 
sino de estudiar y entender el significado e implicaciones de cada uno de ellos.

6. Inicie sesión en Linux en alguno de los PCs de la sala del Centro de Cálculo. 
En este documento se denominará máquina remota a la máquina virtual (VM) del [IaaS-ULL](https://www.ull.es/servicios/stic/2015/10/27/nuevo-servicio-iaas/) 
y máquina local al PC del centro de cálculo en el que está trabajando.

7. Acceda a la [interfaz web](https://iaas.ull.es/ovirt-engine/sso/login.html) 
de la plataforma IaaS-ULL y autentifíquese en esa interfaz con sus credenciales (username + password) de la cuenta institucional. 
[Esta imagen](https://raw.githubusercontent.com/fsande/IB-P01-EntornoIaaS/3b0223eef4fff02835108ac59ea8d2f2f26c43cc/img/1-Ovirt-login.png)
muestra la pantalla de acceso a la interfaz.  
Vea el estado de la máquina y arránquela para comenzar a trabajar con ella.
[Esta imagen](https://raw.githubusercontent.com/fsande/IB-P01-EntornoIaaS/3b0223eef4fff02835108ac59ea8d2f2f26c43cc/img/2-OvirtVMs.png)
muestra las máquinas virtuales disponibles. 
Inicialmente su máquina aparece con estado "Apagado" y se arranca mediante el botón "Ejecutar".  
El proceso de arranque de la máquina puede durar unos minutos.
Una vez que la máquina haya arrancado, tome nota de la Dirección IP de la máquina, que se muestra en el apartado "Detalles" de la máquina.
[Esta imagen](https://raw.githubusercontent.com/fsande/IB-P01-EntornoIaaS/3b0223eef4fff02835108ac59ea8d2f2f26c43cc/img/5-ovirt-Direcci%C3%B3nIP.png)
muestra la pantalla de información correspondiente a una máquina virtual y en ella se muestra la dirección IP de la máquina.   
La [dirección IP](https://en.wikipedia.org/wiki/IP_address) es una secuencia de números (de la forma `10.6.131.106`) que identifican de forma unívoca a cualquier dispositivo conectado a Internet.
Esta dirección será necesaria para establecer conexiones directas a la máquina a través de ssh desde su casa o desde las salas del Centro de Cálculo de la ESIT. 
Anote esa dirección IP puesto que la máquina conserva esa dirección IP de forma estable. 
Si en algún momento experimenta dificultades de conexión, conecte a través de la interfaz web y compruebe que
la dirección de la máquina no ha cambiado.
Para consultar la IP de una máquina en un terminal Linux utilice el comando:
```
$ ifconfig -a
```

8. Abra en el navegador la consola de la máquina (VNC Console (Browser)) y acceda a la misma.
[Esta imagen](https://raw.githubusercontent.com/fsande/IB-P01-EntornoIaaS/3b0223eef4fff02835108ac59ea8d2f2f26c43cc/img/3-ovirt-loginVM1.png)
muestra la pantalla de acceso a la máquina a través de la consola en el navegador.   
Recuerde que inicialmente las credenciales de acceso son: Username - `usuario` y password - `usuario`.
En este primer acceso el sistema le solicitará que introduzca la contraseña actual y que escriba dos veces la
nueva contraseña elegida (véase
[la imagen](https://raw.githubusercontent.com/fsande/IB-P01-EntornoIaaS/3b0223eef4fff02835108ac59ea8d2f2f26c43cc/img/3-ovirt-loginVM1.png)).
No se preocupe por la contraseña por ahora puesto que siempre la puede cambiar en el futuro con el comando
`passwd` pero **anote** el password que elija para no perderlo u olvidarlo.
La recomendación es que elija ahora un password muy simple (algo como `abcd` y lo cambie por otro que sea robusto y fácil de recordar para Ud.
cuando acceda posteriormente a la máquina a través de ssh.  
Compruebe a continuación el sistema operativo y versión del mismo:
```
$ lsb_release -a
```

9. Actualice el software (paquetes) de la máquina siguiendo las indicaciones de [esta página](https://linuxconfig.org/how-to-update-ubuntu-packages-on-18-04-bionic-beaver-linux) (por ejemplo).
Los comandos que tendrá que utilizar son:
```
$ sudo apt update
$ sudo apt upgrade
$ sudo apt autoremove
```
[Esta imagen](https://raw.githubusercontent.com/fsande/IB-P01-EntornoIaaS/3b0223eef4fff02835108ac59ea8d2f2f26c43cc/img/update.png)
muestra el resultado de ejecución del primero de estos comandos y 
[esta otra](https://raw.githubusercontent.com/fsande/IB-P01-EntornoIaaS/3b0223eef4fff02835108ac59ea8d2f2f26c43cc/img/upgrade2.png)
del segundo de ellos.    
Cuando el sistema le pregunte si hacerlo, indique No instalar `grub`.
Véase 
[esta imagen](https://raw.githubusercontent.com/fsande/IB-P01-EntornoIaaS/3b0223eef4fff02835108ac59ea8d2f2f26c43cc/img/grub.png)
y 
[esta otra](https://raw.githubusercontent.com/fsande/IB-P01-EntornoIaaS/3b0223eef4fff02835108ac59ea8d2f2f26c43cc/img/grub2.png) 
que ilustran esas opciones.


10. Edite los ficheros necesarios para [cambiar el nombre lógico de la máquina](https://askubuntu.com/questions/9540/how-do-i-change-the-computer-name) que le ha sido asignada. 
Se propone utilizar como nombre algo como Ubuntu-18-IB-XXX (cambiando "XXX" por lo que Ud. quiera), aunque puede Ud. usar para su máquina el nombre que prefiera.
Para realizar ese cambio ha de editar Ud. los siguientes ficheros (necesita usar `sudo` para tener permisos de
root al tratarse de ficheros del sistema) y sustituir en ellos el nombre actual de la máquina (que es "ubuntu") por el que haya elegido:
```
$ sudo vi /etc/hostname
$ sudo vi /etc/hosts
```
Para que este cambio tenga efecto, ha de reiniciar la máquina.  
Siempre puede reiniciar la máquina desde la interfaz web de administración o bien usando el comando:
```
$ sudo reboot
```

11. Instale `git` en su máquina:
```
$ sudo apt install git
```
y compruebe que está instalado:
```
$ git --version
```

12. Consiga que se pueda subir código desde su máquina virtual hacia su cuenta GitHub sin necesidad de autentificación. 
Consulte para ello las instrucciones
[Adding a new SSH key to your GitHub account](https://docs.github.com/en/enterprise/2.15/user/articles/adding-a-new-ssh-key-to-your-github-account)

13. Cree un directorio `practicas` y  clone en él un repositorio git:
```
cd
mkdir practicas
cd practicas
git clone git@github.com:fsande/IB-P01-EntornoIaaS.git 2019-2020-IB-P01-EntornoIaaS
```
 
14. En la máquina local ejecute el Microsoft Visual Studio Code (VSC) y siga 
[estas instrucciones](https://code.visualstudio.com/docs/remote/ssh)
para configurar la edición remota de ficheros alojados en su máquina virtual.  
Para instalar VSC en la instalación Linux de su casa siga
[estas instrucciones](https://code.visualstudio.com/docs/setup/linux)
descargando el paquete `.deb`. 
Resulta útil realizar el paso 3 (opcional) del apartadto "SSH host setup#" que se muestra
[en esta página](https://code.visualstudio.com/docs/remote/troubleshooting#_configuring-key-based-authentication)
Ejecute para ello (sustituyendo la dirección IP por la de su VM):
```
$ ssh-keygen -t rsa -b 4096
$ export USER_AT_HOST=usuario@10.6.131.106
$ export PUBKEYPATH="$HOME/.ssh/id_rsa.pub"
$ ssh-copy-id -i "$PUBKEYPATH" "$USER_AT_HOST"
```
[Esta imagen](https://raw.githubusercontent.com/fsande/IB-P01-EntornoIaaS/master/img/VSC-connect-to-host.png)
muestra el paso 2 del apartado "Connect to a remote host" de esas instrucciones mientras que
[esta otra](https://raw.githubusercontent.com/fsande/IB-P01-EntornoIaaS/master/img/VSC-password.png)
muestra la ventana de autentificación de VSC para darle acceso a la máquina virtual.  
Una vez completado este proceso se podrán editar ficheros en la máquina virtual usando VSC.

15. Utilice el VSC para escribir el código fuente del programa 
[HelloWorld.cc](https://github.com/fsande/IB-class-code-examples/blob/master/IntroductionToC%2B%2B/hello_world.cc).
Grabe ese fichero en el directorio ~/practicas/ de su máquina virtual.
Acceda a la máquina virtual usando ssh, compile y ejecute ese programa.

16. Siga [estas instrucciones](http://www.linuxproblem.org/art_9.html) 
para establecer la configuración de la máquina de modo que se pueda conectar a ella sin necesidad de escribir el password en cada conexión. 
Para poder conectarse por ssh con las máquinas virtuales de IaaS ull ha de autentificarse en la página [acceso.ull.es](acceso.ull.es).  
Recuerde que en caso de acceder desde fuera de del campus ULL ha de hacerlo mediante una conexión VPN. 
Consulte [esta referencia](https://www.ull.es/servicios/stic/2016/05/10/servicio-de-vpn-de-la-ull/) 
(en el Centro de Cálculo, por ahora no lo necesita) para conectarse a través de vpn.

17. También resulta conveniente utilizar alguno de los métodos (ssh config o alias) que se presentan en 
[estas instrucciones](https://scotch.io/tutorials/how-to-create-an-ssh-shortcut) 
de modo que se simplifique la conexión con la máquina remota pudiendo escribir algo como:
```
$ ssh maquina_pai
```
para conectarse a la máquina virtual.






























### Servidor web basado en Node y Express
Establezca una conexión `ssh` con su máquina virtual IaaS.

utilice [esta referencia](https://lenguajejs.com/npm/introduccion/que-es/) para conocer `npm` e instalarlo en
su máquina virtual.

Clone este repositorio en su VM del IaaS-ULL y siga estas instrucciones para instalar en la máquina IaaS un servidor web basado en Node y Express. 
No es necesario que conozca los detalles de estas herramientas, sino simplemente seguir las instrucciones suministradas.

Si todo funciona correctamente, al abrir un navegador en la URL `http://<your VM IP address>:8080` debería ejecutar en esa web un programa que calcula el 
valor de PI de forma aproximada.

Modificando convenientemente el fichero index.html (o colocando los ficheros necesarios en su lugar) en el directorio `www` del proyecto 
creado puede visualizar diferentes webs que pudiera crear en el futuro. Experimente con este servidor web.


[![Node Logo](http://sub1.kevinchisholm.com/blog/images/node-js-logo.png)](http://blog.kevinchisholm.com/?s=node)

## Dependencias

Lo que se precisa para ejecutar instalar el servidor: 

* [Node.Js](https://nodejs.org)

### Configuración

* 1 - Clone este repo en el directorio de esta práctica: 

```
git clone git@github.com:fsande/PAI-P02-WebServer-Exercism.git <yourDirectory>
```

* 2 - Sitúese en ese directorio para trabajar en él:

```
cd <yourDirectory>
```

* 3 - Ejecute este comando:

```
npm install
```

* 4 - Ejecute a continuación:

```
npm start
```

* 5 - Abra una página en su navegador con la siguiente dirección:

```
http://<your VM IP address>:8080
```

Para que el servidor web se mantenga activo incluso en el caso de que se cierre la sesión en la máquina
virtual utilice el comando
```
$ nohup sudo -b npm start
```
en el paso 5 anterior.

### Exercism
[Exercism](https://exercism.io/) es una plataforma orientada a aprender a programar o también a mejorar las
capacidades de cualquier programadora.
El objetivo de Exercism es servir como medio para aprender a programar en un determinado lenguaje, y para ello se propone
hacerlo mediante la resolución de ejercicios que otros usuarios han planteado. 
Lo que se persigue es que tanto quien resuelve el problema como quien lo planteó aprendan al mismo tiempo. 
Además, la interacción con el resto de la comunidad podrá llevar a debates para determinar cuál sería la mejor solución para un determinado problema.

La plataforma se basa en una una aplicación de línea de comandos disponible para diferentes sistemas
operativos (Linux, Mac, Windows).
Usando esa aplicación, un usuario puede descargar una serie de ejercicios de programación disponibles en la
plataforma y realizar los correspondientes programas hasta que consiga pasar los diferentes tests que se
suministran con cada ejercicio.

La plataforma puede ser usada en "modo práctica", en cuyo caso no existe la opción de mentorización (solicitar
que una experta le ayude con sus ejercicios), pero aún
así merece la pena practicar los múltiples ejercicios que hallará en la plataforma.

## Primeros pasos en Exercism
Comience por [registrarse en Exercism](https://exercism.io/users/sign_up). 
usando su cuenta de GitHub.
Una vez disponga de una cuenta, configure lo básico de la misma y elija un "track" (un lenguaje) en el que
desee practicar.
Obviamente se propone que elija el track correspondiente a JavaScript++.

Propóngase a continuación resolver el problema "Hello World".
En la página de ese problema (o de cualquier otro) hallará Ud. un enlace que indica *Get started* y 
[Begin walk-through](https://exercism.io/cli-walkthrough).
Si sigue ese enlace le llevará a la página *Welcome to the Exercism installation guide!* con instrucciones
sobre cómo instalar `exercism`.
En este documento se propone instalarla en la máquina virtual Linux de la asignatura.
Eligiendo la opción *Linux* y a continuación la opción *Using snap* se le pedirá que ejecute
```
$ sudo snap install exercism
```
Ese comando instalará en primer lugar `snap` y a continuación `exercism`, que es lo que se persigue.
También en esa página se indica que se compruebe que la instalación es correcta con el comando
```
$ exercism version
```
[`snap`](https://blogubuntu.com/que-es-ubuntu-snap) es un mecanismo alternativo al ya conocido
`apt-get install` para instalar aplicaciones en Ubuntu Linux.
Si quiere Ud. saber más sobre `snap` puede consultar
[esta referencia](https://snapcraft.io/docs/getting-started),
aunque ello no es necesario para el trabajo que se propone realizar con Exercism.

Una vez instalada la aplicación `exercism` el siguiente paso es configurar la interfaz de comandos (CLI) de la
aplicación.
Para ello se pide que se ejecute el comando
```
$ exercism configure --token=xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
```
donde el *token* que figura en el comando anterior se encuentra (es específico de cada usuario) en la [página
de configuración](https://exercism.io/my/settings) de la cuenta de usuario que se ha creado.
Basta copiar de esa página el token y colocarlo en el comando anterior.

El comando anterior, una vez ejecutado indica:
```
You have configured the Exercism command-line client:

Config dir:                       /home/usuario/snap/exercism/5/.config/exercism
Token:         (-t, --token)      xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
Workspace:     (-w, --workspace)  /home/usuario/snap/exercism/5/exercism
API Base URL:  (-a, --api)        https://api.exercism.io/v1
```
A continuación se puede elegir un problema para pasar a resolverlo.
Se propone, como ya se ha dicho, elegir el problema "Hello World".
En la página de ese problema figura una descripción precisa del problema planteado y en la parte derecha de
esa página figuran las instrucciones para:
* Download. Descargar el problema mediante el comando `exercism download --exercise=hello-world --track=javascript`
* Solve. Para resolver el problema se propone usar el editor favorito del usuario. Se recomienda usar Visual
  Studio Code
* Submit. El comando para subir a la plataforma la solución que el usuario proponga.

Si se ejecuta el comando para descargar el problema el sistema responde:
```
exercism download --exercise=hello-world --track=javascript

Downloaded to
/home/usuario/snap/exercism/5/exercism/javascript/hello-world
```
indicando el directorio donde ha colocado el código necesario para trabajar en ese problema.

Revise los ficheros que exercism ha descargado.

## Solución del ejercicio

El siguiente paso consiste en editar el programa (en el caso del problema *Hello World* el fichero a editar es
`hello-world.js`).
Edite ese fichero hasta que considere que tiene una versión operativa.

Si se analizan los tests del problema *Hello World* que figuran en el fichero `hello-world.spec.js`
se observa que la función que los test evalúan es `hello()`.

En la plantilla que Exercism ofrece para la función, ésta se implementa como una 
[arrow function](https://javascript.info/arrow-functions-basics):

```js
export const hello = () => {
  // Place your code here
};
```

Además de la función que evalúan los tests (`hello()` en el caso de este problema) puede Ud. usar cuantas
otras funciones crea conveniente.
La solución no tiene porqué aportarse en una única función (depende de la complejidad del programa).
El módulo que contiene la solución (fichero `hello-world.js`) solo exporta (de ahí la sentencia `export`)
hacia otros módulos las funciones necesarias para evaluar los tests.

Para los módulos, Exercism utiliza 
[sintaxis ES6](https://eloquentjavascript.net/10_modules.html#h_hF2FmOVxw7)
mientras que NodeJS utiliza sintaxis CommonJS.
Es por ello que el programa que se realice no puede ejecutarse directamente en node.
Si se ejecuta, en el caso del problema *Hello World* con Node se obtiene un error:

```
node hello-world.js

export const hello = () => {
^^^^^^

SyntaxError: Unexpected token 'export'
```

Para poder ejecutar los programas de Exercism con la sintaxis de módulos de ES6, una posibilidad es usar 
[babel-node](https://babeljs.io/docs/en/babel-node).

[Babel](https://babeljs.io/)
es un 
[transpiler](https://en.wikipedia.org/wiki/Source-to-source_compiler)
de Javascript. 
Babel se suele utilizar para escribir código JS con características modernas que pudieran no estar
contempladas en NodeJS, como ocurre con la sintaxis ES6 para módulos.

Para instalar `babel-node`:
```
npm install --save-dev @babel/node
```

y una vez instalado se pueden ejecutar los programas JS usando `npx`:

```
npx babel-node hello-world.js
```

A partir de este punto se debiera desarrollar de forma incremental la solución del problema planteado y se
puede usar `console.log()` para evaluar provisionalmente la corrección de los resultados que se están
obteniendo.

## Ejecución de los tests para un determinado problema
Una vez finalizado su programa, el siguiente paso consiste en pasar (superar) los tests del código.
Cada ejercicio de Exercism va acompañado de una serie de tests que el programa debe superar para ser
considerado válido.

Tal como se explica en la página [Running the Tests](https://exercism.io/tracks/javascript/tests), cada problema va
acompañado de sus tests unitarios.

Para comprobar su solución ejecute:

```
$ npm run test
```

Cuando su solución al problema pase todos los tests y esté Ud. satisfecha con la misma, puede remitirla a la
plataforma.
Utilice para ello el comando `exercism submit` que hallará Ud. en la página correspondiente al problema.
Una vez que haya enviado su solución a Exercism recibirá un mensaje similar a este:
```
Your solution has been submitted successfully.
You can complete the exercise and unlock the next core exercise at:

https://exercism.io/my/solutions/xxxx
```
A partir de este punto puede ya ver las soluciones que otras usuarias hayan dado al mismo problema o bien
avanzar con otros problemas de ese mismo "track".
