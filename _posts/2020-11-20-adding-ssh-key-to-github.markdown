---
layout: post
title:  "Adding ssh key to github"
date:   2020-11-20 08:45:03 -0300
categories: software
---

# Adding ssh key to github

On github you need search by **Settings**.

![Settings](/images/github-ssh/1.png)

Then, in the next page, search for **SSH and GPG keys**

![SSH and GPG keys](/images/github-ssh/2.png)

In the next page click in **New SSH Key**

![New SSH Key](/images/github-ssh/3.png)

Now, in your terminal:

```shell
ssh-keygen
```

For the messages below only press *enter*

_Enter file in which to save the key (/home/vagrant/.ssh/id_rsa):_

_Enter passphrase (empty for no passphrase):_

_Enter same passphrase again:_

At this point your keys (private and public were generated)

```shell
cat ~/.ssh/id_rsa.pub
```

copy the content and paste in the github

![ssh key](/images/github-ssh/4.png)

Just click in **Add SSH Key** and your ssh is available for use it.


