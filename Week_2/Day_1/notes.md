### Notes

#### Primitive Data Types

* 6 primitive data types in JS (values that are not objects)
  * undefined
  * null
  * boolean
  * string
  * number
  * symbol
* Anything other than those are Objects
  * functions, arrays, objects, etc.

##### Objects

* Contain key-value pairs
* Contain keys which are always strings (or symbols)
* Have unique keys (the same value cannot be repeated)
* Have keys point to values of any type

Objects have a literal syntax using braces {}

```
const emptyObject = {}
```

```
const tinyObject = {"size": "Tiny"}
```

Object keys are considered string by default. So the quotes around size are unnecessary.

```
const tinyObject = {size: "Tiny"}
```

The variable size is still considered a string.

Object values can be any type.

```
const myObject = {
  a: 6,       // Number
  b: "abc",   // String
  c: true,    // Boolean
  d: null,    // Null
}
```

When accessing an object property using the square brackets the key needs to be a string. Otherwise JS interprets it as a variable, which may have no value or an unintended value.

If the variable points to a string it can be used.

```
const person = { firstName: "Khurram" };
const propertyName = "firstName";
const firstName = person[propertyName];
```

Alternatively the objects values can be accessed with dot notation.

```
person.firstName
```

You can use square bracket notation to assign new values to new or existing objects.

```
const mary = { name: "Mary Sue" };
mary["name"] = "Mary Jane";
mary["age"] = 22;
```

This assigns the desired value to the keys, ```name``` and ```age```.

```Object.keys(...)``` is used to return an array of keys.

```
Object.keys(person)
> [ 'name', 'address', 'phoneNumbers' ]
```

