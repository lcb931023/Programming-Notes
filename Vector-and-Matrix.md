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

Making a vector "*normal*" by setting its magnitude to 1

	Why? Because 1 is easy to work with!

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
