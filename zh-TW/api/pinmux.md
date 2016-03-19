# Pinmux


| API | description |
| --- | --- |
| pimux | Help you to set pinmux. |

# API 


### pinmux

* Content

``` js
  pinmux(
    pin, // number
    function mode    // nubmer
  )

```

* Example

``` js
  pinmux(35, 8); // change pin35 to 8 function mode (GPIO).
```