# tumblrScrapy
一个针对Tumblr的爬虫，通过API获取视频、图片的地址，保存到本地。
 
##tumblrScrapy
&emsp;&emsp;Tumblr页面在滚动条拉到最底下时会自动加载下一页内容，当浏览的页面多时，会非常非常卡，加上国内在访问Tumblr奇慢无比，于是萌生了写一个爬虫自动爬的想法。

&emsp;&emsp;首先我从tumblr页面分析开始，发现tumblr的资源连接都是明文存在的，如果在浏览器中直接输入资源的连接，可以非常快速的访问资源，但是在tumblr上总是不停的加载加载再加载，估计是和Tumblr的后台业务有联系，于是经过一番分析找到了Tumblr的JSON数据接口：`http://username.tumblr.com/api/read/json?start=0&num=200'`，username为用户的名称，start、num为开始、结束的记录数目（以天为单位），然后用Python写了爬虫，这两天似乎国内已经无法访问上Tumblr了，于是翻墙找了一段API返回的数据，打成txt在附件中，不会翻墙的小伙伴可以用这个txt练习。

&emsp;&emsp;初步的设想是将抓取后的数据保存到本地txt和MongoDB，后期会用Python写一个下载脚本，批量读取这些URL进行下载。

ToDo:
 - 视频地址提取尚未完工，想用正则表达式进行提取
 - 结果存储到MongoDB未完工，待定
 - 可以写一个自动发布脚本，将热门数据自动发布到个人网页上（版权问题、道德问题，不实现）
