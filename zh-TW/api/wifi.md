# Wifi


| API | description |
| --- | --- |
| wifi | Help you to set wifi mode. |

# API 


### wifi

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