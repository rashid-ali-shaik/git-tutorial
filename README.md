# git-tutorial

This is practice repo for git and git hub

# to remove the sensitive information replaced by null

# example

KEYSTORE_PASSWORD = "SECURE PASSWORD"

if you forgot to remove and lots of commits have this password.

# the git commit to replace the string

<b>$1</b> = path of the file (./src/components/security.js)
<b>$2</b> = string that needs to replace (SECURE PASSWORD)
<b>$3</b>= new string that goona place in that (leave empty if you need null)

git filter-branch -f --tree-filter "if [ -f <b>$1</b> ];then sed -i s/<b>$2</b>/<b>$3</b>/g <b>$1</b>;fi" --prune-empty --tag-name-filter cat -- --all

# git command to remove the file in all the commits in the tree

<b>$1</b> = path to the file ('.\wordPress\from FTP\config.php')

git filter-branch --force --index-filter "git rm --cached --ignore-unmatch <b>$1</b>" --prune-empty --tag-name-filter cat -- --all

# If you use any of the commands to push in to the local server use

git push origin --all --force

git push origin --tags --force
