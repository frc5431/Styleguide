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

EXAMPLE:
```java
namespace Mappings {
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


{% endmethod %}