##UITextView 自定义高度

![textview](../image/text_view.png)


###先说说IOS7的怎么做

```

tipsTextView.textAlignment = NSTextAlignmentNatural;
NSMutableParagraphStyle *paragraphStyle = [[NSMutableParagraphStyle alloc] init];
paragraphStyle.lineHeightMultiple = 25.0f;
paragraphStyle.maximumLineHeight = 25.0f;
paragraphStyle.minimumLineHeight = 25.0f;
NSDictionary *attribute = @{
                            NSParagraphStyleAttributeName : paragraphStyle,
                            };
tipsTextView.attributedText = [[NSAttributedString alloc] initWithString:tipsStr attributes:attribute];

[tipsTextView sizeToFit];


```

###再看看IOS5/6 怎么做


```

tipsTextView.textAlignment = NSTextAlignmentNatural;
NSMutableParagraphStyle *paragraphStyle = [[NSMutableParagraphStyle alloc] init];
paragraphStyle.lineHeightMultiple = 25.0f;
paragraphStyle.maximumLineHeight = 25.0f;
paragraphStyle.minimumLineHeight = 25.0f;
NSDictionary *attribute = @{
                            NSParagraphStyleAttributeName : paragraphStyle,
                            };
tipsTextView.attributedText = [[NSAttributedString alloc] initWithString:tipsStr attributes:attribute];

tipsTextView.frame = CGRectMake(14, 10, 262, tipsTextView.contentSize.height);


```
注意观察，其实就是决定textview frame 的时候调用的方法不一样， 注意区分！


`[tipsTextView sizeToFit];`

`tipsTextView.frame = CGRectMake(14, 10, 262, tipsTextView.contentSize.height);`

---------------

###最后看看IOS7的textKit

苹果在ios7之后引入了textkit，下面我们来学习textKit可以帮助我们怎样更好的处理文本信息。

`先看看textKit的定义：`

>Text Kit指的是UIKit框架中用于提供高质量排版服务的一些类和协议，它让程序能够存储，排版和显示文本信息，并支持排版所需要的所有特性，包括字距调整、连写、换行和对齐等。


以前，如果我们想实现复杂的文本排版，例如在textView中显示不同样式的文本，或者图片和文字混排，你可能就需要借助于UIWebView或者深入研究一下Core Text。在iOS6中，UILabel、UITextField、UITextView增加了一个NSAttributedString属性，可以稍微解决一些排版问题，但是支持的力度还不够。现在Text Kit完全改变了这种现状。

`before:UILabel、UITextView  ---> NSAttributedString ---->UIWebView`

`now:UILabel、UITextView  ---> NSAttributedString ---->TextKit`


由于TextKit涉及的东西比较多，我会在另一篇博客里面为大家详解，欢迎继续关注我的博客。



