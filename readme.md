# Steps to add a submodule

1. Make sure a new git repo already exist that will hold the content of the new submodule, for example, we'll be using "git@github.com:/newemptyrepo"
2. Navigate to the directory you're modulizing:
> cd myproject/submodule-dir
3. Remove the to-be submodule from the parent's index:
> git rm -r --cached .
4. Init a new git repo inside the to-be submodule:
> git init
5. Set up the origin for the to-be submodule and make your first commit:
> git remote add origin git@github.com:/newemptyrepo <br>
git add . && git commit && git push --set-upstream origin master
6. Now you must navigate to the parent repo's top-level path:
> cd .. && cd `git rev-parse --show-toplevel`
7. Finally, add the submodule as you would normally:
> git submodule add git@github.com:/newemptyrepo ./myproject/submodule-dir
8. Now commit & push the changes the above command makes and you're all set up!