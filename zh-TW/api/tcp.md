# TCP


| API | description |
| --- | --- |
| __tcpClient | Help you to connect TCP. |

# Native binding API  


### __tcpClient
* Content

``` js
  __tcpClient(
    ip,   // string
    port, // number
    connected callback, // callback function
  )

```

* Example

``` js
  tcpClient('52.77.236.179', 443, function(data) {
    // callback
  });

```