# blog
URL输入 （浏览器发送请求）
URL：统一资源定为符（Uniform Resource Locator），用于定位资源；包含内容：协议，域名，端口号等等

协议：http，file，https。
http://google.com.hk/ 定位位于web上的文件
file:///users/xxx/ 定位本地电脑上的文件
https://taobao.com/ http的安全版本，http是明文传输，https经过了加密。
//xxx/xxx/ 没有明确标明协议，表示和当前页面所用协议相同。

*域名解析
根据域名找到相应的IP地址（域名是给人看的，浏览器看不懂域名的，要找到IP地址才行）DNS（Domain Name System）：网络名称（域名）系统，域名和IP对应，这样计算机就找到IP了。
域名：google.com
端口号：80（http默认80；8080给root用户使用的）
IP地址 公网IP和局域网IP是不同的。本机IP：127.0.0.1（调试手机时可以用这个测试）

*域名解析过程
1.浏览器缓存DNS
2.本地缓存，hosts文件；和DNS不同，可以自己修改hosts文件（可以本地调试，127.0.0.1）。
3.路由器缓存DNS
4.ISP（Internet Service Provider）缓存DNS
5.如果都没有找到的话，则向根域名服务器(全球有13台逻辑服务器，即根域名服务器只有13个IP，中国有3台镜像)查找域名对应IP，根域名服务器把请求转发到下一级，直到找到IP。

*服务器处理（服务器收到请求后）
服务器用来处理请求的应用软件（web server），常见的有：Apache、Nginx、IIS、Lighttpd。

*服务器处理流程（常说的后端）
MVC(model-view-controller)：模型-视图-控制器。
服务器应用常用语言：php、java、ruby、python、node.js。
model是对数据库的抽象。受到请求后，需要使用数据库语言（sql语句）来操作数据库获得数据，但是太麻烦了，于是抽象出model。
view是HTML的模板，拿到数据后，将数据填充到HTML模板，得到HTML文件。（常说的前端） //？常说的各种前端框架好像也是类型的结构啊。
处理完成后，返回请求和数据。

*浏览器处理
收到服务器的返回请求后，浏览器开始处理。
HTML字符串倍浏览器接收后被一句一句读取解析
解析到link标签后重新发送请求获取css
解析到script标签后发送请求获取js，并执行代码
解析到img标签后发送请求获取图片资源

*绘制网页
浏览器根据HTML和CSS计算得到渲染树（好像是同时渲染的，js改变DOM后，还会进行渲染，这就涉及到性能优化了），绘制到屏幕上
js会被执行

作者：依泥
链接：http://www.jianshu.com/p/3661c8707851
來源：简书
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。