# 不同位置正确编码
## （1）输出在HTML文本中
```xml
<div>$UserData</div>
```

正确编码示例：

```xml

```



## （1）HTML 实体编码

```xml
<div>$UserData</div>
```


需要编码的字符：
&, <, >, ', ", /

转义方式："&#x" + hex + ";"

## （2）HTML 属性编码(不包括时间属性、URL属性)

```xml
<div attr="$UserData"></div>
```

需要编码的字符：
'\u0009', '\n', '\u000C', '\r', '\u0020', '&', '<', '>', '\"', '\'', '/', '=', '`', '\u0085', '\u2028', '\u2029'


## (3) CSS编码
```xml
<div style="background:url(${UserData} );">123</div>
```

需要编码的字符：
'\"', '\'', '\\', '<', '&', '(', ')', '/', '>', '\u007f', '\u2028', '\u2029'
编码方式方式："\\" + hex + " "；

##（4）URL编码（src、url 属性中）
```xml
<a href="${UserData} ">https://venscor.com</a>
```
源码原则：除"#&-./0123456789=?@ABCDEFGHIJKLMNOPQRSTUVWXYZ_abcdefghijklmnopqrstuvwxyz~"外，一律URL编码。

编码方式："%" + hex

## （5）JS编码
编码原则：输出在Js或者HTML标签时间属性内。


