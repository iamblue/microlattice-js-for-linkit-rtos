# Timer


| API | description |
| --- | --- |
| timer | Help you to build loop function easily. |

# API 


### timer

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