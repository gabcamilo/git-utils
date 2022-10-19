# Git configuration

A simple tutorial (and reminder) of how I like to configure Git to improve workflow.

## Checking configs

There are three levels of configs on git:
* `--system` - all computer users
* `--global` - only current user
* `--local` - only this repo

To check the current configuration use the `git config --list` command.

### example output for `git config --global --list`:

```
init.defaultbranch=main
user.name=Gabriela Carvalho Camilo
user.email=gabccamilo.dev@gmail.com
core.editor=vim
```

## Adding shortcuts for git commands

You can add custom shortcuts for git commands using the `[alias]` tag in the configuration file as shown in the example bellow:

```yaml
s = !git status -s # -s for simpler output
c = !git add --all && git commit -m # add and commit with one command. WARNING!!! Be sure you really want to add everythig before using it to commit!
l = !git log --oneline # -oneline for simpler output
```

## Customizing `git log`

When visualizing many commits, `git log` can be a little overwhelming so, I like to customize its output to improve data visualization. To achieve this goal the argument `--pretty=format:` can be used alongside the desired format, as shown in the example below (good for darker themes on the terminal):

```shell
 $ git --no-pager log --pretty=format:'%C(yellow)%h%C(red)%d %C(reset)%s - %C(cyan)%cn, %C(green)%cr'
```

The complete list of arguments can be found in the [git documentation](https://git-scm.com/docs/pretty-formats), and remember you can create a shortcut for this huge command line in the git configuration file.
