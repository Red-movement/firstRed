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

- ID

- Tipo (saldo inicial, gasto o ingreso) // estas son opciones fijas

- Monto

- Categoria (fijo, diario, emergencia, recreacion, ahorro) // estas pueden cambiar pero se va a guardar solo ID

- Aviso (notificacion)

###<u>Categorias:</u>

- ID

- Nombre

Estas en principio serian nuestras primeras tablas, se pueden agregar o modificar

Relaciones:

Usuarios a movimientos => uno a muchos

Categorias a movimientos => muchos a muchos



# Python

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












