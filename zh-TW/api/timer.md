# Timer


| API | description |
| --- | --- |
| __loop | Help you to build loop function easily. |
| setTimeout | Javascript setTimeout api |
| setInterval | Javascript setInterval api. |


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
  __loop(function() {
    print(123);
  }, 2000);

```

### setTimeout

* Example 

``` js
__pinmux(35, 8);

var status = 0;

setTimeout(function(){
  __gpioWrite(35, status);
  if (status === 0 ) {
    status = 1;
  } else {
    status = 0;
  }
}, 2000);


```

### setInterval

* Example 

``` js

__pinmux(35, 8);

var status = 0;

setInterval(function(){
  __gpioWrite(35, status);
  if (status === 0 ) {
    status = 1;
  } else {
    status = 0;
  }
}, 2000);

```