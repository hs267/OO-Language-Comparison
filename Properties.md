# Properties of OO languages

## Python
### Getters and setters…write your own or built in?


 No built-in getter and setter, but you can write your own built in. 

```python
    class P:
	
    def __init__(self,x):
	        self.__x = x
	
	    def get_x(self):
	        return self.__x
	
	    def set_x(self, x):
	        self.__x = x

	>>> from mutators import P
	>>> p1 = P(55)
	>>> p2 = P(6666)
	>>> p1.get_x()
	55

	>>> p1.set_x(1)
	>>> p1.set_x(p1.get_x()+p2.get_x())
	>>> p1.get_x()
	6667

	>>> 
	p1.x = p1.x + p2.x
```


### Backing variables?
```python
class property(object)
	 |  property(fget=None, fset=None, fdel=None, doc=None) -> property attribute
	 |  
	 |  fget is a function to be used for getting an attribute value, and likewise
	 |  fset is a function for setting, and fdel a function for del'ing, an
	 |  attribute.  Typical use is to define a managed attribute x:
	 |  class C(object):
	 |      def getx(self): return self._x
	 |      def setx(self, value): self._x = value
	 |      def delx(self): del self._x
	 |      x = property(getx, setx, delx, "I'm the 'x' property.")
	 |  
	 |  Decorators make defining new properties or modifying existing ones easy:
	 |  class C(object):
	 |      @property
	 |      def x(self): return self._x
	 |      @x.setter
	 |      def x(self, value): self._x = value
	 |      @x.deleter
	 |      def x(self): del self._x
```

### Computed properties?

* Python also provides a mechanism for blurring the distinction between these standard ways of using attributes. A computed attribute (or "managed attribute") looks like it directly accesses storage, but works like a function. 

```python
        If color is a computed attribute of object wgt, then in these statements ...
	    save_me = wgt.color
        top_edge_color = (255,) + wgt.color[1:]
```

## C#

### Getters and setters…write your own or built in?

* The accessor of a property contains the executable statements that helps in getting (reading or computing) or setting (writing) the property. The accessor declarations can contain a get accessor, a set accessor, or both. For example −

```c#
// Declare a Code property of type string:
public string Code {
   get {
      return code;
   }
   set {
      code = value;
   }
}

// Declare a Name property of type string:
public string Name {
   get {
      return name;
   }
   set {
      name = value;
   }
}

// Declare a Age property of type int:
public int Age { 
   get {
      return age;
   }
   set {
      age = value;
   }
}
```

### Backing variables?
* C# supports backing fields, which privately store data behind public methods, properties, and indexers.
### Computed properties?

```c#
// Age in dog years
public float AgeInDogYears
{
    get
    {
        float dogYearAge;
 
        if (age < 1)
            dogYearAge = 0;
        else if (age == 1)
            dogYearAge = 10.5f;
        else
            dogYearAge = 21 + ((age - 2) * 4);
 
        return dogYearAge;
    }
}
```