# serverless-download

chrome 65以后就删除了对[a.download](https://stackoverflow.com/questions/49474775/chrome-65-blocks-cross-origin-a-download-client-side-workaround-to-force-down)的跨域支持。


js图片另存为，在chrome上确实玩不转了，chrome现在不支持将url地址直接赋值给a标签的href属性（浏览器会直接跳转）。

唯一的办法就是将图片url转化为base64或者ObjectURL，有两种转化方法：

1、canvas

2、fetch或者xhr

但是这两种方法都有跨域限制，所以只能后端提供支持cors了。

本仓库提供了4个下载例子:

* 同域下载
* 跨域下载，页面直接跳转
* 跨域，服务端支持cors，通过canvas转换为base64进行下载
* 跨域，服务端支持cors，通过fetch获取blob，然后转换为ObjectURL进行下载

通过fetch下载时，chrome会提示[不安全的脚本](https://support.google.com/chrome/answer/99020?p=unauthenticated&visit_id=636806410731401727-3641021513&rd=1#content)，需要信任一下才能正常下载。

所以最终还是建议通过canvas转换为base64的方式来下载。
