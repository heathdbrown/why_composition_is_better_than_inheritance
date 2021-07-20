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
