#Comments

Comments can get hazy and a little more hazy depending on the program you are using. We would really appreciate it if all coders follow these standards for commenting code.

{% method -%}
First things first are single line comments.
**Please don't put pointless comments**
When we mean pointless comments we mean comments that are obviously explaining nothing and is already view able by the code itself no explanation. 
Those comments just take up space, aren't funny and just bother the reader because it's quite obvious
what the coder is doing. It's okay to put comments right above the line of code you want to comment, if 
you feel as if it's more readable.

**EXCEPTION:** The occasional funny joke is allowed, as long as it's not too distracting and replacing actual important comments.

{% common -%}

BAD:
```java
int first = 1; //Sets first to one
int second = 2; //Sets second to two

int combined = first + second; //Adds first and second together
```

{% sample lang="java" -%}

GOOD:
```java
int motorPortOne = 123; //Check mapping on robot left motor is on CAN line 123
int motrPortTwo = 543; //Same as above, mapped to right motor

//Show users that motors have been initialized
System.out.println(motorPortOne + System.lineSeperator() + motorPortTwo);
```

{% sample lang="cpp" -%}

GOOD:
```cpp
int motorPortOne = 123; //Check mapping on robot left motor is on CAN line 123
int motrPortTwo = 543; //Same as above, mapped to right motor

//Show users that motors have been initialized
std::cout << motorPortOne << std::endl << motorPortTwo;
```

{% endmethod %}

{% method -%}

Multiline comments are mainly used for functions, classes, structs, really important stuff and beginning
of files.

Every function you write should have a JavaDoc-like comment documenting:
 * Parameters
 * Return value
 * Exceptions thrown
 * Preconditions/postconditions of params
 * Behavior of function
 
 
 {% sample lang="java" -%}
 
 ```java
/*
 * Beginning of file text
 * Created by Robotics Programming
 */
package org.usfirst.frc.team5431
 
/*
 * This class handles basic motor control
 * And movement, mapping -1 - 0 - 1 to a raw value
 */
public class Motor {
  /*
   * Sets the premapped motor values to a common
   * One between (Description provided by class)
   * Careful for explosion of function
   * No errror handling
   */
  public void setMotorSpeed(int newSpeed){
    ...
  }
}
```

{% sample lang="cpp" -%}

```cpp
/*
 * Beginning of file text
 * Created by Robotics Programming
 */


#include <iostream>
#include <WPILib.h>
 
/*
 * This class handles basic motor control
 * And movement, mapping -1 - 0 - 1 to a raw value
 */
class Motor : public frc::SimpleMotor {
public:
  /*
   * Sets the premapped motor values to a common
   * One between (Description provided by class)
   * Careful for explosion of function
   * No errror handling
   */
  void setMotorSpeed(const int newSpeed){
    ...
  }
}
```



{% endmethod %}