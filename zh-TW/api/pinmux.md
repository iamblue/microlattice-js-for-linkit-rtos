# Pinmux


| API | description |
| --- | --- |
| __pimux | Help you to set pinmux. |

# Native binding API 


### __pinmux

* Content

``` js
  __pinmux(
    pin, // number
    function mode    // nubmer
  )

```

* Example

``` js
  pinmux(35, 8); // change pin35 to 8 function mode (GPIO).
```