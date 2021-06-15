---
layout: post
title: whats in a name
date: 2021-06-14
---

today i learned some naming conventions in python.

```python
def this_is_a_public_function():
	print('it lives outside a class')
	print('it is accessible from anywhere')

def _this_is_a_protected_method():
	print('it lives inside a class')
	print('it is accessible from any class derived from it')

def __this_is_a_private_method():
	print('it lives inside a class')
	print('it is only accessible from within the class')

```