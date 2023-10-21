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

##### Iterating Over Objects

Objects in JS are not iterable in the same way that arrays are. Instead a ```for...in``` statement is needed.

The for loop will return key values within the object. For example:

```
var planetMoons = {
  mercury: 0,
  venus: 0,
  earth: 1,
  mars: 2,
  jupiter: 67,
  saturn: 62,
  uranus: 27,
  neptune: 14
};

for (var planet in planetMoons) {
  var numberOfMoons = planetMoons[planet];
  console.log("Planet: " + planet + ", # of Moons: "+ numberOfMoons);
}

> Planet: mercury, # of Moons: 0
> Planet: venus, # of Moons: 0
> Planet: earth, # of Moons: 1
> Planet: mars, # of Moons: 2
> Planet: jupiter, # of Moons: 67
> Planet: saturn, # of Moons: 62
> Planet: uranus, # of Moons: 27
> Planet: neptune, # of Moons: 14
```

Objects can sometimes have properties that they inherit from their prototype chain. Sometimes a filtering step is necessary.

```
for (var planet in planetMoons) {
  // additional filter for object properties:
  if (planetMoons.hasOwnProperty(planet)) {
    // ...
  }
}
```