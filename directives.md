# C\# -类
  
当你定义一个类，你定义一个数据类型的蓝图。实际上你并没有定义任何数据，但是它定义了类的名字意味着什么。也就是说，一个类的对象由哪些可以在该类上进行的操作构成。对象是类的实例。方法和变量构成的类被称为类的成员。
  
##定义一个类
  
一个类定义以关键字class开始，其次是类的名称；类的主体部分体由一对花括号括起来。以下是一个类定义的一般形式：
<pre><code><access specifier> class  class_name
{
   // member variables
   <access specifier> <data type> variable1;
   <access specifier> <data type> variable2;
   ...
   <access specifier> <data type> variableN;
   // member methods
   <access specifier> <return type> method1(parameter_list)
   {
      // method body
   }
   <access specifier> <return type> method2(parameter_list)
   {
      // method body
   }
   ...
   <access specifier> <return type> methodN(parameter_list)
   {
      // method body
   }
}</code></pre>
  
笔记：
  
- 访问说明符的访问成员的规则与类本身的访问规则相同。如果没有说明，则默认访问的类的类型为 internal 。对成员的默认访问类型是 private 。
  
- 数据类型指定了变量的类型，如果有返回值的话，返回指定的数据类型的方法返回的数据类型。
  
- 访问类的成员，可以使用"."点运算符。
  
- 点运算符连接的成员的名字和对象的名称。
  
下面的例子说明了到目前为止对于概念的讨论：
<pre><code>using System;
namespace BoxApplication
{
    class Box
    {
       public double length;   // Length of a box
       public double breadth;  // Breadth of a box
       public double height;   // Height of a box
    }
    class Boxtester
    {
        static void Main(string[] args)
        {
            Box Box1 = new Box();   // Declare Box1 of type Box
            Box Box2 = new Box();   // Declare Box2 of type Box
            double volume = 0.0;    // Store the volume of a box here

            // box 1 specification
            Box1.height = 5.0;
            Box1.length = 6.0;
            Box1.breadth = 7.0;

            // box 2 specification
            Box2.height = 10.0;
            Box2.length = 12.0;
            Box2.breadth = 13.0;
           
            // volume of box 1
            volume = Box1.height * Box1.length * Box1.breadth;
            Console.WriteLine("Volume of Box1 : {0}",  volume);

            // volume of box 2
            volume = Box2.height * Box2.length * Box2.breadth;
            Console.WriteLine("Volume of Box2 : {0}", volume);
            Console.ReadKey();
        }
    }
}</code></pre>
  
上面的代码被编译执行后，产生如下执行结果：
<pre><code>Volume of Box1 : 210
Volume of Box2 : 1560</code></pre> 
  
##成员函数和封装
  
一个类的成员函数有其自己定义或其原型在类的定义中类似于其他变量。它可以操作该类的任何成员对象，并且可以访问一个类的所有成员。
  
成员变量是一个对象的属性（从设计的角度来看），他们都是私有（private）的以便实施封装。这些变量只能使用public成员函数访问。
  
让我们把上述那些概念来 set 和 get 一个类中不同的类成员的值：
