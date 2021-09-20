---
layout: post
title: cd/cd
date: 2021-09-19
---

i did not know that continuous delivery and continuous deployment were different concepts. i thought that they were two different names (with the same abbreviation) for the same process.

now that i know the difference, i can see that i've been using continous deployment in dev. every time i merge a branch into main, the automated test suite runs. if the tests pass, the branch is automatically deployed to the dev environment.

for production, i deploy using continous delivery. the latest build in dev is pushed to production after manually selecting a bunch of settings and clicking a button. again, the automated tests must pass in order for the deployment to proceed. the difference is that a human must trigger this process manually.

the difference is subtle, but important. too much is at stake for continous deployment to production. an outage in dev may be annoying, but will not affect the bottom line.

