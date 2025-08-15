What is YAML?
Why is YAML?

Data serialization

If data is not particlaur format. Then it is diffcult to process. Here is where templating language like JSON/YAML comes into play.


Standard Template Language - JSON / YAML

muni.yaml

```yaml
---
name: muni
age: 25
work: true
task:
  - meetings
  - work
  - study
address:
  street: 509 Madhanur
  district: Krishnagiri
  pin: 635123
```


# Understanding YAML

YAML (YAML Ain't Markup Language) is a human-readable data serialization format that is commonly used for configuration files and data exchange between languages with different data structures.

## YAML Syntax

### Strings, Numbers and Booleans:

```yaml
---
string: Hello, World!
number: 42
boolean: true
```

### List 

```yaml
---
fruits:
  - Apple
  - Orange
  - Banana
```

### Dictionary 

```yaml
---
person:
  name: John Doe
  age: 30
  city: New York
```

### List of dictionaries 

YAML allows nesting of lists and dictionaries to represent more complex data.

```yaml
---
family:
  parents:
    - name: Jane
      age: 50
    - name: John
      age: 52
  children:
    - name: Jimmy
      age: 22
    - name: Jenny
      age: 20
```