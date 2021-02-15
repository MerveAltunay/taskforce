

# Hiyerarşik Kalıtım (Hierarchical Inheritance)


Java’da nesne yönelimli programlamayı oluşturan 4 önemli unsurdan bir tanesi Inheritance kavramıdır. Inheritance, sınıflar arasında kalıtımı mümkün kılarak, bir sınıf özelliklerinin başka bir sınıf içerisinde kullanılabilmesine olanak sağlamaktadır. Bu sayede classlar arasında ortak kullanıma sahip kod parçacıklarının birden fazla yazılması engellenmiş olur. Ayrıca kodun tekrar kullanılabilirliğini sağlayarak performansı artırdığı ve kolay okunabilir bir program yapısı sağladığından dolayı Inheritance kavramı oldukça önemli bir konudur.

Inheritance birçok farklı tipte uygulanabilmektedir. Bunlardan başlıcaları şunlardır; Single Inheritance, Multilevel Inheritance, Multiple Inheritance ve Hierarchical Inheritance. Java programlama dilinde single, multilevel ve hierarchical inheritance uygulanabilirken multiple inheritance yapısı doğrudan uygulanamamaktadır. Bu yazıda sizlere Java’nın kullanmamıza imkan sağladığı Inheritance tiplerinden olan **Hierarchical Inheritance** yapısından bahsedeceğim.

Hiyerarşik kalıtım, bir superclassın birden fazla subclassa sahip olduğu ve her subclassın ise sadece bir tane superclassa sahip olduğu bir kalıtım çeşididir.

<img src="hierarchical_inheritance.png"/>

Yukarıdaki akış şemasında da görüldüğü üzere, class A ‘dan B, C ve D isminde 3 farklı sınıf türetilmiştir. Ve bu türetilen sınıflar yalnızca bir superclass üzerinden miras alabilmektedir. Bu durumda class A superclass, B,C ve D classları ise subclassdır. 

Hierarchical Inheritance sözdizimi aşağıdaki gibidir:

````java

class A {

public static void methodA() {
                   ………………
}}

class B extends A  {

public static void methodB() {
                   ………………
}}

class C extends A  {

public static void methodC() {
                   ………………
}}

class MainClass {

public static void methodB() {
                    ………………
}

public static void main (String [] args) {
 
B objectB = new B();
C objectC = new C();

objectB.methodA();
objectC.methodA();

}}

````

Kalıtım hiyerarşisinde, subclasslar üzerinde yeni özellikler ve metotlar tanımlanabilirken ayrıca  superclasstan kalıtım yoluyla alınan özellikler ve metotlar yeniden tanımlanarak da kullanılabilmektedir. Bu yönteme **Overriding** denilmektedir. Yani bir üst classtan gelen özelliklerin geçersiz kılınarak, yeniden implemente edilmesi olayıdır.


Aşağıdaki modelde bir tane ATA sınıfımız var ve bu sınıftan kalıtım alan iki alt sınıfımız bulunmaktadır. OTVTax, KDVTax subclassları Tax sınıfından kalıtım yoluyla eriştikleri calculate metotunu yeniden implemente ederek Tax sınıfını override etmişlerdir. Bu model hiyerarşik kalıtımın basit bir örneğidir.

![Hiyerarşik Kalıtım](/Users/kodluyoruz/Projeler/kodluyoruz/taskforce/java/java-102/object-oriented-programming/figures/hierarchical-inheritance.png)

````java
public class Tax {
	
	public double calculate(double value) {
		
		return value + value * 0.1;
	}
}

public class OTVTax extends Tax {

	@Override
	public double calculate(double value) {
		
		return value + value * 0.2;
	}
}

public class KDVTax extends Tax{

	@Override
	public double calculate(double value) {
		
		return value + value * 0.3;
	}
}
````


