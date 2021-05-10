---
layout: post
title: coalescing
date: 2021-05-10
---

today i learned about a command in sql i had never used before. 

```sql
SELECT COALESCE(NULL, NULL, variable_name, False);
```

this returns the first non-null value out of the list of input parameters. in the example above, the query will return the value of `variable_name` if it evaluates to `NULL` and `False` if `varible_name` evaluates to `NULL`.