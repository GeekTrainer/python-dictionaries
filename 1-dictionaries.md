# Python dictionaries

Imagine an application built to work with information about people, let's say a name and an age. If you were writing the code to work with a single person, you might create variables which look like the following:

```python
name = 'Christopher'
age = 42
```

While this would work well for one person, things become more complex when you start adding variables for two or more people:

```python
christopher_name = 'Christopher'
christopher_age = 42

eisen_name = 'Eisen'
eisen_age = 37
```

Notice how you now have duplicated variables with different prefixes. After a little while this becomes unwieldy. You will frequently find yourself working with related sets of data, like information demographic information about a person or average rainfall for different months in different cities. Storing those as individual values isn't a viable option. This is where Python dictionaries can help.

Python dictionaries allow you to work with related sets of data. A dictionary is a collection of key/value pairs. You can almost think about it like a group of variables inside of a container, where the key is the name of the variable, and the value is the value stored inside it.

## Creating a dictionary

Python uses curly braces (`{ }`) to denote a dictionary. You can either create an empty dictionary and add values later, or populate it at creation time. Each key/value is separated by a colon, and the name of each key is contained in quotes as a string literal. Because the key is a string literal, you can use whatever name is appropriate to describe the value.

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

There is no difference between calling `get` or using the index operator (`[ ]`) to retrieve a value beyond syntax. You will find most developers use the index operator.

## Modifying dictionary values

Values inside a dictionary object can also be modified. You can perform this action by using the `update` method. `update` accepts a dictionary as a parameter, and will update any existing values with the new ones you provide. If you wished to change the `name` for the `person` dictionary, you could use the following:

```python
person.update({'name': 'Eisen'})

# name is now set to Eisen
```

Similar to using the index operator (`[ ]`) to read values, you can also use it to modify values. The key difference in syntax is you use `=` (sometimes called the assignment operator) to provide a new value. To rewrite the example above to change the name, you could use the following:

```python
person['name'] = 'Eisen'

# name is now set to Eisen
```

The key advantage to using `update` is the ability to modify multiple values in one operation. The two examples below are logically the same while the syntax is different. You are free to use whichever syntax you feel is most appropriate. For updating individual values, most developers will use the index operator.

```python
# Using update
person.update({
    'name': 'Eisen',
    'age': 30
})

# Using the index operator
person['name'] = 'Eisen'
person['age'] = 30
```

## Adding and removing keys

You are not required to create all keys when initializing a dictionary - in fact you don't need to create any! Whenever you want to create a new key, you assign it just as you would an existing one. You could use the following to add a new property named `home_city` to `person`:

```python
person['home_city'] = 'Seattle'

# person dictionary now contains: {
#   name: 'Eisen'
#   age: 30
#   home_city: 'Seattle'
# }
```

> [!IMPORTANT] Key names, like everything else in Python, is case sensitive. As a result, `'name'` and `'Name'` would be seen as two separate keys in a Python dictionary.

To remove a key, you use `pop`. `pop` will return the value and remove the key from the dictionary. To remove `home_city`, you can use the following code:

```python
person.pop('home_city')

# person dictionary now contains: {
#   name: 'Eisen'
#   age: 30
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
#   age: 30
#   address: {
#      city: Osaka
#      country: Japan
#   }
# }
```

To retrieve values in a nested dictionary, you chain together the index operators or calls to `get`.

```python
print(f'{person['name']} lives in {person['address']['city']}')

# Output: Eisen lives in Osaka
```
