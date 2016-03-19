# https


| API | description |
| --- | --- |
| https | Help you to send the http request. |


# API 


### https
* Content

``` js

/* get api */

https({
  method: 'GET' // string
  url:    // string
  header: // string, default please set: '\r\n'
}, function(data) {
  // callback function
});

/* post api */

https({
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
    url: 'https://apis.map.qq.com/ws/location/v1/ip?ip=61.135.17.68&key=6MABZ-VFKAF-DITJ6-JRPZN-OUOFJ-ULBWQ',
    header: '\r\n',
  };

  http(config, function(data) {
    print(data);
    var i = JSON.parse(data);
    print('status:' + i.status);
  });

/* post api */
  var data = { a: 123 };
  var config = {
    url: "https://",
    method: "POST",
    header: "deviceKey:123123\r\n";,
    contentType: "application/json",
    data: JSON.stringify(data),
  }

  http(config, function(data) {
    print('data: '+ data);
  });

```