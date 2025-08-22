# gym-git-exercise-solutions

## Bundle One

### Exercise 1

- Create a project folder & initialize git

```sh
git init
```

- Make changes to the project (add files and contents)

```sh
touch TODO.md
```

- Rename your main branch from `master` to `main` (If your branch name is already `main` then rename it

```sh
git branch -m main
```

- Stage your changes and commit them

```sh
git add TODO.md

git commit -m "Initial commit"
```

- Create a Github repo and connect it with your project

```sh
git remote add origin git@github.com:aleerabdallah/bundle-one.git
```

- Push your changes to GitHub

```sh
git push -u origin main
```

- Create a new branch `dev`

```sh
git branch dev
```

- From `dev` create another branch `test`

```sh
git checkout dev

git branch -b test
```

- Go back to the `dev` branch and delete the `test` branch

```sh
git checkout dev

git branch -d test
```

### Exercise 2

- Create a new `home.html` file, add some html changes and save them

```sh
touch home.html
```

- Stash save your current changes

```sh
git stash -u
```

- Repeat the same process for a new `about.html` page and stash save your changes

```sh
touch about.html

git stash -u
```

- Repeat the same process for a new `team.html` page and stash save your changes

```sh
touch team.html
git stash -u
```

- Using stash pop restore the changes of the `about.html` page

```sh
git stash pop stash@{1}
```

- With the help of an index use stash pop bring back the `home.html` page changes

```sh
git stash pop 1
```

- Commit the current changes and push them

```sh
git add .
git commit -m "Created home and about page"
git push origin dev
```

- Using stash pop restore the changes of the `team.html` page index

```sh
git stash pop
```

- Reset the current changes using git reset and go back to the changes without the `team.html` page

```sh
git reset --hard
```

## Bundle Two

### Exercise 1

- Create a new branch named `ft/bundle-2`

```sh
git checkout -b ft/bundle-2
```

- Add new changes to your project. create a new page named `services.html` and add some changes.

```sh
touch services.html
```

- Commit your changes and create a Pull Request against the `main` branch in your github repository

```sh
git add .
git commit -m "added servies page on ft/bundle-2"
git push origin ft/bundle-2
```

- Request a review and make sure your Pull request gets merged (Look for someone to merge your PR)

### Exercise 2

- Checkout your `main` branch and pull the latest changes

```sh
git chekout main
git pull origin main
```

- Create a new branch named `ft/service-redesign`

```sh
git checkout -b ft/service-redesign
```

- Add new changes to the `service.html` page

```html
<!--New content-->
<h1>Welcome to Our Updated Services Page</h1>
```

- commit and push them

```sh

git status
git add services.html
git commit -m "redesign: updated the main heading"
git push origin ft/service-redesign
```

- create a new PR for your changes

```sh



```

- go back to your `main` branch and add again new changes to your `service.html` page, you can add different changes but make sure to affect the same part(line of code) as you did in the other PR

```sh
git checkout main

```

```html
!--New content from main -->
<h1>Welcome to Our Main Updated Services Page</h1>
```

- Commit and push those changes

```sh

git add services.html
git commit -m "Main: Updated the heading services.html into a different content"
git push origin main

```

- Now go back to the Github PR you had created for the `ft/service-redesign`branch, you will then see that you have conflicts with the `main` branch

```
This branch has conflicts that must be resolved
Use the web editor or the command line to resolve conflicts before continuing.

services.html
```

- In your project checkout the `ft/service-redesign`branch

```sh
git checkout ft/service-redesign
```

- Compare the `ft/service-redesign`with the `main` branch using git diff and observe the changes

```sh
git diff main
```

```
diff --git a/services.html b/services.html
index a414629..575b15b 100644
--- a/services.html
+++ b/services.html
@@ -5,7 +5,7 @@
     <title>Our Services</title>
   </head>
   <body>
-    <h1>Welcome to Our Main Updated Services Page</h1>
+    <h1>Welcome to Our Updated Services Page</h1>
     <p>Here you can find all the services we offer.</p>
     <div class="card-wrapper">
       <div>
```

- Using git merge, merge the `main` branch with `ft/service-redesign` branch and commit and push you changes again

```sh

git merge main
```

```html
<!--fixed conflict -->
<h1>Welcome to Our Amazing Updated Services Page</h1>
```

```sh
git add services.html
git commit -m "Resolved merge conflict between main and ft/service-redesign"
git push origin ft/service-redesign
```

```
No conflicts with base branch
Merging can be performed automatically.
```

## Bundle 3

### Exercise 1

- Create a new branch named `ft/team-page`

```sh
git checkout -b ft/team-page
```

- Create a new html page named `team.html` and add some changes

```sh
touch team.html
```

- commit and push those changes

```sh
git add team.html
git commit -m "Added team.html"
git push -u origin ft/team-page
```

- Create a new PR for the changes

```sh
Created a pull request using UI

```

- Go back to `main` branch (checkout the `main` branch)

```sh
git checkout main
```

- Create new branch named `ft/contact-page`

```sh
git checkout -b ft/contact-page

```

- Go back to the `ft/team-page`

```sh
git checkout ft/team-page
```

- With the help of git log look for the last commit and copy its hash

```sh
git log --oneline

4e4b013 (HEAD -> ft/team-page, origin/ft/team-page) Added team.html
964f1a7 (origin/ft/service-redesign, ft/service-redesign) Resolved merge conflict between main and ft/service-redesign
adcbf4e (origin/main, main, ft/contact-page) Main: updated the heading service.html into a different content
0b09ee7 redesign: updated the main heading
```

- Checkout again `ft/contact-page` using git cherry-pick get the changes from the last commit on the `ft/team-page` branch.

```sh
git checkout ft/contact-page
git cherry-pick 4e4b013

[ft/contact-page 95b73e0] Added team.html
 Date: Fri Aug 22 17:10:11 2025 +0200
 1 file changed, 9 insertions(+)
```

- Add new changes for the contact page and commit, push them

```sh
touch contact.html
git add contact.html
git commit -m "Added: contact.html with some content"
git push -u origin ft/contact-page
```

- Create a new PR for the contact page

```sh
Opened a pull request on github ready for review
```

- From the `ft/contact-page` branch create a new branch called `ft/faq-page`

```sh
git checkout -b ft/faq-page
```

- Create a new `faq.html` page and add some changes there

```sh
touch faq.html
```

- Commit and push those changes

```sh
git add faq.html
git commit -m "Added: faq.html with some content in it"
git push origin ft/faq-page
```

- Using git revert, revert the changes of the last commit of the `ft/team-page` branch. (use the commit hash you copied earlier)

```sh
git checkout ft/team-page
git revert 4e4b013

```

Output:

```sh
[ft/team-page 13181ca] Revert "Added team.html"
 1 file changed, 9 deletions(-)
```

- Push the changes and create a new PR

```sh
git push origin ft/team-page
```

Opened a pull request ready for review before merge

### Exercise 2

- Create new branch from the `ft/faq-page` branch named `ft/home-page-redesign`
- Go back to the `main` branch and make some changes there
- Commit and push them
- go back to the `ft/home-page-redesign` branch
- Using git rebase, rebase your branch to `main`
- Add changes to the home page and commit push them
- Create a PR for the changes.

## Bundle 4

### Exercise 1

- Checkout the `main` branch
- Create a new repository on Github
- Using git remote add the repo to your project as second remote named `git-copy`
- Make a new changes on the home page
- Commit the changes
- Push the changes to the both remotes. the `origin` and `git-copy`

### Exercise 2

- Checkout a new branch named `ft/footer`
- Add some changes to the branch and commit them
- Add more changes again to the branch and create a second commit
- Push and create a new PR for the branch
- Checkout the `main` branch again
- From there create a new branch named `ft/squashing`
- Using git merge squash, squash the changes on the `ft/footer` branch
- Commit the changes with a different commit message such as `footer changes squashing`
- Push the changes and create a PR

## Bundle 5

### Exercise 1

- On your Github repo enable Github pages
- Check if the link is publicly visible to anyone

### Exercise 2

- Fork this project <https://github.com/TheGymRwanda/git-cafe-exercise>
- Clone your fork on your machine
- Edit the `index.html` file
- Change the text `Welcome to our place` to `Welcome to our restaurant`
- Commit and push the changes
- Raise a PR to the original Repo

## Bundle 6

In this exercise, you will be working on the copy of the git-cafe-exercise that you have forked on your account in the previous exercise.

Keep in mind that each exercise must be done on a different branch

### Exercise 1

- On the `git-cafe-exercise` repo create a new feature branch
- Add new changes related to a new page named `Menu`
- Afterward, raise a new PR
- Request review

### Exercise 2

- Create a new bug fix branch
- From there change the title of the `index-4.html` file to “**Contact**”
- Raise a new PR
- Request review

### Exercise 3

- On the `git-cafe-exercise` repo, there is a small hot-fix on the contact page
- Change the telephone on the `index-4.html` page from `+1 800 603 6035` to `+1 800 659 6035`

### Exercise 4

- Review two PRs from your peers and request some changes on those PRs —> your peers need to give you access to their repository for you to review them.
- Once, they have adjusted the requested changes, approve and merge that PR.
