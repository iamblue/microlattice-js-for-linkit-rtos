# TCP


| API | description |
| --- | --- |
| tcpClient | Help you to connect TCP. |

# API 


### tcpClient
* Content

``` js
  tcpClient(
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