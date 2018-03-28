# Trim your branches

Run git branch -r. Marvel at all the old tracking branches that have been left in your local repo.

Run git remote prune origin to delete the local tracking branches that don’t exist on origin anymore. You might want to throw a --dry-run on there to confirm that git is going to do the right thing.

Re-run git branch -r. Better, right?

Now that your local repo is clean, take a look at the branches on origin by running git ls-remote --heads origin.

Delete any of your branches that are no longer needed with git push origin --delete old_branch.

Maybe bug your coworkers to do 4 and 5, too.
