---
title: 'Java中类名+方法名（）{}什么意思'
categories: Java
tags:
  - Java
abbrlink: 23330
date: 2019-09-15 12:55:10
---

发现问题并解决它
<!--more-->

```
public class Parcel7b{
	class MyContents implements Contents{
		private int i = 11;
		public int value() {return i;}
	}
	public Contents contents() {  //1
		return new MyContents();
	}
	
	public static void main(String[] args) {
		Parcel7b p = new Parcel7b();
		Contents c = p.contents();
	}
}
```

在代码1处，使用了类名+方法名的方式创建方法，这样写有什么用？

-----------------------------分隔符---------------------------------------------------------------------------------------------------------------------------------------------------------------

意思是这个方法的返回类型是某个类的实例。

上面的这种创建方式，说明此方法返回的是Contents的一个实例（对象）

那有什么好处？

可以通过类名+方法名调用的方法叫静态方法，属于类级别方法，类方法可在不实例化对象的前提下调用，一般类的静态方法和静态变量都是通过static关键字修饰的，而且静态方法体里不能应用任何实例变量和实例方法。至于你那段程序，调用那个方法和new一个对象效果是一样的。不过只是把实例的创建封装在方法里，通过类名加方法来调用而已,让实例化代码简洁点外，无任何差别。不过，有些时候，有些类的设计，出于某种需要，不希望类的构造方法是public的，也就是用户无法直接new出来的，通常就会通过这么一个静态方法来调用获取实例。而且这些方法体里除了直接return 一个实例之外，可能还会做某些处理,这在java里许多类都有这种设计。如，j2me中的Image类。