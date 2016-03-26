# UDP


| API | description |
| --- | --- |
| udpClient | Help you to connect UDP protocol. |

# Native binding API 


### udpClient
* Content

``` js
  __udpClient(
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