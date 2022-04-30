#less
```css
--color:#bfa;
```
原生css中设置变量的方式
```css
var(--color);
```
原生css引用变量的方式
```less
@a:122px;
```
less中设置变量的方法
```less
body{
    .box2{
        width: @a;
    }
}
```
在less中,可以直接在父元素中进行嵌套编写对子元素样式进行设置,在变量名前加@可对其进行引用
```less
.box{
    &:hover{
    }
}
```
嵌套编写引用自身时需要用&符号表示自身
```less
.@{c}{
}
```
但将变量设置为组名的时候需要用中括号将变量名括起来
```less
.@{c}{
    width: 100px;
    height: $width;
}
```
在less中可以直接用$符号对当前设置的属性值进行引用
```less
.p1{
}
.p2:extend(.p1){
}
```
继承变量名中的属性值
```less
.p3{
    .p1();
}
```
直接引用其属性值,对比继承消耗内存多
```less
.p4(){
}
```
在less中可以设置函数,其本身不会生效
```less
.test(@w){
    width: @w;
}
div{
    .test(200px);
}
```
less中可以设置混合函数,在其中可以设置变量,引用时需填写变量值
```less
.box1{
    height: 100px - 50px;
    width: 100px * 2;
}
```
less中可以进行简单的计算
```less
@import "style.less";
```
引入less文件的方式