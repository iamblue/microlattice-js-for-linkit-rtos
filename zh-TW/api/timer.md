# Timer


| API | description |
| --- | --- |
| __loop | Help you to build loop function easily. |

# Native binding API  


### __loop

* Content

``` js
  __loop(
    function, // function
    ms,    // nubmer
  )

```

* Example

``` js
  // every 2s , loop `print(123);` function
  __timer(function() {
    print(123);
  }, 2000);

```