# Challenge 05 - Let's go ahead and jump!

## Integrantes del equipo
- Debbimar Díaz Santiago
- Jonlier Díaz Rivera
- Jeremy Curry Romero

## Reglas del juego
Este reto esta basado en hacer un script de c# el cual permita que el robot pueda brincar. Y por otra parte, explicar el proceso de como se realizaron los diferentes mappings como shoot, horizontal/vertical movement,etc.

## Proceso de WASD

<div align="center">
  <img src="https://github.com/user-attachments/assets/dc49dfee-2424-456a-b5cf-2864487b35c2" <img width="500" height="200"/>
  <p><i>Paso 1: Scripts.</i></p>
</div>

El movimiento del jugador con WASD se realizo en clase al igual que la accion de Shooting. Lo primero que se hacia era crear un script, este se lograba yendo a algun objeto, se seleccionaba "add component" luego "new script" y ahi se le nombraba segun su funcion y se guardaba en el folder creado para scripts en assets. Estos son los scripts que se hicieron en clase.


<div align="center">
  <img src="https://github.com/user-attachments/assets/3092d419-8a97-4dcf-929a-04197ce7f2e2" <img width="592" height="187" />
  <p><i>Paso 2: Player movement update.</i></p>
</div>

Al inicio de clase se habia hecho el movimiento WASD del jugar junto con las flechas con el input viejo. En la imagen el codigo comentado es el old input. Tambien se realizo con los circuitos o mejor dicho los visualScripting con el graph (Imagen siguiente). Al final tuvimos que ir en unity a "edit" luego a "project setting" y cambiar del imput viejo al nuevo. Para esto se tuvo que agregar la libreria de UnityEngine.InputSystem y se agrego una linea de codigo para lo del deltaTime.


<div align="center">
  <img src="https://github.com/user-attachments/assets/28035dd1-9873-4ed3-b582-8e0e897acfcf" <img width="592" height="187" />
  <p><i>Paso 2: (Old input)</i></p>
</div>

Este es el VisualScripting para el input viejo de movimiento de jugador con WASD. Este se logro yendo a "add component"  despues a VisualScripting y graph. Una vez dentro era cuestion de darle a new node y se agregaba la funcion que se necesitaba para lograr la accion deseada.

<div align="center">
  <img src="https://github.com/user-attachments/assets/f73e3708-c5b7-4336-8e64-adf78a310d1d" <img width="592" height="187" />
  <p><i>Paso 3: Input</i></p>
</div>

Volviendo al movimiento de jugador, se deshabilito el inout viejo en los settings y se coloco el nuevo y el codigo se reemplazo. Pero para lograr esto habia que bajar en package manager en unity el Input System manager. Una vez se instalo pues se iba a "add component" y se le daba a action.

<div align="center">
  <img src="https://github.com/user-attachments/assets/2012515b-da59-48a1-acb7-6181ed0cecbf"  <img width="592" height="187" />
  <p><i>Paso 3: (Input SysMap)</i></p>
</div>

Una vez ahi, se le coloco de nombre InputSysMap01 y es una herramienta que sirve para facilitar ese link de la accion que quiere realizar el jugador en el juego.

<div align="center">
  <img src="https://github.com/user-attachments/assets/5fb95c10-da71-4e86-9d2b-8f5379aa297c" <img width="592" height="187" />
  <p><i>Paso 4: Look player movement</i></p>
</div>

Al finalizar el movimiento WASD pues nos movemos a el movimiento de la pantalla o camara. Al inicio en la clase tambien se habia realizado el mismo con el input viejo y se habia hecho un visual scripting tambien. Pero aqui en la imagen podemos ver el codigo para el input nuevo y tambien una funcion awake que sirve para que el mouse desaparezca dentro del recuadro de imagen mientras se este moviendo la camara. Algo que hay que agregar es que con el input nuevo, el cambio mas grande que hubo en el codigo es el tener que agregar una variable Vector 2 que este tiene los ejes de X y Y entonces el lookValue es de tipo float porque asi el sistema reconoce el movimiento con el valor positivo a un lado y con el negativo hacia a otro.

<div align="center">
  <img src="https://github.com/user-attachments/assets/2d336053-fa9e-4466-9945-0ed02d9a30e4"  <img width="592" height="187" />
  <p><i>Paso 5: Speed y Rotation</i></p>
</div>

Las variables de speed y rotationSpeed se encuentran privadas pero en un Serialized Field es para poder darle permiso al editor desde unity hacer cambios y cambiar el valor cuando desee. La variable speed es para el movimiento WASD del jugador y la de rotacion es para el moviemiento de la camara, el valor seria la sensibilidad, entre mas alta mas rapida y mas baja pues mas lento.

<div align="center">
  <img src="https://github.com/user-attachments/assets/11c205d5-325f-40b7-ba6b-a5ffbec95e9a" <img width="600" height="200"  />
  <p><i>Paso 6: Forward Movement</i></p>
</div>

Otro script que se habia creado en clase fue el fowardMovement. Esta variable funcionaba para al objeto que se le aplicara una vez realizada la opcion que lo active esto simplemente iba a seguir hacia adelante. Tambien estaba en SerializedField para poder editarlo desde unity cambiando el valor el cual seria el speed para la velocidad en el que ese objeto se fuera a mover hacia adelante. Despues de esto se realizo el PlayerShooting junto con el Bullet y el ShootPoint.

## Proceso de Player Shooting

## Proceso de Jump

## Proceso de Shift 

## Experiencia ganada

Debbimar - "Lo mas que me gusto de esta tarea y trabajo en clase fue el visual scripting, aunque prefiero escribir codigo a tener que bregar con esos conectores pienso que fue bien interesante y "cool". Aunque entre mas acciones el diagrama es mas grande y grande que apenas se puede ver completo sigue siendo una forma de programar (en bloque) para un videojuego. Realmente es entretenido bregar con los conectores pero vuelvo y repito, prefiero el codigo porque lo siento mas directo y limpio y si tando "rodeo" ya que en programacion con bloque hay que estar pendiente a las lineas y que los conectores esten conectados a donde deben."

Jonlier -

Jeremy -
