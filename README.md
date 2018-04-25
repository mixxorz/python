# Mitch's Unofficial Python Style Guide

A Python style guide that doesn't make you think.

## Background

You can read all about it in my [blog post](#insert-blog-post-link).

## Rules
* [Readable consistency](#readable-consistency)
* [Follow PEP 8](#follow-pep-8)
* [Almost always use single quotes](#almost-always-use-single-quotes)
* [Line breaks and trailing commas](#line-breaks-and-trailing-commas)
* [Long function calls](#long-function-calls)
* [Long if statements](#long-if-statements)
* [Long comprehensions](#long-comprehensions)

### Readable consistency
Style guides are meant to enforce consistency and readability in your code base. But if being consistent sacrifices readability, then you’re better off being inconsistent.

Alas, this introduces some ambiguity. So when in doubt, follow the style guide. (Or not. It’s up to you.)

### Follow PEP 8
[Read it. Live it. Love it.](https://www.python.org/dev/peps/pep-0008/)

### Almost always use single quotes
Use single quotes unless the string itself contains single quotes. In which case, use double quotes.

Yes:
```python
error_message = 'You have done something wrong'
consolation_message = "It's okay. People make mistakes."
```

No:
```python
error_message = "You have done something wrong"
consolation_message = 'It\'s okay. People make mistakes'
```

For triple-quoted strings however, always use double quotes, c/o [PEP 8 String Quotes](https://www.python.org/dev/peps/pep-0008/#string-quotes).

### Line breaks and trailing commas
Break lists, sets, and dictionaries into multiple lines. The first item should be on the next line. Add a trailing comma.

Yes:
```python
fruits = [
    'pineapple',
    'guava',
    'banana',
    'tomato',
]

scientific_names = {
    'pineapple': 'Ananus sativus',
    'guava': 'Psidium guava',
    'banana': 'Musa paradisicum',
    'tomato': 'Lycopersican esculentum',
}
```

No:
```python
fruits = ['pineapple',
          'guava',
          'banana',
          'tomato']

scientific_names = {'pineapple': 'Ananus sativus',
                    'guava': 'Psidium guava',
                    'banana': 'Musa paradisicum',
                    'tomato': 'Lycopersican esculentum'}

```

If a list does not exceed the max line length, then it could be written in one line.

OK:
```python
fruits = ['pineapple', 'guava', 'banana', 'tomato']
```

### Long function calls
Break function calls into multiple lines if they exceed the max line length. Similar to lists.

Yes:
```python
guess_fruit(
    color='red',
    size='small',
    climate='cold',
    region='north america',
    minimum_tastiness_factor=4.3,
)
```

No:
```python
guess_fruit(color='red', size='small', climate='cold',
            region='north america', minimum_tastiness_factor=4.3)
```

If the arguments do not exceed the max line length, then you may keep the arguments in one line. No trailing comma. The closing parenthesis must be on the same level as the opening parenthesis.

OK:
```python
guess_fruit(
    color='red', size='small', climate='cold', region='north america'
)
```

No:
```python
guess_fruit(
    color='red', size='small', climate='cold', region='north america')

guess_fruit(
    color='red', size='small', climate='cold', region='north america',
)  # No trailing comma
```

### Long if statements
Break long if statements similar to long function calls. [Break before operators](https://www.python.org/dev/peps/pep-0008/#should-a-line-break-before-or-after-a-binary-operator).

Yes:
```python
if (
    fruit.color == 'red'
    and fruit.size == 'small'
    and fruit.climate == 'cold'
    and fruit.region == 'north america'
):
    pass

if (
    fruit.color == 'red' and fruit.size == 'small' and fruit.climate == 'cold'
):
    pass
```

No:
```python
if (fruit.color == 'red'
        and fruit.size == 'small'
        and fruit.climate == 'cold'
        and fruit.region == 'north america'):
    pass

if (
    fruit.color == 'red' and fruit.size == 'small' and fruit.climate == 'cold'
    and fruit.region == 'north america'
):
    pass
```

### Long comprehensions
Break long list, set, and dictionary comprehensions into multiple lines. The first line should be the for statement.

Yes:
```python
best_fruits = [
    f for f in fruits
    if f.color == 'red'
    and f.size == 'small'
    and f.climate == 'cold'
]
```

_1.0.0 (2018-04-25)_
