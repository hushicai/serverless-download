# serverless-download

chrome 65以后就删除了对a.download的跨域支持:

https://stackoverflow.com/questions/49474775/chrome-65-blocks-cross-origin-a-download-client-side-workaround-to-force-down

js图片另存为，在chrome上确实玩不转了，chrome现在不支持将url地址直接赋值给a标签的href属性（浏览器会直接跳转）。

唯一的办法就是将图片url转化为base64或者ObjectURL，有两种转化方法：

1、canvas

2、fetch或者xhr

但是这两种方法都有跨域限制，所以只能后端提供支持cors了。
