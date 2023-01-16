# Generating Random Number

## How To Generate a Random Number

In Java, there is three-way to generate random numbers using the method and classes.

- Using the **random()** Method
- Using the **Random** Class
- Using the **ThreadLocalRandom** Class

### Using the Math.random() Method

The Java **Math** class has many methods for different mathematical operations. One of them is the **random()** method. It is a **static** method of the Math class. We can invoke it directly. It generates only **double** type random number **greater than or equal to 0.0** and **less than 1.0**. Before using the random() method, we must import the `java.lang.Math` class.

**Syntax**:

```java
public static double random();
```

It does not accept any parameter. It returns a pseudorandom double that is greater than or equal to 0.0 and less than 1.0.

### RandomNumberExample1.java

Let’s create a program that generates random numbers using the random() method.

```java
import java.lang.Math;

public class RandomNumber {
	public static void main(String[] args) {
	// Generating random numbers
	System.out.println("1st Random Number: " + Math.random());
	System.out.println("2nd Random Number: " + Math.random());
	System.out.println("3rd Random Number: " + Math.random());
	System.out.println("4th Random Number: " + Math.random());
	}
}
```

### RandomNumberExample2.java

We can also use the following formula if we want to generate random number between a specified range.

```java
Math.random() * (max - min + 1) + min
```

In the above formula, the min value is inclusive while the max value is exclusive.

Let’s create a program that generates random numbers between 200 to 400.

```java
public class RandomNumber {
	public static void main(String[] args) {
	int min = 200;
	int max = 400;

	// Generate random double value from 200 to 400
	System.out.println("Random value of type double between "+min+" to "+max+":");
	double a = Math.random()*(max-min+1)+min;
	System.out.println(a);

	// Generate random int value from 200 to 400
	System.out.println("Random value of type double between "+min+" to "+max+":");
	int b = (int)(Math.random()*(max-min+1)+min);
	System.out.println(b);
	}
}
```

### Using the Random Class

Another way to generate a random number is to use the **Java Random class** of the `java.util` package. It generates a stream of pseudorandom numbers. We can generate a random number of any data type, such as integer, float, double, Boolean, long. If you are going to use this class the generate random numbers, follow the steps given below:

- First, import java class `java.lang.Random`
- Create an **object** of the Random class
- Invoke any of the following methods:
- **nextInt(int bound)**
- **nextInt()**
- **nextFloat()**
- **nextDouble()**
- **nextLong()**
- **nextBoolean()**

All the above methods return the next pseudorandom, homogeneously distributed value (corresponding method) from this random number generator’s sequence. The **nextDouble()** and **nextFloat()** method generates random value between 0.0 and 1.0.

The **nextInt(int bound)** method accepts a parameter bound (upper) that must be positive. It generates a random number in the range 0 to bound-1.

### RandomNumberExample3.java

Let’s create a program that generates random numbers using the Random class.

```java
import java.util.Random;

public class RandomNumberExample3 {
	public static void main(String args[]) {
		// creating an object of Random class
		Random random = new Random();

		// Generates random integers 0 to 49
		int x = random.nextInt(50);

		// Generates random integers 0 to 999
		int y = random.nextInt(1000);

		// Prints random integer values
		System.out.println("Randomly Generated Integers Values");
		System.out.println(x);
		System.out.println(y);

		// Generates Random doubles values
		double a = random.nextDouble();
		double b = random.nextDouble();

		// Prints random double values
		System.out.println("Randomly Generated Double Values");
		System.out.println(a);
		System.out.println(b);

		// Generates Random float values
		float f=random.nextFloat();
		float i=random.nextFloat();

		// Prints random float values
		System.out.println("Randomly Generated Float Values");
		System.out.println(f);
		System.out.println(i);

		// Generates Random Long values
		long p = random.nextLong();
		long q = random.nextLong();

		// Prints random long values
		System.out.println("Randomly Generated Long Values");
		System.out.println(p);
		System.out.println(q);

		// Generates Random boolean values
		boolean m=random.nextBoolean();
		boolean n=random.nextBoolean();

		// Prints random boolean values
		System.out.println("Randomly Generated Boolean Values");
		System.out.println(m);
		System.out.println(n);
	}
}
```

### Using the ThreadLocalRandom Class

The **ThreadLocalRandom** class is defined in `java.util.concurrent` package. It is initialized with an internally generated seed, the same as the random generator of the Math class. It cannot be modified. We can use this class in the following way:

```java
ThreadLocalRandom.current().nextX(...)
```

Where X is Int, Long, etc.

**Note**: It is impossible to share a ThreadLocalRandom with multiple threads accidentally.

We can generate a random number of any data type, such as integer, float, double, Boolean, long. If you are going to use this calls to generate random numbers, follow the steps given below:

- First, import the class by using `java.util.concurrent.ThreadLocalRandom`
- Invoke the corresponding method for which you want to generate numbers randomly
- **nextInt()**
- **nextDouble()**
- **nextLong()**
- **nextFloat()**
- **nextBoolean()**

All the above methods override the corresponding method of the Random class and return the corresponding value.

- **nextInt(int bound)**
- **nextDouble(int bound)**
- **nextLong(int bound)**

The above methods parse a parameter **bound** (upper) that must be **positive**. It returns corresponding randomly generated value between 0 (inclusive) and the specified bound (exclusive). It throws **IllegalArgumentExecetion** if the bound is negative

- **nextInt(int origin, int bound)**
- **nextDouble(int origin, int bound)**
- **nextLong(int origin, int bound)**

The above methods parse two parameters **origin** and **bound**. The origin specifies the **least value** returned and the bound specifies the **upper bound**. It returns corresponding randomly generated value between the specified origin (inclusive) and the bound (exclusive). Also, throws **IllegalArgumentExecetion** if the origin is greater than or equal to bound.

### RandomNumberExample4.java

Let’s create a program that generates random numbers using the **ThreadLocalRandom class**.

```java
import java.util.concurrent.ThreadLocalRandom;

public class RandomNumberExample4 {
	public static void main(String args[]) {

		// Generate random integers between 0 to 999
		int a = ThreadLocalRandom.current().nextInt();
		int b = ThreadLocalRandom.current().nextInt();

		// Print random integer values
		System.out.println("Randomly Generated Integer Values:");
		System.out.println(a);
		System.out.println(b);

		// Generate Random double values
		double c = ThreadLocalRandom.current().nextDouble();
		double d = ThreadLocalRandom.current().nextDouble();

		// Print random doubles
		System.out.println("Randomly Generated Double Values:");
		System.out.println(c);
		System.out.println(d);

		// Generate random boolean values
		boolean e = ThreadLocalRandom.current().nextBoolean();
		boolean f = ThreadLocalRandom.current().nextBoolean();

		// Print random Booleans
		System.out.println("Randomly Generated Boolean Values:");
		System.out.println(e);
		System.out.println(f);
	}
}
```
