## Classes
Classes: expands the concept of Struct
- Only Real difference: access privilege

## Access Modifiers
### Public members
can be accessed by all classes
### Private members
only
### Constructor
##### Copy Constructors

## Inheritance
Classes can inherit from other classes
- Enhance existing classes
- Reusability
- If you have classes that share characteristics and reuse an specific behavior save time by placing them in a base class
- Derived classes are usually BIGGER than its base class

```
class Derived : public Base
{
  public:
    new member functions;
    new data members;
  private:
    new member functions;
    new data members;
};
```
The `public`  keyword in the first line allows us to access base members from derived: `derived.basemember = x;`

### Calling Base Constructor
Calling the base constructor from the derived class:
```
Derived::Derived(parameters):Base(parameters)
{...}
```
calls the Base constructor before executing the `{...}`
Even if we don't explicitly type it the base constructor is called

### Shadowing
```
class Base{
  method1();
  int x;
};

class Derived:public Base{
  method1();
  int x;
};

Derived.method1(); // Now which one is it calling?
// derived's method1()
```

### Virtual

The virtual keyword indicates to the compiler that it should choose the appropriate definition of f() not by the type of reference, but by the type of object that the reference refers to.

Virtual needs to be added to the method in the
Base class, and then you may or may not add it
to the Derived classes (for common practice, you
  should).
