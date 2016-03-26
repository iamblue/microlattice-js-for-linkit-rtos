# http


| API | description |
| --- | --- |
| __http | Help you to send the http request. |


# Native binding API 


### __http
* Content

``` js

/* get api */

__http({
  method: 'GET' // string
  url:    // string
  header: // string, default please set: '\r\n'
}, function(data) {
  // callback function
});

/* post api */

__http({
  url: // string,
  method: 'POST' // string,
  header: // string, default please set: '\r\n'
  contentType: // string,
  data: // string, please sent json format
}, function(data) {
  // callback function
});

```

* Example


``` js

/* get api */
  var config = {
    method: 'GET',
    url: 'http://apis.map.qq.com/ws/location/v1/ip?ip=61.135.17.68&key=6MABZ-VFKAF-DITJ6-JRPZN-OUOFJ-ULBWQ',
    header: '\r\n',
  };

  __http(config, function(data) {
    print(data);
    var i = JSON.parse(data);
    print('status:' + i.status);
  });

/* post api */
  var data = { a: 123 };
  var config = {
    url: "http://",
    method: "POST",
    header: "deviceKey:123123\r\n";,
    contentType: "application/json",
    data: JSON.stringify(data),
  }

  __http(config, function(data) {
    print('data: '+ data);
  });

```