<!--remove-start-->

# Ping

<!--remove-end-->






##### Breadboard for "Ping"



![docs/breadboard/ping.png](http://i.imgur.com/agyKcet.png)<br>



&nbsp;




Run with:
```bash
node ping.js
```


```javascript
var five = require("johnny-five");
var board = new five.Board();

board.on("ready", function() {

  // Create a new `ping` hardware instance.
  var ping = new five.Ping(7);

  // Properties

  // ping.in/ping.inches
  //
  // Calculated distance to object in inches
  //

  // ping.cm
  //
  // Calculated distance to object in centimeters
  //


  ping.on("change", function() {
    console.log("Object is " + this.in + " inches away");
  });
});

```




&nbsp;

### [Go to Next Lesson >>](../holiday_lights/)