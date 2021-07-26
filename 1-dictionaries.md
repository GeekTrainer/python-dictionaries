# Python dictionaries

Python dictionaries allow you to work with more complex data structures. A dictionary is a collection of key/value pairs. You can almost think about it like a group of variables inside of a container. Dictionaries are useful when you have multiple pieces of data related to one another, like a name and age for a person, or a date, rainfall and temperature for a weather reading.

## Creating a dictionary

Python uses curly braces (`{ }`) to denote a dictionary. You can either create an empty dictionary and add values later, or seed it at creation time. Each key/value is separated by a colon, and the name of each key is contained in quotes as a string literal.

```python
person = {
    'name': 'Christopher',
    'age': 42
}
```

Notice the `age` value of `42` in the example above. When setting the values in a dictionary, you need to ensure the datatype is correct. As stored above, `age` will be a number. If you had used `'42'`, with the value in quotes, it would be stored as a string.

## Reading dictionary values

You can read values inside a dictionary. Dictionary objects have a `get` method which can be used to access a value by using its key. If you wanted to print the `name`, you could use the following code:

```python
print(person.get('name'))

# Displays Christopher
```

As you might suspect, accessing values in a dictionary is a common operation. As a result, there's a shortcut. You can also pass the key into what's known as the index operator, or square brackets (`[ ]`). This uses less code than `get`, and most programmers use this syntax instead. You could rewrite the example above by using the following:

```python
# person['name'] is identical to using person.get('name')
print(person['name'])

# Displays Christopher
```

## Modifying dictionary values

Values inside a dictionary object can also be modified. You can perform this action by using the `update` method. `update` accepts a dictionary as a parameter, and will update any existing values with the new ones you provide. If you wished to change the `name` for the `person` dictionary, you could use the following:

```python
person.update({'name': 'Eisen'})

# name is now set to Eisen
```

> [!NOTE] `update` is able to modify multiple values at once by providing a dictionary with multiple updated values.

Similar to using the index operator (`[ ]`) to read values, you can also use it to modify values. The key difference in syntax is you use `=` (sometimes called the assignment operator) to provide a new value. To rewrite the example above to change the name, you could use the following:

```python
person['name'] = 'Eisen'

# name is now set to Eisen
```

## Adding and removing keys

You are not required to create all keys when initializing a dictionary. If you wish to create a new key, you can assign it just as you would an existing one. You could use the following to add a new property named `home_city` to `person`:

```python
person['home_city'] = 'Seattle'

# person dictionary now contains: {
#   name: 'Eisen'
#   age: 42
#   home_city: 'Seattle'
# }
```

> [!IMPORTANT] Key names, like everything else in Python, is case sensitive.

To remove a key, you use `pop`. `pop` will return the value and remove the key from the dictionary. To remove `home_city`, you can use the following code:

```python
person.pop('home_city')

# person dictionary now contains: {
#   name: 'Eisen'
#   age: 42
# }
```

## Complex data types

Dictionaries are able to store any type of a value, including other dictionaries. This allows you to model complex data as needed. Imagine needing to store an `address` for the `person` with a `city` and `country`. You could add a new dictionary to the existing one just as you would a normal value.

```python
# Add address
person['address'] = {
    'city': 'Osaka',
    'country': 'Japan'
}

# person dictionary now contains: {
#   name: 'Eisen'
#   age: 42
#   address: {
#      city: Osaka
#      country: Japan
#   }
# }
```
