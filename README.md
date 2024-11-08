# dog_ninja
## Charactor Package

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