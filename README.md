#TiTus

<img width=400 src="http://tus.io/assets/img/tus1.png" />


[tus](http://tus.io) is a protocol based on HTTP for resumable file uploads. Resumable means that an upload can be interrupted at any moment and can be resumed without re-uploading the previous data again. An interruption may happen willingly, if the user wants to pause, or by accident in case of an network issue or server outage.

tus-android-client is a library meant to be used in addition to tus-java-client for uploading files using the tus protocol to any remote server supporting it. This package provides additional classes which makes interacting with the Java library easier on Android.


##Usage
```javascript
var Tus= require("ti.tus");
Ti.Media.showCamera({
	success : function(e) {
		var file = Ti.Filesystem.getFile(Ti.Filesystem.applicationDataDirectory, "myPhoto");
		file.write(e.media);
		var client = Tus.createClient(file.nativePath);
		client.addEventListener("progress",handleProgress);
		client.addEventListener("success",handleSuccess);
		client.addEventListener("error",handleError);
	}
});


```