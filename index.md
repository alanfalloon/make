---
title: GNU Make Unofficial Git Mirror
layout: default
---

What is it?
===========

This is a [Git](http://git-scm.com/) mirror of the
[GNU Make](http://www.gnu.org/software/make/)
[CVS repository](http://savannah.gnu.org/cvs/?group=make) hosted on
[savannah.gnu.org](http://savannah.gnu.org/projects/make/).

The mirror is updated daily. If make development starts heating up, I
will increase the update frequency.

How do I use it?
================

To clone the GNU make sources using Git, use one of the following commands:

    $ git clone git://github.com/alanfalloon/make.git
    $ git clone https://alanfalloon@github.com/alanfalloon/make.git

If you plan on using [GitHub](http://github.com) to host your patches,
then its probably best to
[fork](http://github.com/alanfalloon/make/fork) the
[project](http://github.com/alanfalloon/make) on GitHub instead.

The `master` branch contains the main-line development. Its probably
best if you rebase your changes on top of master whenever you pull, so
either use the `git pull --rebase` command, or setup your local
`master` branch to always rebase by setting the `branch.master.rebase`
configuration variable:

    $ git config branch.master.rebase true

Submitting Changes
------------------

This repository is only a mirror of the official make repository. If
you want to see your changes merged in to make, you need to send your
patches to the [developer mailing list][mailing-list]. Don't send your
patches to me, I can't do anything with them.

You can easily send all your patches from git using the
[git-send-email][git-send-email] command:

    $ git send-email --to='make-alpha@gnu.org' origin/master..master

However, be careful not to spam the list. It never hurts to try it
with the `--dry-run` switch first.

Since Make is an official GNU project, you will need to
[assign the copyright of your patches][fsf-assignment] to the
[FSF](http://fsf.org/) or the maintainers won't be able to accept your
patches.

[fsf-assignment]: http://www.gnu.org/prep/maintain/maintain.html#Copyright-Papers
[mailing-list]: http://lists.gnu.org/mailman/listinfo/make-alpha
[git-send-email]: http://www.kernel.org/pub/software/scm/git/docs/git-send-email.html

Adding Features to Make
-----------------------

If your patches are more than simple bug fixes, its probably best to
search the archives of the mailing list to see if this type of feature
has been discussed before, and you should ask for feedback from the
other developers before you begin serious development of your feature
since they will probably have some valuable input.

Collaborating on Patches
------------------------

If you want to collaborate with other developers on a patchset, I
strongly recommend using
[topgit](http://kerneltrap.org/mailarchive/git/2008/8/3/2795494). topgit
tracks each patch as a topic branch, automates updates between
dependant topic branches (patches), and finally translates a topic
branch and its dependencies into a patchset ready to email.

Best of all, since it maintains all the history of your topic
branches, you can push and pull between developers of a patchset
without any of the confusion caused by rebased changes.

Why?
====

Since most of us don't have commit access to the make repositories, we
need to submit our changes as patches. Git makes this much easier.

Git was designed for developing software through patch-sets. Its the
same development model that the Linux kernel uses, and kernel
development is the use-case that drives the Git design decisions.

But mostly, I just like using Git.
