# Huorong-Rules

嗯，看到QQ的瓜有点多，读取桌面，遍历浏览器记录啥的，以黑名单方式限制不够全面，天知道以后会读取啥。

所以整了一个白名单方式限制的，限制所有 Tencent 目录的程序（假设你是安装在默认目录），只能读取它该访问的，其他一概询问（或者已知不需要的文件自动拒绝）。

目前允许访问的包括：
Tencent 自己的目录，包括Tencent Files，聊天记录，多媒体，下载文件等。
微信的目录，聊天记录，多媒体，下载文件等。
部分系统目录，包括部分系统DLL（可能之后还会再精准一点）、字体、图标缓存、Prefetch，等正常运行所需的目录/文件（包括Flash，不需要可以自己关）。

显式拒绝的包括：
Chrome 相关文件。
hosts。
桌面（主要读取了lnk，禁止了，看之后还读到啥再加）
一些会正常启动会被尝试读取，频繁弹提示的文件（可有可无，不影响启动，使用的文件）

以上没有允许的，一概提示处理（AppData可以参考另外一个规则，因为有误伤可能，只做了 Chrome 的显式拒绝，全盘拦截所以其他如遇到的会直接报提示处理）

这边已经测试了 QQ、微信、TIM 桌面标准版本，能够正常启动、使用、存取聊天记录、在测试期内（大概半小时）不弹出防护询问（我这边弹出的，都已经加到自动处理规则了）的，当然不排除会有什么定时任务可能得之后弹出，不过已经不影响使用了。

一拍脑袋，纯手工编辑，非常非常非常初始的版本，可能有遗漏，欢迎大家提Issue/PR补充~

#### 使用方法：

火绒->防护中心->左下角高级防护->自定义防护（注意启用，然后点文字进去）

分别导入 "自动处理规则"（tencent-auto.json）、"自定义规则"（tencent-custom.json），启用即可。（注意两个文件要分别在不同选项卡中导入，窗口顶部切换！！！）



#### 敲黑板，不要在弹出的提示内选择“记住本次操作”，否则会对所有文件生效。如有需要修改可以至 自动处理 规则内添加，好使了可以直接PR方便大家~
