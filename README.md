# Challenge 05 - Let's go ahead and jump!

## Integrantes del equipo
- Debbimar Díaz Santiago
- Jonlier Díaz Rivera
- Jeremy Curry Romero

## Reglas del juego
Este reto esta basado en hacer un script de c# el cual permita que el robot pueda brincar. Y por otra parte, explicar el proceso de como se realizaron los diferentes mappings como shoot, horizontal/vertical movement,etc.

## Proceso de WASD

<div align="center">
  <img src="https://github.com/user-attachments/assets/dc49dfee-2424-456a-b5cf-2864487b35c2" width="50%" />
  <p><i>Paso 1: Scripts.</i></p>
</div>

El movimiento del jugador con WASD se realizo en clase al igual que la accion de Shooting. Lo primero que se hacia era crear un script, este se lograba yendo a algun objeto, se seleccionaba "add component" luego "new script" y ahi se le nombraba segun su funcion y se guardaba en el folder creado para scripts en assets. Estos son los scripts que se hicieron en clase.


<div align="center">
  <img src="https://github.com/user-attachments/assets/3092d419-8a97-4dcf-929a-04197ce7f2e2" width="50%" />
  <p><i>Paso 2: Player movement update.</i></p>
</div>

Al inicio de clase se habia hecho el movimiento WASD del jugar junto con las flechas con el input viejo. En la imagen el codigo comentado es el old input. Tambien se realizo con los circuitos o mejor dicho los visualScripting con el graph (Imagen siguiente). Al final tuvimos que ir en unity a "edit" luego a "project setting" y cambiar del imput viejo al nuevo. Para esto se tuvo que agregar la libreria de UnityEngine.InputSystem y se agrego una linea de codigo para lo del deltaTime.


<div align="center">
  <img src="https://github.com/user-attachments/assets/28035dd1-9873-4ed3-b582-8e0e897acfcf" width="50%" />
  <p><i>Paso 2: (Old input)</i></p>
</div>

Este es el VisualScripting para el input viejo de movimiento de jugador con WASD. Este se logro yendo a "add component"  despues a VisualScripting y graph. Una vez dentro era cuestion de darle a new node y se agregaba la funcion que se necesitaba para lograr la accion deseada.

<div align="center">
  <img src="https://github.com/user-attachments/assets/f73e3708-c5b7-4336-8e64-adf78a310d1d" width="50%" />
  <p><i>Paso 3: Input</i></p>
</div>

Volviendo al movimiento de jugador, se deshabilito el inout viejo en los settings y se coloco el nuevo y el codigo se reemplazo. Pero para lograr esto habia que bajar en package manager en unity el Input System manager. Una vez se instalo pues se iba a "add component" y se le daba a action.

<div align="center">
  <img src="https://github.com/user-attachments/assets/2012515b-da59-48a1-acb7-6181ed0cecbf"  width="50%" />
  <p><i>Paso 3: (Input SysMap)</i></p>
</div>

Una vez ahi, se le coloco de nombre InputSysMap01 y es una herramienta que sirve para facilitar ese link de la accion que quiere realizar el jugador en el juego.

<div align="center">
  <img src="https://github.com/user-attachments/assets/5fb95c10-da71-4e86-9d2b-8f5379aa297c" width="50%" />
  <p><i>Paso 4: Look player movement</i></p>
</div>

Al finalizar el movimiento WASD pues nos movemos a el movimiento de la pantalla o camara. Al inicio en la clase tambien se habia realizado el mismo con el input viejo y se habia hecho un visual scripting tambien. Pero aqui en la imagen podemos ver el codigo para el input nuevo y tambien una funcion awake que sirve para que el mouse desaparezca dentro del recuadro de imagen mientras se este moviendo la camara. Algo que hay que agregar es que con el input nuevo, el cambio mas grande que hubo en el codigo es el tener que agregar una variable Vector 2 que este tiene los ejes de X y Y entonces el lookValue es de tipo float porque asi el sistema reconoce el movimiento con el valor positivo a un lado y con el negativo hacia a otro.

<div align="center">
  <img src="https://github.com/user-attachments/assets/2d336053-fa9e-4466-9945-0ed02d9a30e4"  width="50%" />
  <p><i>Paso 5: Speed y Rotation</i></p>
</div>

Las variables de speed y rotationSpeed se encuentran privadas pero en un Serialized Field es para poder darle permiso al editor desde unity hacer cambios y cambiar el valor cuando desee. La variable speed es para el movimiento WASD del jugador y la de rotacion es para el moviemiento de la camara, el valor seria la sensibilidad, entre mas alta mas rapida y mas baja pues mas lento.

<div align="center">
  <img src="https://github.com/user-attachments/assets/11c205d5-325f-40b7-ba6b-a5ffbec95e9a" width="50%" />
  <p><i>Paso 6: Forward Movement</i></p>
</div>

Otro script que se habia creado en clase fue el fowardMovement. Esta variable funcionaba para al objeto que se le aplicara una vez realizada la opcion que lo active esto simplemente iba a seguir hacia adelante. Tambien estaba en SerializedField para poder editarlo desde unity cambiando el valor el cual seria el speed para la velocidad en el que ese objeto se fuera a mover hacia adelante. Despues de esto se realizo el PlayerShooting junto con el Bullet y el ShootPoint.

## Proceso de Player Shooting

<div align="center">
  <img src="https://github.com/user-attachments/assets/cbc1c809-d77e-44bb-bf26-993125deb211" <img width="50%"/>
  <p><i>Paso 1: Creacion de Bullet.</i></p>
</div>

Para comenzar con el sistema de disparo del jugador (Player Shooting), primero se creó la bala. Para esto, se fue al menú GameObject, se seleccionó el 3D Object  "Sphere" y se posicionó correctamente frente a la pistola del jugador. Luego, se ajustó su tamaño para que tuviera la apariencia de una bala.

<div align="center">
  <img src="https://github.com/user-attachments/assets/32135746-f42b-473e-8d3a-59f682c0bc8f" <img width="50%"/>
  <img src="https://github.com/user-attachments/assets/736b1660-64dd-4157-8984-f38db08fddc8" <img width="50%" />
  <p><i>Paso 2: Prefab y Shooting Point</i></p>
</div>

Una vez creada la bala, se convirtió en un Prefab arrastrándola desde la jerarquía hacia la carpeta de Assets. A este prefab se le aplicó un color rojo. luego, se creó un objeto vacío (Empty GameObject) llamado “ShootingPoint”, que se utiliza como punto de origen del disparo. Es decir, cada vez que el jugador dispara, el sistema crea una instancia del prefab de la bala en la posición y dirección del ShootingPoint. El prefab es esencial, ya que el sistema de disparo del jugador depende de él para poder instanciar la bala cada vez que se presione el botón de disparo.

<div align="center">
  <img <img src="https://github.com/user-attachments/assets/d63c7803-4ca0-46a4-8ad0-59c1a1dbe455" <img width="50%" />
  <p><i>Paso 3: Creación del Script</i></p>
</div>

Después de tener el prefab de la bala, se creó el script que controlará el disparo del jugador.
Para esto, se seleccionó el objeto Player, se presionó “Add Component” y luego “New Script”, asignándole el nombre PlayerShooting.

<div align="center">
  <img src="https://github.com/user-attachments/assets/d01194a9-6700-4577-963d-cdbc6617235f" <img width="50%" />
  <p><i>Paso 4: Player Shooting (primer metodo)</i></p>
</div>

Dentro del script PlayerShooting, se declararon dos variables públicas llamadas prefab y shootPoint, las cuales permiten establecer en el editor de Unity cuál será el objeto que se disparará (el prefab) y desde qué punto del jugador saldrá el disparo (el ShootPoint). Para programar el funcionamiento inicial del sistema de disparo, se utilizó un if statement el cual verificaba si el jugador hacía left click, utilizando la instrucción Input.GetKeyDown(KeyCode.Mouse0). Al el jugador hacer left click, el script creaba una copia del prefab de la bala mediante la función Instantiate(prefab) y le asignaba la misma posición y rotación del objeto ShootPoint, asegurando que la bala saliera desde la pistola y en la dirección correcta. Este primer método cumplía correctamente la función de disparar proyectiles, aunque utilizaba el sistema antiguo de entrada de Unity, conocido como Input System clásico, el cual fue posteriormente reemplazado por el nuevo sistema de unity.

<div align="center">
  <img src="https://github.com/user-attachments/assets/a5bde2e6-b01f-4f06-b9a6-1620619af2ab" <img width="50%"  />
  <p><i>Paso 5: AutoDestroy</i></p>
</div>

Luego de implementar el primer método, se creó un nuevo script llamado AutoDestroy, el cual se aplicó al prefab de la bala. Este script tiene la función de destruir automáticamente la bala después de un tiempo determinado (delay), evitando que las balas se acumulen en la escena.

<div align="center">
  <img src="https://github.com/user-attachments/assets/6e385816-3510-4c72-82f4-7f3d5cb195d4" <img width="50%" />
  <p><i>Paso 6: Player Shooting (segundo método)</i></p>
</div>

Después de probar el primer método en clase, se implementó una versión más moderna del Player Shooting, utilizando el nuevo Input System de Unity.
Para configurarlo, se fue a Edit, Project Settings, Player y luego a la opción “Active Input Handling”,en donde se seleccionó “Input System Package (New)”.
Después, en el script PlayerShooting, se añadió la línea "using UnityEngine.InputSystem" en la parte de arriba del script, lo que permite usar las nuevas herramientas del sistema de entrada de unity.

<div align="center">
  <img src="https://github.com/user-attachments/assets/b8331f01-b7a0-49c7-93ae-547e2d027b70"  <img width="50%"  />
  <p><i>Paso 7: Player Shooting (Continuación del segundo método)</i></p>
</div>

Por último, se creó la función OnFire(), la cual contiene un if statement, que al detectar que el jugador presiona el botón de disparo, instancia una nueva bala en la posición y rotación del ShootingPoint, de forma muy similar al método anterior. En resumen, el nuevo método realiza la misma acción que el anterior, pero utiliza las funciones del nuevo sistema de entrada de Unity.

## Proceso de Jump

## Proceso de Shift 

## Experiencia ganada

Debbimar - "Lo mas que me gusto de esta tarea y trabajo en clase fue el visual scripting, aunque prefiero escribir codigo a tener que bregar con esos conectores pienso que fue bien interesante y "cool". Aunque entre mas acciones el diagrama es mas grande y grande que apenas se puede ver completo sigue siendo una forma de programar (en bloque) para un videojuego. Realmente es entretenido bregar con los conectores pero vuelvo y repito, prefiero el codigo porque lo siento mas directo y limpio y si tando "rodeo" ya que en programacion con bloque hay que estar pendiente a las lineas y que los conectores esten conectados a donde deben."

Jonlier -

Jeremy -
