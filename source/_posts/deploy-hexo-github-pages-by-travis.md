---
title: deploy hexo github pages by travis
date: 2016-01-23 14:37:21
tags: Others
---
In my daily work, the [Jenkins](https://jenkins-ci.org) is a great CI framework to deploy and test.   
How about the open source project?  
I suggest [Travis CI](https://travis-ci.org) is simple to deploy and test for your GitHub project.  
In this time, I will deploy my Hexo to githubpages with Travis.
The first thing is to enable your git project with Travis.  
### Enable Travis with your Git project
![travisci.png](/blog/img/travisci.png)

### Configure Travis to your Git Project
```
    touch .travis.yml
```
make shere the --silent is enable to exclude the token infomation for travis log.

```
language: node_js
branches:
  only:
  - master
before_install:
- npm install -g hexo-cli
- npm install -g hexo
before_script:
- git config --global user.name 'yourname'
- git config --global user.email 'youremail'
- sed -i'' "s~git@github.com:koyasu221b/blog.git~https://${GH_TOKEN}:x-oauth-basic@github.com/koyasu221b/blog.git~" _config.yml
install:
- npm install
script:
- hexo generate
after_success:
- hexo deploy --silent

```

### Install Travis command line tools
```
   $ gem isntall travis
   $ travis login
    
```
### Add GIT TOKEN
```
   $ travis encrypt 'GH_TOKEN=<TOKEN>' --add
    
```
This will add a new section to the .travis.yml file
```
env:
  global:
    secure: fxBE17yzFhC2+FjwVLYbgIhggyfliv3dFCDozTJD7U3n...
```
### Update the _config.yml
```
deploy:
  type: git
  repo: git@github.com:koyasu221b/blog.git
  branch: gh-pages
```

After you write a post, do a push to Github and you will find your blog is update.

![travisci_output.png](/blog/img/travisci_output.png)

