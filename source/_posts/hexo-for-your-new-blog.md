---
title: hexo for your new blog
date: 2016-01-17 10:38:19
tags: Others
---
Today, I migrate my blog from [Octopress](http://octopress.org) to [hexo](https://hexo.io)  
Hexo is a fast and lightway blog framework made from nodejs. 
You can write the post by [Markdown](http://daringfireball.net/projects/markdown/) language  
and generates static files in seconds.  
By the way, It's a good time to learn nodejs to build a blog framework.  
Here are some steps to setup:
### Install Hexo
```
    npm install -g hexo-cli
```

### Init New Blog
```
    hexo init <folder>
```

### Writing
```
    hexo new [layout] <title>
```

### Generating static file
```
    hexo generate
```

### Preview
```
    hexo server
```

### Deploy to Github Page
modify the _conifg.yml
```
    deploy:
        type: git
        repo: your git repo
```
Now, you can use the following command to deploy:

```
    hexo deploy
```

What're you wating for?  
Try the hexo for your fist blog.  
