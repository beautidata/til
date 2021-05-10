---
layout: post
title: declarative mapping
date: 2021-05-09
---

a couple of days ago sqlalchemy introduced some [changes](https://pypi.org/project/SQLAlchemy/1.4.14/). declarative mapping is now the term to use when referring to many former declarative extensions. as opposed to imperative mapping, which is what we are now calling the former classical style of mapping configuration. declarative mapping is typically used with a `declarative_base()` class, but it can also be used with a decorator.