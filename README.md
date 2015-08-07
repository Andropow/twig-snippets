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
# set a variable
{% set var = content.string %}
``` 

```
# set array
{% set myarray = {'acorn': 'awesome', 'fudge': 'better'} %}
``` 

## Comparison & Control  

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
#  foreach loop for myarray
{% for arrayfor in myarray %} {% endfor %}
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





