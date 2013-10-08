ror-guide
=========

**general instructions for RubyOnRails developers**


## Videos

1. 10:00  The Perfect Work-flow with Git, GitHub, and SSH
  
  > [<img src="http://img.youtube.com/vi/hv4hwgQO9xI/0.jpg" alt="Drawing" width=100"/>](http://www.youtube.com/watch?v=hv4hwgQO9xI)

2. 8:40 Ruby on Rails Tutorial installation
  
  > [<img src="http://img.youtube.com/vi/MiAz0DnnY_k/0.jpg" alt="Drawing" width=100"/>](http://www.youtube.com/watch?v=MiAz0DnnY_k)

3. 3:50 Github issue tracker
  
  > [<img src="http://7.i.blip.tv/g?src=Mojombo-GitHubIssuesIntroduction494.png&w=259&h=150&fmt=jpg" alt="Video" width="100" style="" />](http://blip.tv/mojombo/github-issues-introduction-2005070)

4. 3:50 JIRA in a Nutshell demo video
  
  > [<img src="http://img.youtube.com/vi/xrCJv0fTyR8/0.jpg" alt="Drawing" width=100"/>](http://www.youtube.com/watch?v=xrCJv0fTyR8)



## Articles

1. git branching
https://gist.github.com/jbenet/ee6c9ac48068889b0912

2. ruby best practices
https://github.com/bbatsov/ruby-style-guide







=========

## 1 Fixing an issue that was assigned to you

### 1 1 clone repo locally

```
hub clone hi/hello_flowers     (git clone git@github.com:hi/hello_flowers)
cd hello_flowers
```

### 1 2 branch out from master

**issue #83 - pagination should appear on top**

```
git status
git checkout master
git checkout -b 83-james-pagination
```

> edit the code to complete the task...

### 1 3 Before you commit (good practices)

> here's the simplest commit/push possible
> and let's see some good practices to add with that

```
git status
git add -A
git commit -am "msg here"
git push origin 83-james-pagination
```




#### 1 3 1 start by mentioning the task number

```
git add -A
git commit -am "#83 msg here"
git push origin 83-james-pagination
```

#### 1 3 2 mention the task description in the commit message

```
git add -A
git commit -am "#83 pagination should appear on top."
git commit -am "#83 pagination on top of products/index."
git commit -am "#83 pagination now on top too."
git push origin 83-james-pagination
```



#### 1 3 3 tests are your best friends, they show you didn't create any side-effects


```
bundle ex cucumber features
```

> 30 scenarios (0 failed, 0 skipped, 30 passed)

> 145 steps (0 failed, 0 skipped, 145 passed)



```
git status
git add -A
git commit -am "#83 pagination should appear on top. 145 steps (0 failed, 0 skipped, 145 passed)"
git push origin 83-james-pagination
```




#### 1 3 4 deploy to our quality server, you might need to show this to your Project Manager


> if you don't have a user yet,

> please ask james.pinto@helloinnovation.com,

> make sure to have your ssh public key.

> ssh-keygen -t rsa -C "your_email@example.com"

> **tip:** leave the passphrase empty



**on my local machine:**

```
git push origin 83-james-pagination
```

**let's connect to the server:**

```
ssh james@quality.helloinnovation.com
hub clone hi/hello_flowers     (git clone git@github.com:hi/hello_flowers)
git checkout 83-james-pagination
rails server -d -p 3021
```

> now show the following URL to your Project Manager
http://quality.helloinnovation.com:3021


### 1 4 Notify your Project Manager


> notify your Project Manager of the github url for your code changes
>
> https://github.com/hi/hello_flowers/tree/83-james-pagination



