#### java .....equals

1.  Integer,String equals比较的是内容
1.  对象比较的的是内存地址

* 当参数obj引用的对象与当前对象为同一个对象时 true 反之是false

* JDK类中有一些类覆盖了oject类的equals()方法,比较规则为：
 
		如果两个对象的类型一致，并且内容一致，则返回true,这些类有：
		java.io.file,java.util.Date,java.lang.string,包装类（Integer,Double等）

* 重写equals方法时   

	 	1、自反性   ：对任意引用值X，x.equals(x)的返回值一定为true.
	 	2、对称性：   对于任何引用值x,y,当且仅当y.equals(x)返回值为true时，x.equals(y)的返回值一定为true;
		3、传递性：如果x.equals(y)=true, y.equals(z)=true,则x.equals(z)=true
		4、一致性：如果参与比较的对象没任何改变，则对象比较的结果也不应该有任何改变
		5、非空性：任何非空的引用值X，x.equals(null)的返回值一定为false

* 重写equals方法的要点

		1、使用==操作符检查“实参是否为指向对象的一个引用”。 
		2、使用instanceof操作符检查“实参是否为正确的类型”。 
		3、把实参转换到正确的类型。 
		4、对于该类中每一个“关键”域，检查实参中的域与当前对象中对应的域值是否匹 配。对于既不是float也不是double类型的基本类型的域，可以使用==操作符 进行比较；对于对象引用类型的域，可以递归地调用所引用的对象的equals方法； 对于float类型的域，先使用Float.floatToIntBits转换成int类型的值， 然后使用==操作符比较int类型的值；对于double类型的域，先使用Double.doubleToLongBits转换成long类型的值，然后使用==操作符比较 long类型的值。 
		5、当你编写完成了equals方法之后，应该问自己三个问题：它是否是对称的、传 递的、一致的？(其他两个特性通常会自行满足)如果答案是否定的，那么请找到 这些特性未能满足的原因，再修改equals方法的代码。