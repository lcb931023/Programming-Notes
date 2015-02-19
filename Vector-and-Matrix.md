# Vector

## What's a Vector?

In Latin: one who carries or conveys, carrier.
Takes something from *here* to *there*

In Math: A set of values that describe **relative position in space**.

## Components

**Direction**: Heading, Rotation

**Magnitude**: Distance, Reach, Force

## Use

Vectors are great for all the operations for moving things around the screen.

- Position vector
- Velocity vector
- Acceleration vector
- Heading vector: normalized unit vector, direction

## Operations

#### Normalizing Vectors

Making a vector "*normal*" by setting its magnitude to 1, for ease of use

#### Addition

```
// c = a + b
c = (a.x + b.x, a.y + b.y)
```

#### Subtraction

```
// c = a + b
// b = c - a
b = (c.x - a.x, c.y - a.y)
```
The direction of the result depends on the order of subtraction
```
-b = (a.x - c.x, a.y - c.y)
```

#### Multiplication / Division
Multiply / Divide the magnitude by the scalar



# Matrix

![Matrix](http://static3.businessinsider.com/image/5076d50becad045713000011/master-ita-softwares-matrix-to-book-your-next-dream-trip.jpg)

...No.

## What?

Rectangular array of numbers / symbols / expressions.

### Anatomy

Arranged in *rows* and *columns*, like a bi-dimentional array
Individual items are called *entries*.
```
// e.g. identity matrix
/1 0 0\
|0 1 0|
\0 0 1/
```
## Why Do I Care?

Because **Vector Space**: Basically the space in which your vectors live and can operate.
AKA *Coordinate System*.

## Operations

#### Addition

#### Subtraction

#### Multiplication

###### ^[TODO]





# Vector To Matrix

To use matrix operation on vectors, We can represent the vector ( x, y ) in the matrix form:
```
[𝑥]
[𝑦]
// A 1 by 2 matrix
```
### 2D to 3D
```
[1 0] * [1]
[0 1]   [1]
is basically
[1 0 0]   [1]
[0 1 0] * [1]
[0 0 1]   [0]

```

## Operation
```
[3] + [2] = [5]
[2] + [2] = [4]
[0] + [0] = [0]
```

### Multiplication Vs Addition

Need a multiplication to have linear combination

#### Messing with Diagonals
```
A(1,1) // starting point
B // translation
A'(2,2) // result

A + B = A'
A + B – A = A’ – A
A – A + B = A’ – A
B = A’ – A

B = [2] - [1]
		[2] - [1]

B = [1]
		[1]
```
Modifying the diagonal of the matrix will not give
us the translation, but the SCALING.

How about Scaling Rotation and Translation?

[TODO]

### Rotations

// These damn matrixes. I'll need to use LaTeX for this section.
