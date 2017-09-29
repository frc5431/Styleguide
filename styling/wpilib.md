# WPILib

{% method -%}

## Which Robot subclass to use?

Use `IterativeRobot`

*REASONING:*
We have been using that for 2 years and it has proven us well. Don't change it if it ain't broke.

{% endmethod %}

{% method -%}

`Robot` class functions will be in this order:
 * robotInit()
 * robotPeriodic()
 * autonomousInit()
 * autonomousPeriodic()
 * teleopInit()
 * teleopPeriodic()
 * disabledInit()
 * disabledPeriodic()
 
*REASONING:*
This order is based on the when the function is called during an FRC match combined with common usage. `robotInit()` is always called first, then `autonomousInit()`, then `teleopInit()`. `disabled` is at the end because it is rarely used and not as important as the other functions.

{% endmethod -%}

{% method -%}

The `Robot` class should have as minimal code as possible. All implementation should be left to other files.

*REASONING:*
Organizational sake. If you want fix a bug on the shooter for example, you would want to look in `Shooter` instead of parsing `Robot`.

{% endmethod %}