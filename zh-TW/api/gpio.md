# GPIO


| API | description |
| --- | --- |
| gpioRead | Help you to read your GPIO data. |
| gpioWrite | Help you to write your GPIO data. |

# Required
* ml-pinmux

# API 


### gpioRead
* Content

``` js
gpioRead(
  pin, // nubmer
  method, // string, pullup or pulldown
)
```

* Example

``` js
  pinmux(35, 8); // Just once declared
  gpioRead(35, 'pulldown'); // read pin35, pulldown method
```


### gpioWrite
* Content

``` js
gpioWrite(
  pin, // nubmer
  value, // number
)
```

* Example

``` js
  pinmux(35, 8); // Just once declared
  gpioWrite(35, 0);
```