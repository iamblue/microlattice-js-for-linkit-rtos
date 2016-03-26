# PWM


| API | description |
| --- | --- |
| __pwmRegister | Help you to regist a pwm. |
| __pwmWrite | Help you to write your PWM data. |
| __pwmRead | Help you to read your PWM data. |

# Required
* ml-pinmux

# Native binding API 


### __pwmRegister
* Content

``` js

__pwmRegister(
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

### __pwmWrite
* Content

``` js
__pwmWrite(
  pin,   // number
  value  // number
)
```

### __pwmRead
* Content

``` js
__pwmRead(
  pin,   // number
  mode   // 0: value, 1: frequency
)
```

## Example
``` js

// ** Hint ** GPIO_31 and PWM_32 is a same physical pin.

__pinmux(31, 9);  // Change GPIO_31 pin to pwm mode
__pwmRegister(32, 4, 400000);  // Regist PWM_32 to 4 MHZ mode, and frequency is 400000.

var value = 0;
__loop(function() {  // loop function
  __pwmWrite(32, value);  // write signal
  value++;
  if (value === 10) {
    value = 0;
  }
}, 10);

```
