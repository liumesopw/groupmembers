# groupmembers
PC微信机器人之实战分析微信艾特群成员,PC个人企业微信机器人之实战分析微信发送xml文章消息call，微信机器人开发sdk，个人微信机器人开发API，淘宝客微信发单机器人开发sdk，导购返利机器人研发SDK、微信群管理机器人开发SDK， 微信二次开发SDK，微信个人号开发API接口协议企业微信SDK、企业微信开发API、,企业微信第三方开发接口适用于企业微信营销软件研发、企业微信工作手机研发、企业微信云控系统研发、企业微信客服系统研发、企业微信营销系统研发、 企业微信客微商营销工具研发、企业微信scrm客服系统研发、企业微信聊天机器人、企业微信群管理机器人研发企业微信协议API接口开发

今天主要讲一下群的@功能，首先在OD里面，先去发送消息的地方加一个断点，然后在PC微信发个消息，发现已经断下来了，发送消息，当没有@的时候，参数传个0，当有@的时候，需要传被@人的wxid过去，
![image](https://user-images.githubusercontent.com/96330669/173977464-a9c3a428-e505-4921-abd1-dbf6b6930d39.png)
调试过程，可以看到传参数里面的内容，前面是被@的微信id，后面跟着内容，来到这个函数的头部，下一个断点，然后在微信群里@一下，然后一步一步向下面走，看在哪里赋值的，当走到一个call的时候，里面不是空的了，是wxid，然后在这个call下一个断点看下，然后进入call里面走断点，看哪里赋值的，	
![image](https://user-images.githubusercontent.com/96330669/173977500-7fbedb8c-90fe-4383-bc22-109a426269f5.png)
然后一直走，发现里面有组装的一些信息，应该就是这个call了，里面一个是wxid，一个是装结构的缓冲区，紧接着的那个call非常有可能是，找到后，做一个实验，就是在PC微信群里直接发一个消息，不带@，然后修改eax 里面传个被@人的wxid，看下PC微信里面是否能收到一个带@的信息，最后发现是接收到一个@的消息，说明这个call就是@群成员的。
![image](https://user-images.githubusercontent.com/96330669/173977528-9e307fd3-2499-4dc2-8d17-9b650020268b.png)
目前已经实现了很多有趣的功能，运行稳定，比如：发各种消息，
接收各种消息，群管，下载文件，加好友，检测僵尸粉，朋友圈等等功能，
可提供接口，方便各种语言二次开发，欢迎技术交流，Q：2645542961
，请勿用于商业用途。
![image](https://user-images.githubusercontent.com/96330669/173977602-8ba72923-ae7b-4069-92bd-db8100b1e855.png)
企业微信：
目前已经实现了大部分功能，运行稳定，比如：发各种消息，
接收各种消息，外部群内部群管理，下载文件，加好友等等功能，
可提供接口，方便各种语言二次开发，欢迎技术交流。
