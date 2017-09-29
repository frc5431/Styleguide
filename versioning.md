### Versioning

{% method -%}

In the `Robot` file, add a `public static final String` constant with the name of `ROBOT_VERSION`. Whenever you make a major change to the robot, update this to the date you edited it plus a major feature of this build.

In your initialization code, either print it out to console or put it on Network Tables.

{% sample lang="java" -%}
EXAMPLE:
```java
public static final ROBOT_VERSION = "8/21/2017 - 10 gear autonomous"
```

Then, in `robotInit()`, add the following line:

```java
System.out.println(ROBOT_VERSION);
```

{% sample lang="cpp" -%}
This can be a `#define` or constant

EXAMPLE:
```cpp
const constexpr std::string ROBOT_VERSION = "8/21/2017 - 10 gear autonomous"
```

Then, in `robotInit()`, add the following line:

```cpp
std::cout << ROBOT_VERSION;
```

{% endmethod %}