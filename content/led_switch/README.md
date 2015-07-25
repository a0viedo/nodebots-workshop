# Digital Input - Led más pulsador

## Circuit

![Button](http://i.imgur.com/al9dls5.jpg)

## Code

``` js
var five  = require('johnny-five'),
    board = new five.Board(),
    button,
    led,
    state = 0;

board.on('ready', function () {
  button = new five.Button(2);
  led = new five.Led(6);

  button.on('down', function () {
    console.log('apretaste el pulsador');
    if(state === 0) {
        led.on();
        state = 1;
        
    } else if(state === 1) {
        led.off();
        state = 0;
    }
  });

  button.on('hold', function () {
    console.log('estás manteniendo apretado el pulsador');
  });

  button.on('up', function () {
    console.log('soltaste el pulsador');
  });
});

```

## Run

```
$ node button.js
```

### [Go to Next Lesson >>](../music_player/)