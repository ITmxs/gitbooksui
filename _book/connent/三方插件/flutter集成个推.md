> 最新的个推插件介绍和使用请参考个推官网：
>  Github：[https://github.com/GetuiLaboratory/getui-flutter-plugin](https://links.jianshu.com/go?to=https%3A%2F%2Fgithub.com%2FGetuiLaboratory%2Fgetui-flutter-plugin)

> IOS 没什么可说的照着步骤走就可以，重点说说Android

> 项目开始前我使用的是getuiflut:^0.2.3 配置项如下：
>
> ![img](https:////upload-images.jianshu.io/upload_images/22818555-df251bce29c08f93.png?imageMogr2/auto-orient/strip|imageView2/2/w/1200/format/webp)
>
> image.png
>
> ![img](https:////upload-images.jianshu.io/upload_images/22818555-268c96667a493719.png?imageMogr2/auto-orient/strip|imageView2/2/w/1200/format/webp)
>
> image.png

> 之后将插件版本更新getuiflut:^0.2.5 官方配置如下：
>
> ![img](https:////upload-images.jianshu.io/upload_images/22818555-695edc06b81b2649.png?imageMogr2/auto-orient/strip|imageView2/2/w/1200/format/webp)
>
> image.png
>
> 这里相对0.2.3多了一个
>
> maven {     url "
>
> http://mvn.gt.getui.com/nexus/content/repositories/releases/
>
> " }
>
> 和集成HMS SDK

> HMS SDK根据我的实际测试不用配置照样可以使用个推，所以就过滤掉这个配置，
>  至此运行项目，一切正常能接到推送消息，但是经过测试会发现此时的app间隔十分钟就不会在收到个推的推送消息了，经过一些列调试，从真机设置，到代码逻辑处理，找到根本问题，通过这两个版本配置会发现
>  maven {     url "[http://mvn.gt.getui.com/nexus/content/repositories/releases/](https://links.jianshu.com/go?to=http%3A%2F%2Fmvn.gt.getui.com%2Fnexus%2Fcontent%2Frepositories%2Freleases%2F)" }在新版中多了这一行配置，将其去掉，问题解决！！！

