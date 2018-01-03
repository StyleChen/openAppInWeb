# openAppInWeb

在web网页中打开本地 APP

如果没有安装APP 则跳去下载；

如果APP没有在腾讯应用宝或腾讯微下载上架

则在QQ内置浏览器和微信内置浏览器是无法打开APP的

因为腾讯对其浏览器进行了限制

所以用户在QQ内置浏览器和微信内置浏览器中打开的时候

要引导用户用浏览器打开

var ua = navigator.userAgent.toLowerCase();//获取判断用的对象 可在真机中alert比较差异

判断微信内置浏览器  不分Android/ios
ua.match(/MicroMessenger/i) == "micromessenger"

ios判断qq内置浏览器   包含空格qq但不包含mqqbrowser
/\s+qq/.test(ua) && !(/mqqbrowser/.test(ua))

Android判断qq内置浏览器   包含空格qq并且包含mqqbrowser
(/\s+qq/.test(ua) && /mqqbrowser/.test(ua))
