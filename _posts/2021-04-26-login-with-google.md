---
layout: post
title: login with google
date: 2021-04-26
---

today i learned how to add "login with google" functionality to a flask app. this required several dependencies:

* defining authorized uris. i used `https://127.0.0.1:5000` for javascript and added a callback endpoint defined in the flask app as a redirect uri
* new authentication libraries
    - oauthlib
    - pyOpenSSL
    - Flask-Login
* changing the `ssl_context` parameter of the flask app, which must be `'adhoc'`
* running the app using `python app.py` instead of `flask run` 
* informing my browser that i do in fact understand the risks involved in visiting this website every time i load the app