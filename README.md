We need to establish a coding standard, so all of our code looks the same. This will be an extensive document, and will talk about things you don't know yet. If you don't know what a certain clause refers to, then you can ignore it for now.

# Standards

To make this more entertaining, there will be a variety of comics spread throughout this page.
![](https://imgs.xkcd.com/comics/standards.png)


![](http://www.commitstrip.com/wp-content/uploads/2016/09/Strip-Le-stagiaire-et-la-variable-english650-final.jpg)

You will use camelCase for names of functions and variables, which means no underscores, and every word but the first is capitalized.

BAD:
```java
int ThisIsAVariable
int this_is_a_variable
int thisisavariable
int thIsiSaVariABLE
```
GOOD:
```java
int thisIsAVariable
```

Names should be descriptive, and explain their purpose.

BAD:
```java
int foo
int blah
int poop
int woawver
```
GOOD:
```java
int pidControllerState
int currentTime
int keyIterator
```

Names shouldn't be too long. If they come out to be huge, use an appropriate acronym, or more preferably, find a way to make it shorter. If you can't make it shorter and keep the original meaning, comment its actual purpose.

BAD:
```java
int thisVariableControlsThePIDControllerInAutonomousModeForShooting
```
GOOD:
```java
//controls the pid for auton to shoot
int autonPIDShooting
```
And less preferable:
```java
int APIDSC
```

![](https://imgs.xkcd.com/comics/smfw.png)

Abbreviations should not be used, except for a few special cases. They are as following:

| *Name*         | *Abbreviation* |
|----------------|----------------|
| Interator      | Iter           |
| Implementation | Impl           |
| Variable       | Var            |
| Function       | Func           |
| Teleoperated   | Teleop         |
| Autonomous     | Auton          |
| Practice       | Prac           |
| Number         | Num            |
| Constant       | Const          |
| Utility        | Util           |
| Argument       | Arg            |
| Parameter      | Param          |

Other approved abbreviations are those that are very commonly used, like DNS for Dynamic Name Service, HTTP for HyperText Transfer Protocol, XML for eXtensible Markup Language, JSON for JavaScript Object Notation, etc.

![](https://imgs.xkcd.com/comics/third_way.png)
This is a constant dispute throughout programmming. We will lay down the law right here right now.
### Tabs vs Spaces
We will use tabs.

### Brackets

When typing anything that requires curly brackets (conditionals, loops, functions, classes, etc), the first bracket goes on the same line as the definition.
BAD:
```java
void wombatEater()
{

void wombatEater()




{
```
GOOD:
```java
void wombatEater(){
```

The second curly bracket will have its own line after the last line of the function

BAD:
```java
void wombatEater(){foo();}
void wombatEater(){
foo();}
```
GOOD:
```java
void wombatEater(){
  foo();
}
```
Each time an opening curly bracket is encountered, indent by an extra tab.

EXAMPLE:
```java
int wombatEater(){
  if(blah){
    for(loop){
      bar();
    }
    foo();
  }
  return 1;
}
```

### Else-if Whitespace
![](https://imgs.xkcd.com/comics/code_quality.png)

If you have an else-if the closing bracket and the else goes on the same line

BAD:
```java
}
else{

}else
if(){

}
else
if()
{
```
GOOD:
```java
}else if(){

}else{
```
### Long lines
Lines should not be unreasonably long. Use common sense to determine how long a line is. If it is too long, add new lines in between, and indent to be the same indentation level. This is also true with function arguments. Each level of parenthesis is a new indentation level.

BAD:
```java
int longVariable = gatherAshes(foo().wombat.consume().digest().intestines.explode().throwAt(blah).retrieveVariable().finally().almostThere().thereWeAre());
```
GOOD:
```java
int longVariable = gatherAshes(
                    foo().wombat.consume()
                    .digest().intestines
                    .explode().throwAt(blah)
                    .retrieveVariable().finally()
                    .almostThere().thereWeAre()
                  );
```

### Operators and Math operations
Put spaces between all operators and math operations so it doesn't look like a bunch of jumbled up math.
<br>
BAD:
```java
System.out.println("hello"+Blah.SPACE+"world");
int a=(1+b/(s+2));
```

GOOD:
```java
System.out.println("hello" + Blah.SPACE + "world");
int a = (1 + b / (s + 2));
```

###Newline and escape characters
Instead of `\n`, use System.lineSeperator()<br>

BAD:
```java
System.out.println("Hello!\n");
```

GOOD:
```java
Sysgem.out.println("Hello!" + System.lineSeperator());
```

### Comments
Comments can get hazy and a little more hazy depending on the program you are using. We would really
appreciate it if all coders follow these standards for commenting code. We will dedicate one person as
the code documenter and manager. To make sure the current code follows all of these standards.

First things first are single line comments. **Please don't put pointless comments**
When we mean pointless comments we mean comments that are obviouslt explaining nothing and is already
viewable by the code itself no explanation, such as these. <br>
BAD:
```java
int first = 1; //Sets first to one
int second = 2; //Sets second to two

int combined = first + second; //Adds first and second together
```
Those comments just take up space, aren't funny and just bother the reader because it's quite obvious
what the coder is doing. It's okay to put comments right above the line of code you want to comment, if 
you feel as if it's more readable <br>
GOOD:
```java
int motorPortOne = 123; //Check mapping on robot left motor is on CAN line 123
int motrPortTwo = 543; //Same as above, mapped to right motor

//Show users that motors have been initialized
System.out.println(motorPortOne + System.lineSeperator() + motorPortTwo);
```

Multiline comments are mainly used for functions, classes, structs, really important stuff and beginning
of files.
EXAMPLE: <br>
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
  public void setMotorSpeed(int newSpeed);
}
```

Licensing and Credit. People do want credit for their own credit and work for their code.
Yet you can't just assume code is yours so Titan Robotics will have their own license that should be
included as a file in every project in the organization as well a small description within each file. <br>
EXAMPLE: <br>
```java
/* =========================================================================

Program:   Robotics Tools and Kits Toolkit
Module:    mainRobotCode.java
Creator:   Robotics Programming
Date:      Oct(10). 10, 2016

Copyright (c) Titan Robotics, blah, blah
All rights reserved.
Look at the man standing over there

This software is distributed WITHOUT ANY WARRANTY; without even
the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR
PURPOSE.  See the above copyright notice for more information.

========================================================================= */
```


###Main code
`main()` should always return 0 if the program executed sucessfully. Specific error codes can be returned.

`main()` should not be too long, and no actual computations should be done there. It must only call functions.
