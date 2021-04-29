---
layout: post
title: incompatibility hacks
date: 2021-04-28
---

today i learned about more tools that don't play nice together.

i want to deploy my flask app to a google compute instance. so i thought that might be easier to do with a docker container. but my app is served over localhost, which is not accessible from outside the docker container. so i had to bind the flask app to the host `0.0.0.0`. then i was able to view the app from my browser, but the login with google functionality broke. 

google has good reasons to not like an ip addresses to be exposed like that, but it makes testing locally during development more difficult. luckily someone on [stack overflow](https://stackoverflow.com/questions/10215863/why-is-google-oauth-returning-invalid-redirect-uri-in-my-rails-app) shared a hack.

i edited my `/etc/hosts` file to add the following line:

```
0.0.0.0		flask		flask.testing.com
```

then i added `https://flask.testing.com:5000/login/callback` to my authorized redirect uri list in google oauth credentials. when the app was served up at `https://0.0.0.0:5000/` i entered `https://flask.testing.com:5000/` in my browser and was able to successfully login with google.

score!

