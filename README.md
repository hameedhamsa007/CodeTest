# CodeTest


Animal.java
===========
public class Animal {
	void walk() {
		System.out.println("WALKING");
	}
}

Bird.java
=========
public class Bird extends Animal {
	void fly () {
		System.out.println("FLYING");
	}
}

Final.java
=========
public class Final {
	public static void main(String args[]) {
		new Bird().walk();
		new Bird().fly();
	  new Bird().sing();
	}
}

Explaination
============ 
1. We cannot implement Final.java class, Because the "sing()" method not defined in Bird.java & Animal.java
  The main method will run first "walk()" method extends in "Animal" class -> second "fly()" method extends in "Animal" class - > The "sing()" not defined anywhere. So JRE will throw an exception "Undefined type of method".
  
 
 
2.

Duck.java
=========
public class Duck {
	public void sound() {
		System.out.println("Quack, Quack");
	}
	public void skill() {
		System.out.println("Swim");
	}
}

Chicken.java
============
public class Chicken {
	public void sound() {
		System.out.println("Cluck, Cluck");
	}
	public void skill() {
		System.out.println("Cannot fly, but it actually can !!!...");
	}
}

Birds.java
============
public class Birds {
	public static void main(String[] args) {
		Duck d = new Duck();
		Chicken c = new Chicken();
		d.sound();
		d.skill();
		c.sound();
		c.skill();
	}
}


3.

Duck.java
=========
public class Duck {
	public void sound() {
		System.out.println("Quack, Quack");
	}
	public void skill() {
		System.out.println("Swim");
	}
}

Chicken.java
============
public class Chicken {
	Rooster roost ;
	public void sound() {
		System.out.println("Cluck, Cluck");
	}
	public void skill() {
		System.out.println("Cannot fly, but it actually can !!!...");
	}
	Chicken(Rooster roost) {
		this.roost = roost;
	}
	public void roostSound() {
		roost.sound();
	}
}

Rooster.java
=============
public class Rooster {
	public void sound() {
		System.out.println("Cock-a-doodle-doo");
	}
}

Birds.java
==========
public class Birds {
	public static void main(String[] args) {
		Duck d = new Duck();
		Chicken c = new Chicken(new Rooster());
		d.sound(); // duck sound
		d.skill(); // duck skill
		c.sound(); // chicken sound
		c.skill(); // chicken skill
		c.roostSound(); // rooster chicken sill
	}
}

4.

Parrot.java
===========
public interface Parrot {
	void sound();
}

Animal.java
===========
public abstract class Animal implements Parrot {
	@Override
	public void sound() {
		System.out.println("Woof, Woof");
	}
}

Bird.java
=========
public abstract class Bird implements Parrot {
	@Override
	public void sound() {
		System.out.println("Cock-a-doodle-doo");
	}
}

Dog.java
========
public class Dog extends Animal {
	public void sound() {
		super.sound();
	}
}

Cat.java
========
public class Cat extends Animal {
	public void sound() {
		System.out.println("Meow, Meow");
	}
}

Rooster.java
============
public class Rooster extends Bird {
	public void sound() {
		super.sound();
	}
}

Duck.java
=========
public class Duck extends Bird {
	public void sound() {
		System.out.println("Quack, Quack");
	}
}

MainClass.java
==============
public class MainClass {
	public static void main(String[] args) {
		Parrot[] parrot = new Parrot[4];
		parrot[0] = new Dog();
		parrot[1] = new Cat();
		parrot[2] = new Rooster();
		parrot[3] = new Duck();
		for (Parrot p : parrot) {
			p.sound();
		}
	}
}
