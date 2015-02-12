// [TODO] Populate this area with notes about pointer from earlier lectures
```
int a,b,c,d // valid
int* a,b,c,d // not valid
```

## Smart Pointer
Wraps a C++ pointer.
```
class Base{
public:
  void DoSomething(){
    //...
  }
}

int main(){
  std::shared_ptr<Base> base(new Base());
  base->DoSomething();
  return 0; 
  // When it gets to the end of scope, it calls the destructor of shared_ptr, which deletes the pointer.
}
```
Internally, the shared_ptr is managing memory for you!
### So smart! Why don't we just use smart pointers All the Time!

Um... it gets... complicated? `// [HELP]`

Shared pointers have more complex behavior, so to use them, the programmer has to know what it's doing internally.

#### Maybe it's called Smart Pointer because you have to be smart to use it. `ba dum tss`
