# GPIO


| API | description |
| --- | --- |
| __gpioRead | Help you to read your GPIO data. |
| __gpioWrite | Help you to write your GPIO data. |

# Required
* ml-pinmux

# Native binding API 


### __gpioRead
* Content

``` js
__gpioRead(
  pin, // nubmer
  method, // string, pullup or pulldown
)
```

* Example

``` js
  __pinmux(35, 8); // Just once declared
  __gpioRead(35, 'pulldown'); // read pin35, pulldown method
```


### __gpioWrite
* Content

``` js
__gpioWrite(
  pin, // nubmer
  value, // number
)
```

* Example

``` js
  __pinmux(35, 8); // Just once declared
  __gpioWrite(35, 0);
```