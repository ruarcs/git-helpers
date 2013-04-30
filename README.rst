.. -*-restructuredtext-*-

git-helpers
=============

This simple set of shell scripts was designed to aid our workflow. We use Github for Windows for our daily workflow, but it is missing one or two key aspects. 

``git tidyup [-p] [<branch>]``
    This is a simple tool to allow users to easily use the
    excellent ``rebase -i`` without having to know the syntax.
    It will show us all of the changes that we
    have not yet pushed. There are two ways it can be called,
    no-args or with a branch name:
        * When a branch name is specified we will do a:

          ``fetch origin $BRANCH``

          ``rebase -i origin/$BRANCH``
        * If no argument is given we will look to see if this branch is
          published on the remote. If it is we will do a:

          ``fetch origin $CURRENT_BRANCH``

          ``rebase -i origin/$CURRENT_BRANCH``
    Using the ``-p`` argument will replace ``fetch`` with ``pull --rebase``.

----------

``git update``
    Just an alias for:

        ``pull --rebase origin $CURRENT_BRANCH``
    
----------

``git incoming [<branch>]``
    List all commits that would be introduced from the remote if we did a ``fetch/pull``.


