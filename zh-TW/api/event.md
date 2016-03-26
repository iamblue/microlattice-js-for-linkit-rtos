# ml-event

## Usage
* Copy this content in your Microlattice.js project.
* `global.eventStatus` is the fixed name, don't change to other name. 

## API
``` js

/* Listening the channel event */
global.eventStatus.on('your channel name', function(data) {
  // handle the data.
});

/* emit the channel event */
global.eventStatus.on('your channel name', 'your data')

```

## Example

``` js

var EventEmitter = require('ml-event').EventEmitter;
var eventStatus = new EventEmitter();
global.eventStatus = eventStatus;

global.eventStatus.on('info', function(data) {
  print(data);  // it will print `hello world` in every 2s.
})

timer(function() {
  global.eventStatus.emit('info', 'hello world!');
}, 2000);

```