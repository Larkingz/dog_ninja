# dog_ninja

### Overview for Charactor Template
`Charactor_Template` is an abstract class that provides a framework for characters with basic properties like position and speed.


### Fields
- `protected int x`: x-coordinate of the character.
- `protected int y`: y-coordinate of the character.
- `protected int speed`: Speed of the character.

### Abstract Methods
- `void setX(int x)`: Sets x-coordinate.
- `void setY(int y)`: Sets y-coordinate.
- `void setSpeed(int speed)`: Sets speed.
- `int getX()`: Returns x-coordinate.
- `int getY()`: Returns y-coordinate.
- `int getSpeed()`: Returns speed.

### Overview for Method Template
The `Method_Template` interface defines a contract for character objects that require movement functionality. Classes implementing this interface must provide an implementation for the `move` method.

### Interface: `Method_Template`

#### Methods
- **`void move(JPanel page)`**: An abstract method that specifies how the character or environment object should move within a given `JPanel`.

### Overview for Dog
The `Dog` class extends `Charactor_Template` and implements `Method_Template`. It defines specific properties and behaviors for a dog character, including health, movement, and image rendering.

### Class: `Dog`

#### Fields
- **`private int health`**: Health of the dog, initialized to 180.
- **`private int speed`**: Jump height/speed, initialized to 120.

#### Constructor
- **`Dog(int x, int y)`**: Initializes the dog’s position using `x` and `y` coordinates.

#### Methods
- **`void setX(int x)`**: Sets the x-coordinate.
- **`void setY(int y)`**: Sets the y-coordinate.
- **`int getX()`**: Returns the x-coordinate.
- **`int getY()`**: Returns the y-coordinate.
- **`void setHealth(int health)`**: Sets the health value.
- **`int getHealth()`**: Returns the health value.
- **`int getSpeed()`**: Returns the speed (jump height).
- **`void setSpeed(int speed)`**: Sets the speed (jump height).

#### Movement
- **`void move(JPanel page)`**: Calls `jump()` to make the dog jump.
- **`void jump(JPanel page)`**: Simulates a jump by moving the dog upward and then falling back after a delay, using a `Timer`.

#### Image Rendering
- **`BufferedImage getImage()`**: Loads and returns the image of the dog from `img/dog.png`.


### Overview for Environment
The `Environment` class extends `Charactor_Template` and implements `Method_Template`. It defines environmental objects like clouds or buildings, each with a type, position, and movement behavior.

### Class: `Environment`

#### Static Constants
- **`CLOUD`**: Integer constant for cloud type (0).
- **`BUILDING`**: Integer constant for building type (1).

#### Fields
- **`private int startX`**: Initial x-coordinate of the environment object.
- **`private int speed`**: Speed at which the object moves.
- **`private int eType`**: Type of the environment object (cloud or building).
- **`private Timer timeMove`**: Timer to manage continuous movement.

#### Constructor
- **`Environment(int x, int y, JPanel page, int eType, int speed)`**: Initializes the environment object’s position, type, and speed, and starts its movement on the given `JPanel`.

#### Methods
- **`void setX(int x)`**: Sets the x-coordinate.
- **`void setY(int y)`**: Sets the y-coordinate.
- **`int getX()`**: Returns the x-coordinate.
- **`int getY()`**: Returns the y-coordinate.
- **`int getStartX()`**: Returns the initial x-coordinate.
- **`void setStartX(int startX)`**: Sets the initial x-coordinate.
- **`int getSpeed()`**: Returns the speed of the object.
- **`void setSpeed(int speed)`**: Sets the speed of the object.
- **`int geteType()`**: Returns the type of the object.
- **`void seteType(int eType)`**: Sets the type of the object.
- **`Timer getTimeMove()`**: Returns the movement timer.
- **`void setTimeMove(Timer timeMove)`**: Sets the movement timer.

#### Movement
- **`void move(JPanel page)`**: Continuously moves the object left across the panel. If it moves out of view, it resets to the starting x-coordinate. Uses a `Timer` to update movement every 10 milliseconds.
- **`void stop()`**: Stops the movement timer.

#### Image Rendering
- **`String getEvType(int eType)`**: Returns the image file name based on the environment type.
- **`BufferedImage getImage()`**: Loads and returns the image for the environment object from `img/cloud.png` or `img/building.png`.


### Overview for wave
The `Wave` class extends `Charactor_Template` and implements `Method_Template`. It represents a wave-like environmental object that moves horizontally across a `JPanel` with a specified speed.

### Class: `Wave`

#### Fields
- **`private int speed`**: Speed at which the wave moves.
- **`private Timer timeMove`**: Timer to manage continuous movement of the wave.

#### Constructor
- **`Wave(int x, int y, int speed, JPanel page)`**: Initializes the wave’s position and speed, and starts its movement on the given `JPanel`.

#### Methods
- **`void setX(int x)`**: Sets the x-coordinate.
- **`void setY(int y)`**: Sets the y-coordinate.
- **`int getX()`**: Returns the x-coordinate.
- **`int getY()`**: Returns the y-coordinate.
- **`int getSpeed()`**: Returns the speed of the wave.
- **`void setSpeed(int speed)`**: Sets the speed of the wave.
- **`Timer getTimeMove()`**: Returns the movement timer.
- **`void setTimeMove(Timer timeMove)`**: Sets the movement timer.

#### Movement
- **`void move(JPanel page)`**: Moves the wave left across the panel. If it moves out of view (x-coordinate ≤ 0), it resets to a new random position off-screen. Uses a `Timer` to update movement at the specified speed.

#### Image Rendering
- **`BufferedImage getImage()`**: Loads and returns the image of the wave from `img/tree.png`.