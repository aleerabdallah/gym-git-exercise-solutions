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
<h1>Welcome to Our Services Page</h1>
<p>Here you can find all the services we offer.</p>
<!--New content-->
<div class="card-wrapper">
  <div>
    <div>
      <h2>Training</h2>
      <img src="" alt="No image" />
    </div>
    <div>
      <h2>Mentorship</h2>
      <img src="" alt="No image" />
    </div>
  </div>
</div>
```

- commit and push them

```sh

git status
git add services.html
git commit -m "Created: div for cards "
git push origin ft/service-redesign
```

- create a new PR for your changes

```sh



```

- go back to your `main` branch and add again new changes to your `service.html` page, you can add different changes but make sure to affect the same part(line of code) as you did in the other PR

```sh
git checkout main

```

- Commit and push those changes

```sh

git add services.html
git commit -m "Main: Updated the content below the heading"
git push origin main

```

- Now go back to the Github PR you had created for the `ft/service-redesign`branch, you will then see that you have conflicts with the `main` branch
- In your project checkout the `ft/service-redesign`branch
- Compare the `ft/service-redesign`with the `main` branch using git diff and observe the changes
- Using git merge, merge the `main` branch with `ft/service-redesign` branch and commit and push you changes again

## Bundle 3

### Exercise 1

- Create a new branch named `ft/team-page`
- Create a new html page named `team.html` and add some changes
- commit and push those changes
- Create a new PR for the changes
- Go back to `main` branch (checkout the `main` branch)
- Create new branch named `ft/contact-page`
- Go back to the `ft/team-page`
- With the help of git log look for the last commit and copy its hash
- Checkout again `ft/contact-page` using git cherry-pick get the changes from the last commit on the `ft/team-page` branch.
- Add new changes for the contact page and commit, push them
- Create a new PR for the contact page
- From the `ft/contact-page` branch create a new branch called `ft/faq-page`
- Create a new `faq.html` page and add some changes there
- Commit and push those changes
- Using git revert, revert the changes of the last commit of the `ft/team-page` branch. (use the commit hash you copied earlier)
- Push the changes and create a new PR

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
