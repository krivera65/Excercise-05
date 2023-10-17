# Excercise-05

Como parte del quinto ejercicio que se nos asignó utilizando el motor de videojuegos Unity, se estuvieron realizando las acciones OnJump y OnFastMovement en nuestro objeto shooter para controlar los movimientos y saltos de este personaje, tanto en un Script como en un Visual Script.

1.	Música añadida al file de Spotify:

  	Camila:

  	Raúl:

  	Karla: Bliding Lights - The Weeknd
  	
Pasos para llegar a la creación final de estas acciones:

2.	Se creó una matriz de acciones

    Action: Horizontal Movement	
  
          Mapping: A and D keys, Left and Right arrows, gamepad left stick

    Action: Vertical Movement
  	
          Mapping: W and S keys, Left and Right arrows, gamepad left stick

    Action: Shoot
  	
          Mapping: Left click of the mouse

    Action: Jump
  	
          Mapping: Space bar of the keyboard

    Action: Look
  	
          Mapping: Mouse movement

    Action: Fast Movement
  	
          Mapping: Y key 

3.	En este paso se crearon dos acciones adicionales a las que estaban implementadas ya en el script shootermovinput y aquí les dejamos los pasos para crear las mismas:

OnFastMovement (Acción de movimiento rápido):

-	Declaración de la acción: En la parte superior del script, se declara una variable public float fastSpeedMultiplier que representa el multiplicador de velocidad rápida. Este valor se usa para aumentar la velocidad de movimiento cuando se activa la acción "OnFastMovement."

-	Detección de entrada: La acción "OnFastMovement" se activa cuando el jugador realiza una entrada, como presionar una tecla o botón específico en el juego. La detección de entrada se maneja a través de Unity Input System y se configura en el Inspector.

-	Función "OnFastMovement": Cuando se activa la acción "OnFastMovement," se llama a la función public void OnFastMovement().

-	Multiplicación de velocidad: En la función "OnFastMovement," se multiplican los valores de movimiento (movementValue.x y movementValue.y) por el fastSpeedMultiplier. Esto aumenta la velocidad del movimiento del jugador mientras la acción se mantiene activa.

OnJump (Acción de salto):

-	Declaración de la acción: En la parte superior del script, se declara una variable public float jumpForce que representa la fuerza del salto. Esta variable determina cuán alto salta el personaje.

-	Control de saltos: Se utilizan varias variables para controlar el salto:
private bool isJumping: Un indicador que verifica si el personaje está en el aire.
private int jumpsLeft: El número de saltos permitidos (en este caso, 2).
private int jumpsMade: El número de saltos realizados.

-	Detección de entrada: La acción "OnJump" se activa cuando el jugador realiza una entrada, como presionar una tecla o botón específico en el juego. La detección de entrada se maneja a través de Unity Input System y se configura en el Inspector.

-	Función "OnJump": Cuando se activa la acción "OnJump," se llama a la función public void OnJump(InputValue value).

-	Salto inicial: La función "OnJump" primero verifica si quedan saltos disponibles (jumpsLeft > 0) y si el personaje no está actualmente en el aire (!isJumping). Si ambas condiciones son verdaderas, se aplica una fuerza hacia arriba (rb.AddForce(Vector3.up * jumpForce, ForceMode.Impulse)) para realizar el salto.

-	Actualización de estado de salto: Después del salto inicial, se actualiza el estado de salto (isJumping = true) y se reduce el número de saltos disponibles (jumpsLeft--) y se incrementa el número de saltos realizados (jumpsMade++).

-	Salto adicional (doble salto): Si el personaje ya está en el aire, pero no ha alcanzado el límite de saltos (jumpsMade < 2), se reinicia la velocidad vertical y se aplica otra fuerza de salto. Esto permite el doble salto.

-	Restablecimiento de saltos en el suelo: Cuando el personaje toca el suelo (detectado mediante la función "OnCollisionEnter"), se restablece el estado de salto, permitiendo al jugador realizar saltos nuevamente.



4. Correr el programa y mostrar los resultados

 ![GIF 10-17-2023 8-23-37 AM](https://github.com/krivera65/Excercise-05/assets/143332773/918b631b-9aef-4893-ae83-639d7517c3c2)

