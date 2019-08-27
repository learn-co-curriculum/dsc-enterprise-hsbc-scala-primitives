
# Primitive Types

## About Primitive Types

* All primitives are that of the JVM (`byte`, `short`, etc.)
* JVM primitives are used as objects in Scala.
* At compile time, depending on the use, may compile to a primitive or an object.

## `Byte`

A byte is an 8 bit number, which is the same in Java.

The maximum for each number in the JVM is defined as ${2^{n-1}}-1$ where $n$ is the number of bits.

The minimum is defined as ${2^{n-1}}$

That means that the maximum size for a byte, which is 8 bits, ${2^{8−1}−1}$, or ${2^{7} - 1}$ or 127.

The minimum would be negative $2^{8−1}$, or $−{2^7}$ or -128


```scala
val b:Byte = 127
```

or if we were to employ coersion


```scala
val b = 127:Byte
```

Here we establishing a negative with the minimum size of a byte.


```scala
val b = -128:Byte
```

If you care to express yourself in hexadecimal the following is the same as 127


```scala
val b = 0x7F:Byte
```

Any increase would either be an error in form of a type mismatch or cause an overflow depending on the operation.


```scala
val maxByte:Byte = 128 //This will cause an compile time exception
val minByte:Byte = -127
```

## Short

Short being 16 bits, the maximum is $2^{16−1}−1$ or 32,767 and the minimum is ${−{2^{16−1}}}$, or -32,768


```scala
val maxShort = 32767:Short
val minShort = -32768:Short
```

## Int

`Int` being 32 bits, the maximum is $2^{32−1}−1$ or 2,147,483,647 and the minimum is $−2^{32−1}$ or -2,147,483,648


```scala
val a = 301202
```

You can be explicit. But often times this is unnecessary


```scala
val a:Int = 301202
```

## Long

64 bit and requires either the type declaration.

Maximum: ${2^{64−1}−1}$
Minimum: ${−2^{64−1}}$


```scala
val g:Long = 30010200
```

or with coersion:


```scala
val g = 30010200:Long
```

You can use an capital `L` using Java’s style


```scala
val g = 30010200L
```

a small `l` as a suffix.


```scala
val g = 30010200l
```

A small `l` looks like a `1` and can lead to confusion.

## Float and Double

Float and Doubles are IEEE 754 Standard Floating Arithmetic Values. Float with a capital `F` or small `f`.


```scala
val f = 19.0f
```


```scala
val f = 19.0F
```

## Float Exponents

Floats can also be expressed with exponents with a small e or a capital E.


```scala
val f = 93e-9F
```


```scala
val f = 93E-9F
```

## Double

Double on the other hand are the default when dealing with decimal point


```scala
val d0 = 19.0
```

You can affix a type or a capital D or a small d at the end to ensure a correct type


```scala
val d1:Double = 19.0
```


```scala
val d2 = 19.0:Double
```


```scala
val d3 = 19.0D
```


```scala
val d4 = 19.0d
```

Of course, you can also have double exponents


```scala
val d = 93.0E-9
```

## Char
Characters literals are much like java. Here is the character 'k'


```scala
val c:Char = 'k'
```

Unicode in characters, can be done with a preceding backslash u.


```scala
val c2 = '\u03B8' //theta Θ
```

## Boolean

Boolean also derive from Java


```scala
val b = true
val b2 = false
```

## Scala treats primitives like objects

Unlike Java, Scala’s primitives may be treated like objects. When calling an operation that works perfectly fine as a primitive, Scala will not box or wrap the primitive. Only when calling a method that requires an object will an object be created.

You don’t have to concern yourself how or when a wrapping occurs since the compiler will do that for you.

Consider the following statement:


```scala
1 + 4
```

In other words this operation looks just like `+` but is a method on the object `1` with a method parameter of `4`.


```scala
1.+(4)
```

Yes, there is operator overloading in Scala

## Primitive Wrappers

There are times in Scala there objects are wrapped to add functionality. For example:


```scala
-5.abs
```

If you are familiar with Java, you know that when you take the absolute value of something you require the static method call, Math.abs.

In Scala, it is in inherit part of Int through a trick called an implicit wrapper.

In this case there is an adapter called RichInt that wraps around a regular Int that provides a this method called abs among others.

Every primitive type in Scala, has a corresponding wrapper.

* `Char` there is `RichChar`
* `Boolean` there is `RichBoolean`
* `Long` there is `RichLong`, etc.

## Primitives Conclusion

All primitives works much like Java with varying differences.

Primitive assignments can be inferred by the type system, or you can add types manually as you see fit.

Primitives may be wrapped by a rich wrapper depending on which method is called

Scala primitives gives more methods and functionality than it had with Java.
