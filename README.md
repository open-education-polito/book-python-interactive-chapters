![CircleCI](https://img.shields.io/circleci/build/github/open-education-polito/python-interactive-book-chapters.svg)
![GitHub](https://img.shields.io/github/license/open-education-polito/python-interactive-book-chapters.svg)
![GitHub
issues](https://img.shields.io/github/issues/open-education-polito/python-interactive-book-chapters.svg)

# Python Interactive Book
OEP Python interactive book.
This repo contains the RST sources of the book. Such sources will have to be
compiled inside a proper runestone instance. 

# Flow
This repo, as cited before, is just a part of the whole infrastructure.
In order to be up and running, it is necessary to follow the following flow:
1. Install runestone (from the original project, no forks involved here)
2. Clone the templating repo from this organization.
3. Clone this repo in the proper folder.
4. Build

What follows is a dedicated guide to get up&running easily. 

# How to test locally
In order to locally test this on your dev machine you have to install runestone
and then build the rst files. 
To do so, one possibility is the following:
0. Create a working folder. Let's call it `libro`.
1. Create a virtual environment. To do so, enter in the working folder and launch
   the following:
```bash
virtualenv -p python3 .venv
```
2. Now it is necessary to activate such virtual environment. 
```bash
source .venv/bin/activate
```
3. Install the runestone software and its dependencies.
```bash
pip3 install runestone
```
4. Now it's necessary to get the right template from the repo:
```bash
git clone https://github.com/open-education-polito/python-interactive-book-template.git
cp -r python-interactive-book-template/* .
rm -rf python-interactive-book-template
```
5. This step requires to pull this repo inside the working folder. To do so,
   just typo
```bash
git clone https//github.com/open-education-polito/python-interactive-book-chapters.git _sources
```
6. Eventually, run the build
```bash
runestone build
```
7. To see the result, open the `runestone server` like this:
```bash
runestone serve
```
And to see it, browser `http://localhost:8000`. 

Rememeber that now you have a full working git repo inside the `_sources`
folder so if you want to work using the git flow you should do it inside
that folder. The build process will not touch such a folder since it is
intended to be just the sources one. 

# How-To Contribute
1. Fork this repo
2. Clone the freshly forked repo
3. Work there and test
4. Commit and push always on the forked repo
5. When code is ready, make a PR
6. When Review is done, squash the commits down to one using    
   `git rebase -i HEAD~n` where `n` is the number of commits to squash. 
   You may use `reword` on the top one, `fixup` on the other entries.
7. Rebase the master. To do this:  
   * `git remote add upstream https://github.com/Open-Education-Polito/oep-python-interactive-book.git`  
   * `git fetch upstream/master`  
   * `git rebase -i upstream/master`  
   * Eventually fix the problems, then `git rebase --continue`  
   * When done, push with `git push origin +master`  
8. The code will be merged


