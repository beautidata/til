---
layout: post
title: initializing instances
date: 2021-04-29
---

today i learned how to initialize a google compute engine instance with the minimal software needed to run my flask app.

in order to get my code from github onto this instance, i'll need to install git:

```bash
sudo apt install git-all
```

in order to clone my repository, i need a new ssh key.

```bash
ssh-keygen -t rsa
```

accept the default option for location and passphrase. to view the public key:

```bash
vi ~/.ssh/id_rsa.pub
```

on github, navigate to settings > ssh and gpg keys > new ssh key, and copy the contents of `id_rsa.pub` into your new ssh key. then navigate to the `~` directory and clone the repository:

```bash
git clone git@github.com/beautidata/flaskalicious.git
```

next install pip.

```bash
sudo apt update
sudo apt -y upgrade
sudo apt install python3-pip
```

navigate to `~/flaskalicious/` and install requirements.

```bash
pip3 install -r requirements.txt
```

this particular app references a `settings.ini` file which is deliberately excluded from version control. from within the `~/flaskalicious/` directory:

```bash
sudo vi settings.ini
```

copy and paste secret keys into the file, then enter `:wq` to save and quit. now everything should run on command:

```bash
python3 app.py
```

there are still details to figure out regarding mapping the instance ip address to a custom domain so that authentication redirect urls are accepted, but at least the app is running in the cloud now. : )



