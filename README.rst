.. -*-restructuredtext-*-

git-helpers
=============

This simple set of shell scripts was designed to aid our workflow. We use Github for Windows
for our daily workflow, but it is missing one or two key aspects. 

``git tidyup [[-f] <branch>]``
    This is a simple tool to allow users to easily use the
    excellent ``rebase -i`` without having to know the syntax.
    It will show us all of the changes that we
    have not yet pushed. There are two ways it can be called,
    no-args or with a branch name:
        * When a branch name is specified we will do a:

          ``pull --rebase origin $BRANCH``

          *  If the branch is not on the remote then we tell the user this.
          *  If we are pulling a new branch we will ask the user if this is
             the correct branch.

          Then we do:

          ``rebase -i $BRANCH``

          Using the ``-f`` argument will replace ``pull --rebase`` with ``fetch``.

        * If no argument is given we will look to see if the current branch is
          published on the remote. If it is we will do a:

          ``fetch origin $CURRENT_BRANCH``

          ``rebase -i origin/$CURRENT_BRANCH``

          If the branch is not on the remote then we tell the user this
          and ask that they explicitly provide a local branch.
|
|
``git update``
    Just an alias for:

        ``pull --rebase origin $CURRENT_BRANCH``


