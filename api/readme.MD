# <u>Comandos github</u>

Les explico brevemente por ahora los comandos que deberian usar:

Primero clonen el repositorio con git clone [url de este repo]([GitHub - Red-movement/firstRed](https://github.com/Red-movement/firstRed.git)) como siempre.

Una vez clonado les va a aparecer como primera instancia en la rama Main, esta es justamente la que no deben tocar

para crear una rama nueva deben hacer lo siguiente:

Ejecuten el comando `git pull` para poder actualizar todo el repo de forma local.

Luego debemos crear una nueva rama con el nombre que querramos para poder trabajar, para esto lo que debemos hacer es lo siguiente: usando el comando `git checkout develop` lo que vamos a hacer es cambiarnos a la rama develop la

cual va a ser la rama que mas este actualizada, realizamos un `git pull` nuevamente para poder actualizarla de

acuerdo al repositorio remoto.

Ahora es cuando comienza la magia, para poder crear nuestra rama en base a la rama develop (**Recalco: esta es la***

**rama que va a tener mas cambio, Main solo recibira grandes cambios una ves este todo probado**) usaremos el comando

`git checkout -b [nombre que decidan para su rama]`. Una vez creada, podran trabajar en ella sin problemas e ir

pusheando codigo todas las veces que deseen sin miedo a afectar otras ramas

**<u>Dato de vital importancia para la trama:</u>** Lo ideal a la hora de nombrar su rama es que sea con el nombre de la

funcionalidad que esten trabajando, ejemplo, voy a trabajar en el boton de agregado de usuarios por lo tanto mi

rama la creare usando `git checkout -b addUserButton`. Sino en todo caso pueden llamar a las ramas con su nombre

---

# <u> Base de datos</u>

Aca estoy definiendo lo que van a ser las tablas de la base de datos, esto se hara en postgreSQL y con algun ORM de Flask (por favor quien se acuerde cual era, agreguelo jeje)

###<u> Usuario:</u>

- ID

- Nombre

- Contraseña // sera un jwt

- Email

- TIpo de ususario (User, Admin)

- Foto de perfil

###<u>Movimientos:</u>

- ID * automatico

- Fecha * automatico

- Titulo *

- Tipo (egreso o ingreso) // estas son opciones fijas *

- Monto *

- Categoria (fijo, diario, emergencia, recreacion, ahorro) // estas pueden cambiar pero se va a guardar solo ID *

- Descripcion

- Aviso (notificacion) // por el momento no prestarle atencion

###<u>Categorias:</u>

- ID

- Nombre

Estas en principio serian nuestras primeras tablas, se pueden agregar o modificar

Relaciones:

Usuarios a movimientos => uno a muchos

Categorias a movimientos => muchos a muchos

---

# <u>Python</u>

Por el momento veremos de trabajar con un entorno virtual (virtual env) para poder ejecutar las instancias de python con las librerias que necesitamos. Actualmente estoy trabajando con la version 3.9.2 de python pero dentro de la version 3 si trabajamos todos con esa no deberiamos tener problemas.

Para crear el entorno virtual deben utilizar la linea de comandos de python para ejecutarlo. Los comandos son:

`python -m venv [nombre del entorno]`

Esto les creara una serie de carpetas donde se encontraran todas las configuraciones, dependencias y archivos para que funcione el virtualenv

**<u>Aclaracion:</u>** en este caso les diria que usemos como nombre del entorno <mark>gasty</mark> para asi queda consistente con el archivo .gitignore que deje en esta rama

Luego para ejecutar nuestro virtual env debemos hacer lo siguiente:

**<u>Windows:</u>** `gasty\Scripts\activate.bat`

**<u>Linux / Unix o Mac:</u>** `source gasty/bin/activate`

Por si lo necesitan desactivar solo usen el comando `deactivate`

Por ultimo y no menos importante quedaria instalar los paquetes y dependencias, para esto usaremos los comandos de siempre: `pip install [nombre del modulo]`

Pero Pero Pero... Deje un archivo (si prestan atencion) el cual se llama requirements.txt, esto tiene las dependencias que apenas instale hasta este dia y que me parecieron ser las iniciales, por lo tanto el comando `pip install` va a tener una pequeña variacion y quedara asi:  `pip install -r requeriments.txt` y va a instalar flask de momento con el ORM (SQLalchemy).

Pd: Me olvide de agregarles como hacer para actualizar el archivo requeriments.txt en caso que instalen una libreria nueva. Para esto, tienen que instalarla como siempre: `pip install [nombre de la libreria]` y despues `pip freeze > requeriments.txt`

> Have Fun!!!!!

---

# <u> Docker</u>

###¿Que es docker?

En terminos simples: Docker es un sistema que te permite virtualizar entornos de desarrollo dentro de un sistema operativo encapsulado. En resumen seria algo asi como tener un sistema operativo dentro de tu sistema operativo donde puedes meter mano sin miedo a romper nada y que todo lo que tengas en tu sistema operativo actual no sea dañado.

Para instalarlo deverian consultar la pagina oficial de Docker [Get Docker | Docker Documentation](https://docs.docker.com/get-docker/)  y seguir los pasos segun su sistema operativo. 🔴 tienen que activar la virtualizacion en su pc (yo sufri mucho con la mia, hay que meter mano en la bios pero se puede), es un proceso simple si encuentran el tutorial indicado pero como me genero traumas aca en este punto los abandono.

Docker tambien se maneja con dos terminos importantes que serian los contendores y las imagenes, los contenedores son por asi decirlo pc´s virtuales donde se ejecutan los diversos sistemas operativos que le agreguemos y despues estan las imagenes que son justamente los sistemas operativos que instalamos y que usamos.

Para no complejizar mucho esto, investigue un poco y deje en este repo un archivo Dockerfile el cual tiene toda la info para que podamos instalar y usar una imagen con lo basico de momento para instalar python para empezar a desarollar con flask y sqlalchemy

---

<img title="" src="https://upload.wikimedia.org/wikipedia/commons/thumb/2/26/Glider-white.svg/800px-Glider-white.svg.png" alt="image.png" width="140" height="140">
