---
layout: post
title: variable environments
date: 2021-04-27
---

"don't commit your authentication keys to github!" they said.

"automatically deploy your app to heroku for free!" they said.

turns out writing a flask app that uses configparser to read a `.ini` file containing sensitive data causes complications when that file does not get deployed to heroku via their github integration. this can be mitigated using environment variables:

```bash
export VARIABLE_NAME=your_sensitive_authentication_key
```

```python
import os

os.environ(VARIABLE_NAME)
```

for which heroku allows you to define custom values. none of this will help you if you are using a sqlite3 database though, for reasons [heroku explains quite clearly](https://devcenter.heroku.com/articles/sqlite3). to deploy on heroku, you need to use a postgres database.

in short:

* heroku + postgres = friends
* heroku + sqlite = enemies

i wanted to write an equation for environment variables but it wasn't clear what the components should be. i certainly learned a lot about what doesn't work today. which is arguably more useful information than what does work, in some cases.