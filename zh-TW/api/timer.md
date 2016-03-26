# Timer


| API | description |
| --- | --- |
| __timer | Help you to build loop function easily. |

# Native binding API  


### __timer

* Content

``` js
  __timer(
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