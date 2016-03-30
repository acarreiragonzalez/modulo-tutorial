#CREAR UN MÓDULO	
Para crear un módulo debemos usar la herramienta de generación de un módulo básico(SCAFFOLD): Con la línea de comandos situado en la carpeta source de Odoo ejecutamos el siguiente comando:![**](https://github.com/acarreiragonzalez/modulo-tutorial/blob/master/imagenes_readme/SCAFFOLD.jpg)
###VISTAS BÁSICAS
Creamos un archivo xml en la carpeta raíz del módulo creado llamado openacademy.xml. A continuación modificaremos openacademy.xml para cambiar la forma en que se muestran los datos.![**](https://github.com/acarreiragonzalez/modulo-tutorial/blob/master/imagenes_readme/VISTAS-BASICAS.jpg)
Esta modificación hace que en el formulario se muestre una sección que separe en pestañas la descripción y un apartado Acerca de, así como para buscar los cursos por su nombre o descripción.
###RELACIONES ENTRE MODELOS
Crearemos un modelo Sessions que contendrá un curso con un tiempo asignado, para ellos primero creamos la clase Session a models.py
![**](https://github.com/acarreiragonzalez/modulo-tutorial/blob/master/imagenes_readme/RELACIONES-MODELOS.jpg)
Y a continuación establecemos las relaciones entre modelos , esto debe hacerse en el models.xml.Relaciones entre varios a uno, y entre uno a varios:
En este tipo de relación, debemos modificar el curso y el modelo Sesion para reflejar su relación con otros modelos, y que así quede establecida la siguiente relación:
Un curso tiene un usuario Responsable (res users)
Una Sesion tiene un Instructor(res partners)
Una sesión tiene un curso (openacademy.course)![**](https://github.com/acarreiragonzalez/modulo-tutorial/blob/master/imagenes_readme/RELACIONES-MODELOS-2.jpg)
###HERENCIA
La herencia sirve para modificar el modelo Partner ya existente en el nucle de odoo, para eso debemos crear un partner.py para controlarlo.![**](https://github.com/acarreiragonzalez/modulo-tutorial/blob/master/imagenes_readme/PARTNER.jpg)
###CAMPOS COMPUTADOS Y VALORES POR DEFECTO
Puede ser común que muchos campos que se muestran no se recojan directamente de la base de datos si no que estos sean calculados o que puedan tener valores por defecto, por eso debemos establecer una conexión con dichos campos computados, en models.py, y agregamos los campos computados.![**](https://github.com/acarreiragonzalez/modulo-tutorial/blob/master/imagenes_readme/CAMPOS-COMPUTADOS.jpg)
Y a continuación, establecemos los campos con valores por defecto en el models.py![**](https://github.com/acarreiragonzalez/modulo-tutorial/blob/master/imagenes_readme/CAMPOS-COMPUTADOS-2.jpg)
###ONCHANGE
La siguiente parte de código no sirve para conseguir una advertencia cuando se introducen valores no válidos, como por ejemplo, un número nativo de asientos o más participantes que asientos.
![**](https://github.com/acarreiragonzalez/modulo-tutorial/blob/master/imagenes_readme/ONCHANGE.jpg)
###RESTRICCIONES DE UN MÓDULO
De nuevo introduciremos código en Models.py, referente a restricciones, en este caso servirá para advertirnos si el instructor no está presente en los asientos de su propia sesión.
Continuamos en Models.py. En este caso se añadirá una limitación, la cual comprueba que la descripción del curso y el título del curso son diferentes, y también que el nombre del curso es único.
![**](https://github.com/acarreiragonzalez/modulo-tutorial/blob/master/imagenes_readme/RESTRICCIONES-MODULO.jpg)
Debido a lo introducido anteriormente se ha deshabilitado la posibilidad de utilizar la función “duplicar”, por ello debemos volver a implementarla (con el siguiente código):
###VISTAS AVANZADAS
En el siguiente paso, nos dedicaremos a darle formato a diferentes partes. Para la primera haremos una modificación en el apartado Sesion  de tal forma que las sesiones que duren menos de cinco días serán de color azul , y las que duren más de quince días, de color rojo.
Continuamos con la agregación de un calendario para el apartado Sesion que nos permitirá ver los eventos asociados a cada curso abierto.
Puntos de vista de la búsqueda, con esto nos referimos a añadir un botón para filtrar los cursos para los cuales el usuario actual es el responsable en la vista de búsqueda de cursos que se ha seleccionado por defecto.
Lo siguiente que agregaremos serán los diagramas de Gantt, que permitirá al usuario ver la programación de sesiones relacionada con el módulo openacademy.
![**](https://github.com/acarreiragonzalez/modulo-tutorial/blob/master/imagenes_readme/VISTAS-AVANZADAS.jpg)
Para continuar, agregaremos una vista de gráficos en sesión que muestre, para cada curso, el número de asistentes bajo la forma de un gráfico de barras.

![**](https://github.com/acarreiragonzalez/modulo-tutorial/blob/master/imagenes_readme/VISTAS-AVANZADAS.jpg)

Por último, en este tutorial añadiremos la vista kanba, una vista que muestra las sesiones agrupadas por columnas.


####Hasta aquí este tutorial amigos###