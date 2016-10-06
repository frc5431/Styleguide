We need to establish a coding standard, so all of our code looks the same. This will be an extensive document, and will talk about things you don't know yet. If you don't know what a certain clause refers to, then you can ignore it for now.

#Standards

To make this more entertaining, there will be a variety of comics spread throughout this page.
![](https://imgs.xkcd.com/comics/standards.png)


![](http://www.commitstrip.com/wp-content/uploads/2016/09/Strip-Le-stagiaire-et-la-variable-english650-final.jpg)

You will use camelCase for names of functions and variables, which means no underscores, and every word but the first is capitalized.

BAD:
```C++
int ThisIsAVariable
int this_is_a_variable
int thisisavariable
int thIsiSaVariABLE
```
GOOD:
```C++
int thisIsAVariable
```

Names should be descriptive, and explain their purpose.

BAD:
```C++
int foo
int blah
int poop
int woawver
```
GOOD:
```C++
int pidControllerState
int currentTime
int keyIterator
```

Names shouldn't be too long. If they come out to be huge, use an appropriate acronym, or more preferably, find a way to make it shorter. If you can't make it shorter and keep the original meaning, comment its actual purpose.

BAD:
```C++
int thisVariableControlsThePIDControllerInAutonomousModeForShooting
```
GOOD:
```C++
//controls the pid for auton to shoot
int autonPIDShooting
```
And less preferable:
```C++
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
###Tabs vs Spaces
We will use tabs.

###Brackets

When typing anything that requires curly brackets (conditionals, loops, functions, classes, etc), the first bracket goes on the same line as the definition.
BAD:
```C++
void wombatEater()
{

void wombatEater()




{
```
GOOD:
```C++
void wombatEater(){
```

The second curly bracket will have its own line after the last line of the function

BAD:
```C++
void wombatEater(){foo();}
void wombatEater(){
foo();}
```
GOOD:
```C++
void wombatEater(){
  foo();
}
```
Each time an opening curly bracket is encountered, indent by an extra tabs.

EXAMPLE:
```C++
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

The only time you don't indent is when you have a namespace.

BAD:
```C++
namespace foo{
  void blah();
}
```
GOOD:
```C++
namespace foo{
void blah();
}
```

###Else-if Whitespace
![](https://imgs.xkcd.com/comics/code_quality.png)

If you have an else-if the closing bracket and the else goes on the same line

BAD:
```C++
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
```C++
}else if(){

}else{
```
###Long lines
Lines should not be unreasonably long. Use common sense to determine how long a line is. If it is too long, add new lines in between, and indent to be the same indentation level. This is also true with function arguments.

BAD:
```C++
int longVariable = gatherAshes(foo().wombat.consume()->digest().intestines->explode()).throwAt(blah).retrieveVariable().finally().almostThere().thereWeAre
```
GOOD:
```C++
int longVariable = gatherAshes(
                  foo().wombat.consume()
                  ->digest().intestines
                  ->explode()).throwAt(blah)
                  .retrieveVariable().finally()
                  .almostThere().thereWeAre);
```

###Visiblity
![](https://imgs.xkcd.com/comics/code_quality_2.png)

When declaring a visiblity in a class, you dont need to indent further.
BAD:
```C++
class foo{
  public:
  bar();
}

class foo{
  public:
    bar();
}
```
GOOD:
```C++
class foo{
public:
  bar();
}
```

###Struct vs Class
Structs should be used for Plain Old Data (POD), or when the type simply acts as a container for variables.
Structs were mainly made to just store data and maybe manipulate it slighty. They were not made to have complex
functions and operations. Yet the naming should be the same as a class camel cased first letter caps. <br>

BAD:
```C++
struct datatype {
 int foo = 0;

 void operand() {
  visionprocessing();
  fibSequence();
  return &(void*);
 }

};
```
GOOD:
```C++
struct DataType {
  int bodyType = 1;
  std::string hoseType = "What hose?";
  float harambeShot = 3.145807; //5807 = SHOT
};
```

###Operators and Math operations
Put spaces between all operators and math operations so it doesn't look like a bunch of
pointer references. <br>
BAD:
```C++
std::cout<<"asd"<<1<<"foo"<<std::endl;
int a=(1+b/(s+2));
```

GOOD:
```C++
std::cout << "Good boy: " << 30 << " Nice..." << std::endl;
int a = (1 + b / (s + 2) );
```

###Newline and escape characters
Please use the builtin escapes via std<br>

BAD:
```C++
std::cout << "Yay\n\n";
```

GOOD:
```C++
std::cout << "Yay" << std::endl << std::endl;
```

EXCEPTION:<br>

std::endl flushes the output stream. If you don't want to flush, use \n.
Create a define when using it since some systems use \r\n (As they do in html)


###Headings and imports
Make sure to separate headers by category, you should also keep proper spacing between all of
the categories that's consistent

BAD:
```C++
#include <iostream>

#include <cmath>
#include "local.hpp"
#include <string>
using namespace std;
```

GOOD:
```C++
#include <iostream>
#include <string>
#include <arrays>

#include <cmath>
#include <anothermath>

#include "local.hpp"

using namespace std;
```

###Comments
Comments can get hazy and a little more hazy depending on the program you are using. We would really
appreciate it if all coders follow these standards for commenting code. We will dedicate one person as
the code documenter and manager. To make sure the current code follows all of these standards.

First things first are single line comments. **Please don't put pointless comments**
When we mean pointless comments we mean comments that are obviouslt explaining nothing and is already
viewable by the code itself no explanation, such as these. <br>
BAD:
```C++
int first = 1; //Sets first to one
int second = 2; //Sets second to two

int combined = first + second; //Adds first and second together
```
Those comments just take up space, aren't funny and just bother the reader because it's quite obvious
what the coder is doing. It's okay to put comments right above the line of code you want to comment, if 
you feel as if it's more readable <br>
GOOD:
```C++
int motorPortOne = 123; //Check mapping on robot left motor is on CAN line 123
int motrPortTwo = 543; //Same as above, mapped to right motor

//Show users that motors have been initialized
std::cout << motorPortOne << "\n" << motorPortTwo << std::endl;
```

Multiline comments are mainly used for functions, classes, structs, really important stuff and beginning
of files.
EXAMPLE: <br>
```C++
/*
 * Beginning of file text
 * Created by Robotics Programming
 */
 
 
/*
 * This class handles basic motor control
 * And movement, mapping -1 - 0 - 1 to a raw value
 */
class Motor {
public:

  /*
   * Sets the premapped motor values to a common
   * One between (Description provided by class)
   * Careful for explosion of function
   * No errror handling
   */
  void setMotorSpeed(int newSpeed);
}
```

Licensing and Credit. People do want credit for their own credit and work for their code.
Yet you can't just assume code is yours so Titan Robotics will have their own license that should be
included as a file in every project in the organization as well a small description within each file. <br>
EXAMPLE: <br>
```C++
/* =========================================================================

Program:   Robotics Tools and Kits Toolkit
Module:    mainRobotCode.cpp
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

###Using and typedef
Never type `using namespace`, as it pollutes the global namespace.

The only time you should use `using` is to replace typedef.


###Main code
`main()` should always return 0 if the program executed sucessfully. Specific error codes can be returned.

`main()` should not be too long, and no actual computations should be done there. It must only call functions.
