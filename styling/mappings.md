# Mappings

{% method -%}


Mappings (such as for that like a joystick or motor) go into a single file, called `Mappings`. Every mapping type is organized by category, in the following order:
 * Buttons
 * Joysticks
 * Motors
 * DIO, Analog, or any other port on RoboRIO
 * Pneumatics
 * Other mappings
 
Each section will have a comment with the section name.

*REASONING:*
Time and time again we get to competition and change a motor or a limit switch and have to change it's ID. Time and time again we forget where we stored the ID. Having one file that is always consistently organized allows you to quickly find the mapping you are looking for.

{% sample lang="java" -%}
Mappings will be `public static final` and follow the naming for a constant.

EXAMPLE:
```java
class Mappings {
  //BUTTONS
  public static final int BALL_SHOOT = 0;
  public static final int BALL_LOAD = 1;
  ...

  //JOYSTICKS
  public static final int JOY_LEFT = 4;
  public static final int JOY_RIGHT = 5;
  ...
  
}
```

{% sample lang="cpp" -%}
Mappings will be `const constexpr` and follow the naming for a constant.


It can be located in a `namespace` or `enum class`


Remember to properly forward define constants

EXAMPLE:
```cpp
namespace Mappings {
  //BUTTONS
  const constexpr int BALL_SHOOT = 0;
  const constexpr int BALL_LOAD = 1;
  ...

  //JOYSTICKS
  const constexpr int JOY_LEFT = 4;
  const constexpr int JOY_RIGHT = 5;
  ...
  
}
```


{% endmethod %}