sensorsChecker.js
=================

Mostly all recent browsers expose an api for `deviceorientation` and `devicemotion` events.

 * That doesn't mean the device you're on has sensors (accelerometer+gyroscope) to feed them.
 * So, to check if the device has sensors, you can't rely on simple feature detection like `"ondeviceorientation" in window` or `"ondevicemotion" in window`
 * This module will let you check if there is really an accelerometer+gyroscope to rely on.

```js
//check the sensors for the deviceorientation api
sensorsChecker.checkDeviceorientation(function(){
		console.log('sensors detected');
	},function(){
		console.error('no sensor detected');
	}
);
//check the sensors for the devicemotion api (this time with some options)
sensorsChecker.checkDevicemotion(function(){
		console.log('sensors detected');
	},function(){
		console.error('no sensor detected');
	},{
		userAgentCheck: /(iPad|iPhone|Nexus|Mobile|Tablet)/i,//@optional (to bypass the sniffing)
		delay: 600//@optional default delay : 500ms
	}
);
```

Used in :

* https://github.com/topheman/PanoramaSensorsViewer
* http://streetview.topheman.com
* https://github.com/topheman/bombs
* https://github.com/topheman/playground2 (finally, no need for, according to the UX)
