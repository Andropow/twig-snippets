# Collection of D8 Twig Snippets

## Basics

```
# print variable 
I am {{ hamburgers }}
``` 

```
# print hashed variable 
{{ content.body['#view_mode'] }}
``` 

```
# string together
{{ 'I am ' ~ var.something }}
``` 

```
# set a variable
{% set var = content.string %}
``` 

```
# set array
{% set myarray = {'acorn': 'awesome', 'fudge': 'better'} %}
``` 

## Comparison & Control  

```
#  foreach loop for myarray
{% for arrayfor in myarray %} {% endfor %}
``` 

```
#  or
{% if (a or b) %} {% endif %} 
```

```
#  and
{% if (a and b) %} {% endif %} 
```

```
# if conditional
{% if myarray %} {% endif %}
``` 

```
#  not empty 
{% if myarray is not empty %} {% endif %}
``` 

```
#  isset 
{% if myarray is defined %} {% endif %}
``` 

```
#  !isset
{% if myarray is not defined %} {% endif %}
``` 

```
#  greater than 
{% if myarray.length > 0 %} {% endif %} 
```
 
```
#  starts with 
{% if 'Fudge' starts with 'F' %} {% endif %}
``` 

```
#  ends with 
{% if 'Funky' ends with 'y' %} {% endif %}
``` 


```
#  contained within  
{{ 1 in [1, 2, 3] }}
{{ 'cd' in 'abcde' }}
``` 


```
#  ternary 
{{ funky ? 'yes' : 'no' }} 
``` 


```
#  regex 
{% if numbers matches '/^[\\d\\.]+$/' %} {% endif %}
``` 



## Functions & Filters

```
#  check_plain 
{{ myarray.acorn|striptags }} 
``` 

```
#  translate 
{{ myarray.acorn|t }} 
{{ 'Hello @acorn'|t({ '@acorn': myarray.acorn }) }}
``` 

```
#  implode array of strings, done automatically in D8 twig 
{{ myarray }}
``` 


```
#  safe join 
{{ [1, 2, 3]|safe_join('|') }} is 1|2|3
``` 

```
#  escape 
{{ user.username|escape }}
``` 

```
#  filter proper class
<div class="icon-{{ item.title|clean_class }}" >
``` 

```
#  filter proper id
<div id="icon-{{ item.title|clean_id }}" >
``` 

```
#  title
{{ 'the apple is green'|title }}
``` 

```
#  capitalize
{{ 'how are you'|capitalize }}
``` 

```
#  lowercase
{{ 'HOWDY'|lower }}
``` 

```
#  uppercase
{{ 'howdy'|upper }}
``` 

```
#  without 
{{ content|without('links') }} // removes content.links
``` 

```
#  date 
{% if date(user.created_at) < date() %} {% endif %} 
``` 

```
#  default 
{{ var|default('var is not defined') }}
``` 

```
#  length  
{% if users|length > 10 %} {% endif %}
``` 

```
#  trim: whitespace or chars  
{{ '  I like Twig.'|trim('.') }}
``` 


```
#  merge: add to array 
{% set values = values|merge(['cat', 'dog']) %} 
``` 

```
#  nl2br converts to <br>
{{ "Let us have apples\nIt will be great"|nl2br }} 
``` 

```
#  number_format
{{ 9800.333|number_format(2, '.', ',') }}
``` 



## Debug & Searching

```
#  using kint in twig file 
{{ kint(page.content) }}
``` 

```
#  print variable
{{ dump(var) }}
``` 

```
#  print all variables
{{ dump(_context) }}
``` 

```
#  print only keys 
{{ dump(_context|keys) }}
``` 

```
#  print formatted keys or value 
{% for key, value in _context %}
 <li>{{ key }}</li>
{% endfor %}
``` 



## Common Workflows

```
#  add new class to attributes array 
{% set classes = ['region-' ~ region|clean_class] %}
<div{{ attributes.addclass(classes) }}>
``` 




## Misc References

[Drupal-defined Twig Filters](https://api.drupal.org/api/drupal/core%21lib%21Drupal%21Core%21Template%21TwigExtension.php/function/TwigExtension%3A%3AgetFilters/8)

