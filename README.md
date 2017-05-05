# MergeJson


```
     (function($)
            {$.concat||$.extend
            ({concat:function(){
                return Array.prototype.concat.apply([],arguments);
            }})
                })(jQuery);
```


#extra json syntax

JSON的语法分为三种类型：
1.简单值：可以在json中表示字符串，数值，布尔值，null。但不支持javascript中的undefined。
```
   "how are you ?"
```
注意：json字符串必须使用双引号（单引号会导致语法错误).

2.对象：作为用复杂数据类型，表示的是一组有序的键值对。而每个键值对的值可以是简单值，也可以是复杂数据类型的值

javascript对象的字面量：
```
            var person={
                name:"LzCrazy",
                age:10
            };
```

在json对象中写法

```
                var object={
                    "name":"lzCrazy",
                    "age":999
                };
```
或者：
            {
                "name":"lzcrazy",
                "age":1321

            }
            
json数据和javascript对象有两个不同的地方，首先，没有声明变量（JSON中没有变量的概念）。其次是末尾的分号（json数据不需要分号）
```
            {
                "name":"lzCrazy",
                "age":1231,
                "company":{
                    "name":"Loving dream comany",
                    "location":"sz"
                }
            }
```
在同一个对象中不允许出现两个同名的属性

3.数组：表示一组有序的值的列表，可以通过数组索引来访问其中的值。数组的值有呃可以是任意类型--简单值，对象，数组。
JSON数组也没有变量和分号。把数组和对象结合起来，可以构成更复杂的数据集合。

例如，
```
    [
        {
            "title":"json",
            "authors":[
                "LzCrazy Me"
            ],
            edition:3,
            year:2017
        },
        {
             "title":"HTML",
              "authors":[
               "LzCrazya Me"
               ],
               edition:3,
                year:2017
        },
    ]
```

JSON中的方法使用。

1,JSON.stringfy(),序列化javascript对象，可以接收两个参数（1,过滤器，可以是一个函数，也可以是一个数组 2,选项
，表示是否在JSON字符中保留缩进）

2.JOSN.parse()解析选项，可以接收一个参数，该参数是一个函数

3.toJSON（）方法，返回一个JSON数据格式的字符
    
    toJson()可以作为函数的过滤器使用，假如把一个对象传入JSON.stringify(),序列化该对象的顺序
        1.如果存在toJSON方法而且能通过它取到有效值，，则调用该方法
        2.如果提供了第二个参数，传入的函数的过滤器的值是第一步的返回值
        3.对第二部返回的每个值进行相应的序列化
        4.如果提供了第三个参数，执行相应的格式化
    
