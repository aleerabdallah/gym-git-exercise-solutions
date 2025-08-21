# gym-git-exercise-solutions

## Exercise 1

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

