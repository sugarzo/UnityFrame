# UnityFrame
一些unity框架，目前只做到了Trigger/Action/状态表示系统

内置了Odin,EasySave3插件

使用方法：

在场景中添加任意一个物品，用于负责事件触发和执行。先在Inspector面板中找到Sugarzo触发器

![image](https://user-images.githubusercontent.com/74815734/189597350-564f48a4-a3a8-44b7-a94a-b1b756ae662c.png)

随后会自动添加对应Trigger和事件列表ActionList,当触发器满足条件触发时会顺序执行事件。

![image](https://user-images.githubusercontent.com/74815734/189597593-1d3f58f4-d856-4c44-a29c-70fbe8d07741.png)


如何扩展Trigger和Action？

可以在unity顶部窗口找到项目框架拓张设置，打开对应窗口。

当然也可以自己建立脚本。触发器需要继承BaseTrigger，自定义设置什么是否触发Execute函数即可。

自定义事件需要继承BaseAction，将事件的逻辑写在RunningLogic中即可，在自定义的事件逻辑完成时需要调用Runover回调函数，该函数会将信息回传给Trigger让触发器执行下一个事件（若需要延迟触发可以使用协程挂起RunOver，参考框架内IntervalAction的写法）

![image](https://user-images.githubusercontent.com/74815734/189597913-763fdc7a-1404-4f1d-a15a-597c6897f136.png)

![image](https://user-images.githubusercontent.com/74815734/189598036-28bcdc1c-c8ed-4316-aab2-49c834b86b50.png)
