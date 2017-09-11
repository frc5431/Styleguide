{% method -%}

Names shouldn't be too long. If they come out to be huge, use an appropriate acronym, or more preferably, find a way to make it shorter. If you can't make it shorter and keep the original meaning, comment its actual purpose.

{% common %}
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

{% endmethod %}