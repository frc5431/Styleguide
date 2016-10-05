We need to establish a coding standard, so all of our code looks the same. This will be an extensive document, and will talk about things you don't know yet. If you don't know what a certain clause refers to, then you can ignore it for now.

#Standards

To make this more entertaining, there will be a variety of comics spread throughout this page.
![](https://imgs.xkcd.com/comics/standards.png)


#Team 5431 Coding Standard
##Naming Scheme

![](http://www.commitstrip.com/wp-content/uploads/2016/09/Strip-Le-stagiaire-et-la-variable-english650-final.jpg)

You will use camelCase for names of functions and variables, which means no underscores, and every word but the first is capitalized.

BAD:
```
int ThisIsAVariable
int this_is_a_variable
int thisisavariable
int thIsiSaVariABLE
```
GOOD:
```
int thisIsAVariable
```

Names should be descriptive, and explain their purpose.

BAD:
```
int foo
int blah
int poop
int woawver
```
GOOD:
```
int pidControllerState
int currentTime
int keyIterator
```

Names shouldn't be too long. If they come out to be huge, use an appropriate acronym, or more preferably, find a way to make it shorter. If you can't make it shorter and keep the original meaning, comment its actual purpose.

BAD:
```
int thisVariableControlsThePIDControllerInAutonomousModeForShooting
```
GOOD:
```
//controls the pid for auton to shoot
int autonPIDShooting
```
And less preferable:
```
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

##Whitespace
![](https://imgs.xkcd.com/comics/third_way.png)
This is a constant dispute throughout programmming. We will lay down the law right here right now.
###Tabs vs Spaces
We will use tabs.

###Brackets

When typing anything that requires curly brackets (conditionals, loops, functions, classes, etc), the first bracket goes on the same line as the definition.
BAD:
```
void wombatEater()
{

void wombatEater()




{
```
GOOD:
```
void wombatEater(){
```

The second curly bracket will have its own line after the last line of the function

BAD:
```
void wombatEater(){foo();}
void wombatEater(){
foo();}
```
GOOD:
```
void wombatEater(){
  foo();
}
```
Each time an opening curly bracket is encountered, indent by an extra tabs.

EXAMPLE:
```
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
```
namespace foo{
  void blah();
}
```
GOOD:
```
namespace foo{
void blah();
}
```

###Else-if Whitespace
![](https://imgs.xkcd.com/comics/code_quality.png)

If you have an else-if the closing bracket and the else goes on the same line

BAD:
```
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
```
}else if(){

}else{
```
###Long lines
Lines should not be unreasonably long. Use common sense to determine how long a line is. If it is too long, add new lines in between, and indent to be the same indentation level. This is also true with function arguments.

BAD:
```
int longVariable = gatherAshes(foo().wombat.consume()->digest().intestines->explode()).throwAt(blah).retrieveVariable().finally().almostThere().thereWeAre
```
GOOD:
```
int longVariable = gatherAshes(
                  foo().wombat.consume()
                  ->digest().intestines
                  ->explode()).throwAt(blah)
                  .retrieveVariable().finally()
                  .almostThere().thereWeAre);
```

##Classes
###Visiblity
![](https://imgs.xkcd.com/comics/code_quality_2.png)

When declaring a visiblity in a class, you dont need to indent further.
BAD:
```
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
```
class foo{
public:
  bar();
}
```
###Struct vs Class
Structs should be used for Plain Old Data (POD), or when the type simply acts as a container for variables.


###Operators and Math operations
This covers what you should do when you want to do math or streams or variable assignments
BAD:
```
std::cout<<"asd"<<1<<"foo"<<std::endl;
int a=(1+b/(s+2));
```

GOOD:
```
std::cout << "Good boy: " << 30 << " Nice..." << std::endl;
int a = (1 + b / (s + 2) );
```

###Newline and escape characters
Please use the builtin escapes via std
BAD:
```
std::cout << "Yay\n\n";
```

GOOD:
```
std::cout << "Yay" << std::endl << std::endl;
```
