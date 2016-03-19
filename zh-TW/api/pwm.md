# PWM


| API | description |
| --- | --- |
| pwmRegister | Help you to regist a pwm. |
| pwmWrite | Help you to write your PWM data. |
| pwmRead | Help you to read your PWM data. |

# Required
* ml-pinmux

# API 


### pwmRegister
* Content

``` js

pwmRegister(
  pin,      // number
  mode,     // number
  frequency // number
)

/*
mode:
  * HAL_PWM_CLOCK_32KHZ = 0
  * HAL_PWM_CLOCK_2MHZ  = 1
  * HAL_PWM_CLOCK_20MHZ = 2
  * HAL_PWM_CLOCK_26MHZ = 3
  * HAL_PWM_CLOCK_40MHZ = 4
  * HAL_PWM_CLOCK_52MHZ = 5
*/

```

### pwmWrite
* Content

``` js
pwmWrite(
  pin,   // number
  value  // number
)
```

### pwmRead
* Content

``` js
pwmRead(
  pin,   // number
  mode   // 0: value, 1: frequency
)
```

## Example
``` js

// ** Hint ** GPIO_31 and PWM_32 is a same physical pin.

/* Write example */

pinmux(31, 9);  // Change GPIO_31 pin to pwm mode
pwmRegister(32, 4, 400000);  // Regist PWM_32 to 4 MHZ mode, and frequency is 400000.

var value = 0;
timer(function() {
  pwmWrite(32, value);  // write signal
  value++;
  if (value === 10) {
    value = 0;
  }
}, 10);

```
