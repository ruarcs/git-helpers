#   "git tidyup <$AGAINST>"
#
#   if(user supplied $AGAINST):
#       check if there exists a branch origin/$AGAINST
#       if(origin/$AGAINST exists):
#           git pull --rebase origin $AGAINST
#           git rebase -i $BRANCH
#       else:
#           output an error message "BRANCH DOES NOT EXIST" and abort.   
#   else:
#       check if, for current branch name $BRANCH, there exists origin/$BRANCH
#       if(origin/$BRANCH exists):
#           git fetch origin
#           git rebase -i origin/$BRANCH
#       else:
#           git fetch origin
#           git rebase -i origin/master
 
################################################################################
 
#   "git update"
#
#   for current branch name $BRANCH (use "symbolic-ref HEAD)":
#       git pull --rebase $BRANCH
#  