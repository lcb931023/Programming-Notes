# Classes
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

### Polymorphism

Describes a set of objects of different classes with similar behavior.

#### Slicing

If you create a vector of a base class: `vector<Base> vectorBase;`

The compiler realize that a Derived class is a special case of the base and lets you add objects to it, but
all the members of Derived that are not contained in Base are sliced away.
```
// Assume Mage and Soldier inherits Human
// Human has HP and Attack
// Mage has MP
Human* oNPC = new Mage();
oNPC -> MP; // Won't find it
```
In order to avoid this slicing we can use a vector
of pointers, as in essence all pointers are of the
same size.
```
vector<Base*> vectorBase;
vectorBase[0] = new Base();
vectorBase[1] = new Derived1();
vectorBase[2] = new Derived2();
```
To work around slicing, we use `dynamic_cast<BaseClassName>()`
- BaseClassName can also be pointers, references, etc.

## Rule of Three

If a class defines one of the following it should declare the other:
- **Destructor** – Calls the destructors of the
object’s class type member.
- **Copy Constructor** – Constructs object’s data
members and assigns all non-class type data
members to the corresponding argument
object’s data member.
- **Copy Assignment Operator** – Assigns all nonclass
type data members to the corresponding
argument object’s data member.

Or, in Human-readable words:

- **Destructor** – Destroys the members.
- **Copy Constructor** – Constructs members and
copy corresponding argument members.
- **Copy Assignment Operator** – Copy
corresponding argument members

### Rule of Five

**C++11**'s extension to the Rule of Three. lets the programmer grab data (copy and delete) from temporary objects.

- **Copy Assignment Operator**: Construct and Copy
- **Move Assignment Operator**: Copy

## Friend

Friend functions are an extension of the
class interface.

Member functions are called like `foo.f();`

Friend functions are called like `f();`

#### Inheriting

friend can not be virtual thus “no dynamic
binding is possible”

#### Virtual Friend Idiom

Dynamic binding is possible through an
intermediary function.
To get the effect of a “virtual friend” the
friend function should call a protected virtual
member function
