# Working Collection of Twig Snippets for D8

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
# if conditional
{% if myarray %} {% endif %}
``` 

```
#  not empty 
{% if myarray is not empty %} {% endif %}
``` 

```
#  isset() 
{% if myarray is defined %} {% endif %}
``` 

```
#  comparison 
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




