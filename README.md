# jquery-extend
jquery-extend用法

    $.extend([deep],targrt,object1[,objectN])

<h3>用法一</h3>
只传入一个参数，且参数为对象，为jquery添加自定义的属性或方法
```javascript
var obj={
   eyes:"three",
   ear:4,
   eat:function(){
      console.log("i want eat you")
   },
}
$.extend(obj);
$.eyes //"three"
$.ear //4
$.eat()//i want eat you
```
<h3>方法二</h3>
传入两个以上参数，且参数为对象，作用为为合并对象，第一个对象参数为合并主体，且后合并的属性可将原有属性覆盖
```javascript
var obj1={
   eyes:"three",
   ear:4,
   banana:{width:99999999}
}

var obj2={
banana:{width:52,price:100},
}
//将obj2合并到obj1
$.extend(obj1,obj2);

console.log(obj1);//Object {eyes: "three", ear: 4, banana:{width:52,price:100}}//banana属性被obj2覆盖
```
<h3>方法3</j3>
传入三个以上参数，第一个参数为布尔值<b>true</b>，之后的参数为对象，这种方法会用递归方式合并对象属性值
```javascript
var obj1={
   eyes:"three",
   ear:4,
   banana:{width:52,price:100},
}

var obj2={
 banana:{width:99999999}
}
//将obj2合并到obj1
$.extend(true,obj1,obj2);

console.log(obj1);///Object {eyes: "three", ear: 4, banana:{width:9999999,price:100}}
```








