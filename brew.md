http://apple.stackexchange.com/a/153791

I decided to look this up and found that there is an issue. The issue is closed but it is not possible to simply run brew update because you will still get the same error.

So here is what you need to do:

cd /usr/local/Library
git pull origin master

In case you have changes in the directory (/usr/local/Library), the git pull will throw an error. In that case, you'll have to fetch the master branch and set it forcibly as master:

git fetch --all
git reset --hard origin/master
This will upgrade your homebrew and you can use brew again.

If you installed Homebrew as a non-root user, you'll need to cd to /Users/yourusername/homebrew/Library instead of /usr/local/Library.
