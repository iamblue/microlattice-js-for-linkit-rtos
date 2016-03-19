# UDP


| API | description |
| --- | --- |
| udpClient | Help you to connect UDP protocol. |

# API 


### udpClient
* Content

``` js
  udpClient(
    ip,   // string
    port, // number
    connected callback, // callback function
  )

```

* Example

``` js
  udpClient('52.77.236.179', 443, function(data) {
    // callback
  });

```