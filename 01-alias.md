---
layout: page
title: More Version Control with Git
subtitle: Typing less
minutes: 10
---
> ## Learning Objectives {.objectives}
>
> * Create alias

When we start using Git a lot we also get tired of type long commands like
`git log --all --decorate --graph --oneline`.
Git allows us to create our own commands that will be transcript to full Git
commands so we can type less.
We can create a command called `lga` to be transcript into
`log --all --decorate --graph --oneline`
using

~~~ {.git}
$ git config --global alias.lga 'log --all --decorate --graph --oneline'
~~~

After we create the `lga` command we can use it as any other Git command, i.e.
we just need to run

~~~ {.git}
$ git lga
~~~

<!-- FIXME Add output -->

And we can pass arguments to `lga`. For example,

~~~ {.git}
$ git lga -10
~~~

<!-- FIXME Add output -->

> ## Callout Box {.callout}
>
> An aside of some kind.


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
> 1.    Create a directory called `my-dotfiles`.
>       You can create this directory anywhere in your filesystem
>       but for sake of consistense we are going to use
>       `~/swc-git-intermediate/my-dotfiles`.
> 2.    Initiate a Git repository on `my-dotfiles`.
> 3.    Create `README.md`.
> 4.    Create a commit with `README.md`.
> 5.    Copy `~/.gitconfig` into `my-dotfiles`.
> 6.    Create a commit with `my-dotfiles`.
> 7.    Push the changes to GitHub.
