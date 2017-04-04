# YAJB-JavaScript
JavaScript lib for Yet Anther JavaScript Bridge

compatible with Android Chromium WebView(since API 30) and iOS WKWebView(iOS 8.0+).

[YAJB-Android](https://github.com/Muxi-Studio/YAJB-Android)
[YAJB-iOS]()

## Usage

```
var YAJB = require('yajb-js')
var yajb = new YAJB() // can also be accessed using window.YAJB_INSTANCE

// send event's name and data to Native
// deal with the returned data
yajb.send("click", {value:1}).then(function(val){
	// value returned from Native
	console.log(val)
}) 


// register a event and wait for the Native to trigger 
yajb.register("emit", function(data){
	// feel free to deal with the returned data
    console.log(data)
})


// register a event
// once the event is triggered, send messsages back to Native
yajb.register("emit", function(data,fn){
	// feel free to deal with the returned data
    console.log(data)
    var message = data + "haha"   
    fn(message)
})
```

## APIs

`YAJB.prototype.send`

`YAJB.prototype.register`
