sensorsChecker.js
=================

Mostly all recent browsers expose an api for `deviceorientation` and `devicemotion` events.

 * That doesn't mean the device you're on has sensors (accelerometer+gyroscope) to feed them.
 * So, to check if the device has sensors, you can't rely on simple feature detection like `"ondeviceorientation" in window` or `"ondevicemotion" in window`
 * This module will let you check if there is really an accelerometer+gyroscope to rely on.

```js
sensorsChecker.checkDeviceorientation(function(){
		console.log('sensor detected');
	},function(){
		console.error('no sensor detected');
	},{
		userAgentCheck: /(iPad|iPhone|Nexus|Mobile|Tablet)/i,//@optional
		delay: 600//@optional default delay : 500ms
	}
);
```

Used in :

* https://github.com/topheman/PanoramaSensorsViewer
* http://streetview.topheman.com
* https://github.com/topheman/bombs (to be implemented)
* https://github.com/topheman/playground2 (to be implemented)