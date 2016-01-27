---
layout: page
title: More Version Control with Git
subtitle: Typing less (using git alias)
minutes: 10
---
> ## Learning Objectives {.objectives}
>
> * Create alias

When we start using Git a lot we also get tired of type long commands like
`git log --all --decorate --graph --oneline`.
Git allows us to create our own commands,
called `alias`,
that will be transcript to full Git
commands so we can type less.
For example,
we can create a command called `lga` to be transcript into
`log --all --decorate --graph --oneline`
using

~~~ {.bash}
$ git config --global alias.lga 'log --all --decorate --graph --oneline'
~~~

> ## Config {.callout}
>
> We used `git config`
> at [Software Carpentry's Novice Git lesson](https://swcarpentry.github.io/git-novice/).
> to set up `user.name`, `user.email`, and `core.editor`.

After we create the `lga` command we can use it as any other Git command, i.e.
we just need to run

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

And we can pass arguments to `lga`. For example,

~~~ {.bash}
$ git lga -5
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
~~~

> ## More Alias {.challenge}
>
> Create alias as describe in the following table.
>
> Alias Command
> ----- -------------------------------
> `a`   `add`
> `cam` `commit --all --message`
> `i`   `init`
> `p`   `push --set-upstream`

> ## Dotfiles {.challenge}
>
> Now let share our `~/.gitconfig` on GitHub.
> When possible, use the alias created previously.
>
> 1.    Create a directory called `dotfiles`.
>       We can create this directory anywhere in our filesystem
>       but for sake of consistense we are going to use
>       `~/swc-git-intermediate/dotfiles`.
> 2.    Initiate a Git repository on `dotfiles`.
> 3.    Create `README.md`.
> 4.    Create a commit with `README.md`.
> 5.    Copy `~/.gitconfig` into `dotfiles`.
> 6.    Create a commit with `dotfiles`.
> 7.    Push the changes to GitHub.
>
>       **We need to create a repository on GitHub for it.**
>
> Now we can go to https://github.com/search?utf8=%E2%9C%93&q=dotfiles
> and look at the `dotfiles` that some people share on GitHub.
