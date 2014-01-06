##ios 的国际化

![internationalization](../image/internationalization.jpg)

###为什么要国际化

* `跨越语言的障碍`，让你的应用程序适合更多的人群


* 让你的应用程序可以根据语言环境的不同，转换成`不同的风格`！



###怎样国际化（xcode5 环境下）


####a、基本设置的国际化

1、默认项目只有英语这个语言，可以在 project 里面的 info 选项下面会有Localizations，增加 chinese 语言；


2、在InfoPlist.strings下面，会有针对这两个语言的文件 

如要在不同的语言环境下应用的名字显示不一样：

在chinese 这个文件下面： 
CFBundleDisplayName="中文";

在english 这个文件下面
CFBundleDisplayName="english";

那么如果系统的语言设置成中文，就会现实 “中文”  如果是英文就会显示 “english”

更多可以设置的可以参照:    [Information Property List Key Reference](https://developer.apple.com/library/ios/documentation/General/Reference/InfoPlistKeyReference/Articles/CoreFoundationKeys.html)

####b、应用程序内容的国际化

1、新建Localization.strings 资源文件；

2、单击该文件，在文件简介这里有一个localization 这个栏目，勾选你需要的语言（前提是你在 project的info下面 新建了这些语言）

3、如一个菜单实现国际化

在Localization.strings 的chinese 文件下
“menu” = “菜单”

在english 文件下
“menu” = “menu”

在使用的时候 NSLocalizedString(@"menu", @""); 返回该语言环境下的字符内容。


###总结

ios 的国际化非常简单， 大家在开发的时候如果你的应用或者游戏可能会在不同的语言环境下用到，建议假如国际化，会使你的应用受众更广。




