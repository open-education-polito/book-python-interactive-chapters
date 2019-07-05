# oep-python-interactive-book
Our Python interactive book - Repo for the RST sources

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

# How to test locally
In order to locally test this on your dev machine you have to install runestone
and then build the rst files. 
To do so, one possibility is the following:
1. Create a virtual environment. To do so, enter in a working folder and launch
   the following:
```bash
virtualenv .venv
```
2. Now it is necessary to activate such virtual environment. 
```bash
source .venv/bin/activate
```
3. Install the runestone software and its dependencies.
```bash
pip install runestone
```
4. It is now necessary to initialize the runestone project. To do so, run
```bash
runestone init
```
Inser the info requested also in a fictional way (this will be used exclusively
as a test so they will not be published anywhere).
5. Now it's necessary to remove the `_sources` folder. To do so run: 
```bash
rm -rf _sources
```
5. This step requires to pull this repo inside the working folder. To do so,
   just typo
```bash
git clone git@github.com:open-education-polito/python-interactive-book.git _sources
```
6. Eventually, run the build
```bash
runestone build
```
7. To see the result, open the `build/<project_name>/index.html` file. That is
   the main entrypoint of the build.
8. Rememeber that now you have a full working git repo inside the `_sources`
   folder so if you want to work using the git flow you should do it inside
   that folder. The build process will not touch such a folder since it is
   intended to be just the sources one. 
