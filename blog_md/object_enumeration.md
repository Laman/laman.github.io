
##objective-c 枚举（enumeration）

![enumeration](../image/enumeration.png)



###说说枚举

* 程序的可读性强

* 程序的健壮行增加

* 增加代码的效率 类似于 宏 


###枚举的用法

* 就像用 struct 一样 ，enum 是自定义一个集合， 增加程序的健壮行和可读性！

```

enum PAPER_TYPE{

    PAPER_TYPE_IMAGE = 0,
    PAPER_TYPE_CHAR
    
};

typedef enum PAPER_TYPE PAPER_TYPE;


```

* 在后续的使用中，就跟使用一个自定的class 一样使用就可以

```

PAPER_TYPE _type;


```

