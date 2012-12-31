# duplex-emitter

Turns a duplex streams into an event emitter.


## Create

```javascript
var s = net.connect(...);

var duplexEmitter = require('duplex-emitter');
var emitter = duplexEmitter(s);
```

## Emit

You can emit events. They will be serialized (to JSON) and piped to the stream.

```javascript
emitter.emit('event1', arg1, arg2); // Send event to the other side
```

## Receive

You can listen for events from the peer:

```javascript
// Got event from the peer
emitter.on('event2', function(arg1, arg2), {
  //...
})
```