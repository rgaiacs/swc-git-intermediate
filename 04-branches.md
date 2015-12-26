---
layout: page
title: More Version Control with Git
subtitle: Branches
minutes: 10
---
> ## Learning Objectives {.objectives}
>
> * Understand branches.

We use the name branch to keep the same notation of set theory
since the Git history is a [tree](https://en.wikipedia.org/wiki/Tree_%28set_theory%29).
**Unfortunately** the term branch could be better understood
if we think of thumbtack **that has a name**.

![Picture of thumbtack and a piece of paper with the text "The task ahead of you is never as great as the Power within you." The picture is called "An inspirational message over the sink" by Bunny Jager available at https://flic.kr/p/88f39H under CC-BY-SA.](fig/thumbtack.jpg)

We can add and remove thumbtack on a tree as you like.
We can do this with Git and we will learn how soon.

![Thumbtack on a branch tree. The picture is called "Thumbtack" by Christian Bucad available at https://flic.kr/p/7XiB1R under CC-BY-NC-ND.](fig/thumbtack-on-tree.jpg)

If our thumbtack is on a leaf of the tree
and the tree grows our thumbtack will change its position.
Git has this same behaviour.

We can get the name of the thumbtacks on our Git repository with

~~~ {.bash}
$ git branch --all
~~~
~~~ {.out}
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/master
~~~

The star, `*`, marks the thumbtacks that has the files that we are using now.

If we want to get **where** the thumbtacks are on our Git tree we can use

~~~ {.bash}
$ git lga
~~~
~~~ {.out}
* 3f3c1bf (HEAD -> master, origin/master, origin/HEAD) Add words
* 22dcdb5 Add words
*   92808ea Add words
|\  
| * 5121eef Add words
* |   ee40506 Add words
|\ \  
| |/  
|/|   
| * 51bd45c Add words
| * ee87332 Add words
* | 87db327 Add words
|/  
* cde9009 Add Python \o/
* 23c6a6b Add words
* 6318870 Begin
~~~

So,
the thumbtacks
`master`,
`HEAD`,
`remotes/origin/HEAD` and
`remotes/origin/master`
are on the commit `3f3c1bf`.

> ## `HEAD` and the GPS {.callout}
>
> `HEAD` is a very special thumbtack.
> It **always** marks our current position
> on the Git tree.
> You can think of it as the pin on your GPS app
> that marks your current location.
>
> ![Picture of a GPS. The picture is called "Garmin-Asus A10 GPS Android smartphone review" by Cheon Fong Liew available at https://flic.kr/p/9bnK7g under CC-BY-SA.](fig/head-and-gps.jpg)

The file `en.dic` doesn't have the word `abduction`.
Lets create a branch,
called `abduction`,
where we will add that word.

To create the branch we use

~~~ {.bash}
$ git branch abduction
~~~

If we list our branches,

~~~ {.bash}
$ git branch --all
~~~
~~~ {.out}
  abduction
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/master
~~~

we will notice that we still at the `master branch`.
To change our current branch we use

~~~ {.bash}
$ git checkout abduction
~~~
~~~ {.out}
Switched to branch 'abduction'
~~~

After we add the word `abduction` to `en.dic`
we can create a commit with that change.

~~~ {.bash}
$ git commit -am "Add abduction"
~~~
~~~ {.out}
[abduction fb8dde2] Add abduction
 1 file changed, 1 insertion(+)
~~~

We can push our branch to GitHub:

~~~ {.bash}
$ git push origin abduction
~~~
~~~ {.out}
Counting objects: 3, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 293 bytes | 0 bytes/s, done.
Total 3 (delta 1), reused 0 (delta 0)
To git@github.com:rgaiacs/YYYY-MM-DD-git-sample.git
 * [new branch]      abduction -> abduction
~~~

And we can check our Git tree:

~~~ {.bash}
$ git lga | head -n 3
~~~
~~~ {.out}
* fb8dde2 (HEAD -> abduction, origin/abduction) Add abduction
* 3f3c1bf (origin/master, master) Add words
* 22dcdb5 Add words
~~~

Notice that the thumbtack `HEAD` and `abduction` change their position
and a new thumbtack, `origin/abduction`, is on our tree.

> ## More branches {.challenge}
>
> Create branches called
> `camp`, `genomic`, `voluntary`
> that should start at the commit `3f3c1bf`.
> At each branch,
> add one commit that add the name of the branch into `en.dic`.
> After create the three branches,
> push them to GitHub.
