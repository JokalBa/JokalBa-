1.数据类型:

        a.基本类型：string number boolean
        b.引用类型:1.核心类型 function和object
                  2.String Number Boolean Array Date Math RegExp
        c.空类型：undefined和null
1.全等和相等的联系和区别：

    联系：都是关系运算符
    区别：相等== 判断值是否相等
         全等=== 先判断类型 在判断值 
**扩展**：只要是对象object转换为boolean时都是true

**注意**：

    引用类型和值类型参与的运算时：
    1.系统会自动调用。valueof()方法，获取返回值，尝试参与运算，如果可以运算就得出结果
    2.如果无法参与运算，系统会继续调用该引用类型数据.toString()方法，获取返回值参与运算

举例：

     console.log([]==![]) //true

     console.log({}==!{}) //false
     
     var obg={};
     console.log(obj+1) //[object object]1
     
     var str='hello';
     var str1=new String('hello');
     console.log(str==str1); //true
     
2.for in 循环 遍历对象的键
  
举例：

    var obj={
      name:'张三',
      age:30,
      sayHello:function(){
          console.log("我叫"+name+","+age);
      }
      }
      
    for(var k in obj){
      console.log(k);  // name age sayHello
      console.log(obj.k); //undefined
      console.log(obj[k]); // 张三 30 function(){}
      }
    
3.in 属性名 in 对象 判断对象是否可以访问某个属性

    在数组中使用in关键字，判断的数组中是否存在索引值指定的元素
    如果要判断数组中是否存在某个值是使用indexof()方法
4.短路运算： || 和 $$

    a.|| 找真  表达式1 || 表达式2
       如果表达式1 为真，则返回表达式1的值，否则返回表达式2的值        
    b.&& 找假  表达式1 && 表达式2
       如果表达式1 为假，则返回表达式1的值，否则返回表达式2的值 
       

5.delete关键字(课后研究Object.defineproperty)


    1.可以删除没有var声明的变量
    2.删除对象中的属性，返回的是undefined值
    3.有返回值，表示删除成功与否，但是不可靠

**注意**

    1.如果访问一个没有声明过的变量，那会报错，变量is not defined
    2.如果访问的是一个对象不存在的属性，则返回undefined；
    
6.循环语句中的break和continue的区别
    
    break是跳出整个循环，继续执行循环下面的代码
    continue跳出本次循环，继续下一次循环
    
    //两者区别举例
    for(var i=0;i<10;i++){
        if(i==5){
            break; //0 1 2 3 4
            continue; //0 1 2 3 4 6 7 8 9
        }
        console.log(i)
    }
    
    举例：跳出两次循环
    for(var i=0;i<10;i++){
    //开闭原则
        var flag=false;
        for(var j=0;j<10;j++){
            if(j==5){
                flag=true;
                break;
            }
        }
        if(flag){
            break;
        }
    }
    
值类型和引用类型的区别：

    值类型是直接存储数据本身的这种数据就是值类型的数据
    引用类型的存储是数据的地址，数据单独存储起来的这种数据就是引用类型的数据
    
值类型和引用类型的赋值特征

    值类型是将存储的值复制一份给新的变量，原来的变量的值不变
    引用类型赋值是将存储的地址复制一份给新的变量，两个变量同时指向同一个对象，修改其中一个，另一个也会变化