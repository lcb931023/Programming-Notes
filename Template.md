# Templates

`//sidenote: #pragma region and #pragma endregion can be used to organize code better in visual studio`

Template deals with Generic types.

Instead of writing:
```
float GetMaxFloat(float a, float b)
{
  return (a>b?a:b);
}
int GetMaxInt(int a, int b)
{
  return (a>b?a:b);
}
```

You can just write:
```
template <class T>
T GetMax (T a, T b)
{
  return (a>b?a:b);
}
```

Neat!

However, this will return an error:
```
int pA = 1;
float pB = 2;
GetMax (pA, pB); // <T> is different now
```

To fix this, we can just use two different class variable names in Template
```
template <class T, class U>
T GetMax (T a, U b)
{
  // ...
}
```

## Wow, that's amazing! How did it do this?

Internally, compiler checks for places the templated functions are called, and then substitute `T` with whatever variable type it is.

## Multiple Templates
```
template <class T>
T GetMax //...
//...

template <class T. class U>
T GetMax //...
//...

Getmax<float>( pA, pB ); // Compiler picks the first template
// Help Alberto I didn't catch this part
```

## Templates with Class Inheritance

```
class Foo // ...
class Bar : public Foo //...
template <class T> //...
template <class T, class U> //...
```
When we call:
```
Foo foo;
Bar bar;
GetMax(foo, bar);
```
Compiler will use `template <class T>` and set `T` to `Foo`
