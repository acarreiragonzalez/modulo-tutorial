#CREAR UN M�DULO	
Para crear un m�dulo debemos usar la herramienta de generaci�n de un m�dulo b�sico(SCAFFOLD): Con la l�nea de comandos situado en la carpeta source de Odoo ejecutamos el siguiente comando:![**](https://github.com/acarreiragonzalez/modulo-tutorial/blob/master/imagenes_readme/SCAFFOLD.jpg)
###VISTAS B�SICAS
Creamos un archivo xml en la carpeta ra�z del m�dulo creado llamado openacademy.xml. A continuaci�n modificaremos openacademy.xml para cambiar la forma en que se muestran los datos.![**](https://github.com/acarreiragonzalez/modulo-tutorial/blob/master/imagenes_readme/VISTAS-BASICAS.jpg)
Esta modificaci�n hace que en el formulario se muestre una secci�n que separe en pesta�as la descripci�n y un apartado Acerca de, as� como para buscar los cursos por su nombre o descripci�n.
###RELACIONES ENTRE MODELOS
Crearemos un modelo Sessions que contendr� un curso con un tiempo asignado, para ellos primero creamos la clase Session a models.py
![**](https://github.com/acarreiragonzalez/modulo-tutorial/blob/master/imagenes_readme/RELACIONES-MODELOS.jpg)
Y a continuaci�n establecemos las relaciones entre modelos , esto debe hacerse en el models.xml.Relaciones entre varios a uno, y entre uno a varios:
En este tipo de relaci�n, debemos modificar el curso y el modelo Sesion para reflejar su relaci�n con otros modelos, y que as� quede establecida la siguiente relaci�n:
Un curso tiene un usuario Responsable (res users)
Una Sesion tiene un Instructor(res partners)
Una sesi�n tiene un curso (openacademy.course)![**](https://github.com/acarreiragonzalez/modulo-tutorial/blob/master/imagenes_readme/RELACIONES-MODELOS-2.jpg)
###HERENCIA
La herencia sirve para modificar el modelo Partner ya existente en el nucle de odoo, para eso debemos crear un partner.py para controlarlo.![**](https://github.com/acarreiragonzalez/modulo-tutorial/blob/master/imagenes_readme/PARTNER.jpg)
###CAMPOS COMPUTADOS Y VALORES POR DEFECTO
Puede ser com�n que muchos campos que se muestran no se recojan directamente de la base de datos si no que estos sean calculados o que puedan tener valores por defecto, por eso debemos establecer una conexi�n con dichos campos computados, en models.py, y agregamos los campos computados.![**](https://github.com/acarreiragonzalez/modulo-tutorial/blob/master/imagenes_readme/CAMPOS-COMPUTADOS.jpg)
Y a continuaci�n, establecemos los campos con valores por defecto en el models.py![**](https://github.com/acarreiragonzalez/modulo-tutorial/blob/master/imagenes_readme/CAMPOS-COMPUTADOS-2.jpg)
###ONCHANGE
La siguiente parte de c�digo no sirve para conseguir una advertencia cuando se introducen valores no v�lidos, como por ejemplo, un n�mero nativo de asientos o m�s participantes que asientos.
![**](https://github.com/acarreiragonzalez/modulo-tutorial/blob/master/imagenes_readme/ONCHANGE.jpg)
###RESTRICCIONES DE UN M�DULO
De nuevo introduciremos c�digo en Models.py, referente a restricciones, en este caso servir� para advertirnos si el instructor no est� presente en los asientos de su propia sesi�n.
Continuamos en Models.py. En este caso se a�adir� una limitaci�n, la cual comprueba que la descripci�n del curso y el t�tulo del curso son diferentes, y tambi�n que el nombre del curso es �nico.
![**](https://github.com/acarreiragonzalez/modulo-tutorial/blob/master/imagenes_readme/RESTRICCIONES-MODULO.jpg)
Debido a lo introducido anteriormente se ha deshabilitado la posibilidad de utilizar la funci�n �duplicar�, por ello debemos volver a implementarla (con el siguiente c�digo):
###VISTAS AVANZADAS
En el siguiente paso, nos dedicaremos a darle formato a diferentes partes. Para la primera haremos una modificaci�n en el apartado Sesion  de tal forma que las sesiones que duren menos de cinco d�as ser�n de color azul , y las que duren m�s de quince d�as, de color rojo.
Continuamos con la agregaci�n de un calendario para el apartado Sesion que nos permitir� ver los eventos asociados a cada curso abierto.
Puntos de vista de la b�squeda, con esto nos referimos a a�adir un bot�n para filtrar los cursos para los cuales el usuario actual es el responsable en la vista de b�squeda de cursos que se ha seleccionado por defecto.
Lo siguiente que agregaremos ser�n los diagramas de Gantt, que permitir� al usuario ver la programaci�n de sesiones relacionada con el m�dulo openacademy.
![**](https://github.com/acarreiragonzalez/modulo-tutorial/blob/master/imagenes_readme/VISTAS-AVANZADAS.jpg)
Para continuar, agregaremos una vista de gr�ficos en sesi�n que muestre, para cada curso, el n�mero de asistentes bajo la forma de un gr�fico de barras.

![**](https://github.com/acarreiragonzalez/modulo-tutorial/blob/master/imagenes_readme/VISTAS-AVANZADAS.jpg)

Por �ltimo, en este tutorial a�adiremos la vista kanba, una vista que muestra las sesiones agrupadas por columnas.


####Hasta aqu� este tutorial amigos###