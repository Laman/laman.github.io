##IOS 自定义字体


###导入字体

1. 添加对应的字体(.ttf或.odf)到工程的resurce，例如my.ttf

2. 在info.plist中添加一项 Fonts provided by application (item0对应的value为my.ttf，添加多个字体依次添加就可以了)

3. 使用时 aLabel.font=[UIFont fontWithName:@"XXX" size:30]; 注意XXX不一定是my，这里是RETURN TO CASTLE，


###打印当前所有字体以找到 fontName

```

NSArray *familyNames = [[NSArray alloc] initWithArray:[UIFont familyNames]];
NSArray *fontNames;
NSInteger indFamily, indFont;
for(indFamily=0;indFamily<[familyNames count];++indFamily)
{
NSLog(@"Family name: %@", [familyNames objectAtIndex:indFamily]);
fontNames =[[NSArray alloc]initWithArray:[UIFont fontNamesForFamilyName:[familyNames objectAtIndex:indFamily]]];
for(indFont=0; indFont<[fontNames count]; ++indFont)
{
NSLog(@" Font name: %@",[fontNames objectAtIndex:indFont]);
}
[fontNames release];
}
[familyNames release];
 

```
###总结

* ios 要使用自定义的字体很简单，有些内容型的应用可能对这方面有比较大的需求，但是要注意字体的版权问题！