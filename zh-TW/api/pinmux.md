# Timer


| API | description |
| --- | --- |
| pimux | Help you to set pinmux. |

# API 


### pinmux

* Content

``` js
  timer(
    function, // function
    ms,    // nubmer
  )

```

* Example

``` js
  // every 2s , loop `print(123);` function
  timer(function() {
    print(123);
  }, 2000);

```