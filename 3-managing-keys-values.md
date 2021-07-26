# Dynamic dictionary management

In programming you frequently create objects using a pre-defined class or blueprint. With dictionaries you are creating an object dynamically; keys and datatypes are not established in advance. You may find yourself in a position of not knowing the structure of a dictionary if you are reading information from an external source, such as a text file. Fortunately Python provides a series of methods you can ues to explore keys and values inside a dictionary.

## Retrieve all keys and values

The `keys()` method returns a list object containing all the keys. You can use this to iterate through all items or determine if a key exists in a dictionary.

Imagine you have the following dictionary storing the last three months of rainfall.

```python
rainfall = {
    'october': 3.5,
    'november': 4.2,
    'december': 2.1
}
```

Let's say you want to display the list of all rainfall. While you could type out each month name, this would become tedious.

```python

for key in rainfall.keys():
    print(f'{key}: {rainfall[key]}cm')

# Output:
# october: 3.5cm
# november: 4.2cm
# december: 2.1cm
```

> [!NOTE] You can still use the index operator (`[ ]`) with a variable name rather than the hard-coded string literal.

## Retrieve all values

Similar to `keys()`, `values()` returns the list of all values in a dictionary **without** their respective keys. This can be helpful in scenarios where the key is used for labeling purposes, such as the example above where the keys are the name of the month, but you need to perform operations on all the values. You could use `values()` to determine the total rainfall amount:

```python
total_rainfall = 0
for value in rainfall.values():
    total_rainfall = total_rainfall + value

print(f'There was {total_rainfall}cm in the last quarter')

# Output:
# There was 9.8cm in the last quarter
```
