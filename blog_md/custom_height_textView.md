##UITextView 自定义高度

![textview](../image/text_view.png)



###先说说IOS7的怎么做

```javascript

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


```javascript

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

###最后看看IOS7的textKit
文章参照 

[TextKit 入门和进阶](http://www.360doc.com/content/13/1031/23/8772388_325719203.shtml)





