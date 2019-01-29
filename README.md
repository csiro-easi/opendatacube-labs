# opendatacube-labs
Experimental datacube development with strong potential for breaking changes and obscure features.


## Workflow for a new experiment
* Clone `csiro-easi/opendatacube-labs` and create a new branch
* Use provided subtree of develop or replace it with the subtree of your choice
* Perform your experimental changes
* Pull new changes from `csiro-easi/opendatacube-labs`
* Merge/Push changes back to your branch
* Merge/Push changes to `csiro-easi/datacube-core`
* PR back into `opendatacube-core`

Note: `--squash` is used to not store all history of the subtree.

## How to use (`git subtrees`)

`git subtrees` work just like usual `git` with the exception of pushing changes to the parent and pulling changes from the parent.


### Creation of a new experiment with develop:

Create a new branch in `csiro-easi/opendatacube-labs` as per usual:
* `git clone git@github.com:csiro-easi/opendatacube-labs.git`
* `git checkout -b <new_branch>`
* `git push origin <new_branch>`


### Create subtree of `datacube-core` with desired branch

* `git subtree add --prefix=datacube-core git@github.com:csiro-easi/datacube-core.git <branch> --squash`
* `git add datacube-core`
* `git commit`
* `git push`


### Making code changes to your new branch:

Perform desired changes as usual:
* `git add` your new files
* `git commit` your changes
* `git push` to push your local changes to your branch.


### Pushing changes back to `csiro-easi/datacube-core`

This is a little different, you need to use `git subtree push`

When you are happy with your experiment and want to push your changes back into `csiro-easi/datacube-core`:
* `git subtree push --prefix=datacube-core git@github.com:csiro-easi/datacube-core.git <branch>`


### Keeping your branch up to date with `csiro-easi/datacube-core`

This is a little different, you need to use `git subtree pull`

`git subtree pull --prefix=datacube-core git@github.com:csiro-easi/datacube-core.git <branch> --squash`


### Pull Requests

Pull requests should be performed on a branch on `csiro-easi/datacube-core` back to `opendatacube/datacube-core`

