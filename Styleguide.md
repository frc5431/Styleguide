We need to establish a coding standard, so all of our code looks the same. This will be an extensive document, and will talk about things you don't know yet. If you don't know what a certain clause refers to, then you can ignore it for now.

#Standards

To make this more entertaining, there will be a variety of comics spread throughout this page.



#Team 5431 Coding Standard
##Naming Scheme


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

