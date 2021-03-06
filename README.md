# why_composition_is_better_than_inheritance
> https://www.youtube.com/watch?v=0mcP8ZpUR38

Github: https://github.com/ArjanCodes/2021-composition-vs-inheritance

Python: https://docs.python.org/3/library/abc.html

🔖 Chapters:
- 0:00 Intro
- 1:11 Explanation of the example
- 3:57 Technique #1: inheritance
- 8:30 Problems with the inheritance technique
- 10:02 Technique #2: composition
- 18:48 Improvement: turn Commission into an abstract class
- 20:03 Limitations of this example
- 21:29 Final thoughts

# Definitions

abstract base class https://docs.python.org/3/glossary.html#term-abstract-base-class

https://docs.python.org/3/library/abc.html

Abstract base classes complement duck-typing by providing a way to define interfaces when other techniques like hasattr() would be clumsy or subtly wrong (for example with magic methods). ABCs introduce virtual subclasses, which are classes that don’t inherit from a class but are still recognized by isinstance() and issubclass(); see the abc module documentation. Python comes with many built-in ABCs for data structures (in the collections.abc module), numbers (in the numbers module), streams (in the io module), import finders and loaders (in the importlib.abc module). You can create your own ABCs with the abc module.

# Composition vs Inheritance

Composition: using the 'has a' relationship
```python
from abc import ABC, abstractmethod
from dataclasses import dataclass
from typing import Optional


@dataclass
class Commission:
  amount: int

@dataclass
class Contract:
  id: int

@dataclass
class Employee:
   id: int
   name: str
   commission: Optional[Commision]
   contracts: Optional[Contract]
```

Inheritance: using the 'is a' relationship
```python
from dataclass import Dataclass
from abc import ABC, abstractmethod

@dataclass
class Employee(ABC):
  id: int
  name: str
  commission: int
  contract: int
  
@dataclass
class SalariedEmployee(Employee):

@dataclass
class SalariedEmployeewithCommission(SalariedEmployee):

```
