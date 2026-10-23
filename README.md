![Build](https://github.com/open-education-polito/python-interactive-book-chapters/actions/workflows/build-deploy.yml/badge.svg)
![GitHub](https://img.shields.io/github/license/open-education-polito/python-interactive-book-chapters.svg)
![GitHub
issues](https://img.shields.io/github/issues/open-education-polito/python-interactive-book-chapters.svg)

# Python Interactive Book
OEP Python interactive book.
This repo contains the RST sources of the book. Such sources will have to be
compiled inside a proper runestone instance. 

## Website
The book is published [here](https://openeducation.polito.it/libro/).

# Flow
This repo contains only the RST sources of the book. To get an HTML version
they have to be built with the
[template repo](https://github.com/open-education-polito/python-interactive-book-template),
which holds the Runestone configuration (`conf.py`, `pavement.py`) and the
list of Python dependencies (`requirements.txt`).

# Deploy
The workflow `.github/workflows/build-deploy.yml` builds the book on every
push and pull request. On every push to `master` it also publishes the result
with rsync. It needs these repository secrets: `SSH_PRIVATE_KEY`, `SSH_HOST`,
`SSH_PORT` and `SSH_USER`.

# How to test locally
You need Python 3.9 or newer.

1. Clone the template and enter its folder:
```bash
git clone https://github.com/open-education-polito/python-interactive-book-template.git libro
cd libro
```
2. Create and activate a virtual environment, then install the dependencies:
```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```
3. Clone this repo into the `_sources` folder (the template ignores it):
```bash
git clone https://github.com/open-education-polito/python-interactive-book-chapters.git _sources
```
4. Build the book (the HTML ends up in `build/python-interattivo`):
```bash
runestone build --all
```
5. Serve it and open `http://localhost:8000` in the browser:
```bash
runestone serve
```

Remember that `_sources` is a full git repo: if you want to work with the git
flow, do it inside that folder. The build never touches it.

## Writing the chapters
* Put the images in `capitoli/images/` and add an `:alt:` text to every
  `.. image::`.
* Use the colour roles `:red:`, `:blue:`, `:green:` and their `bolt` variants
  directly: they are defined once in the template `conf.py`, do not redefine
  them in the chapters.
* Indent code with spaces (4 per level), never with tabs.
* Every `activecode`, `mchoice`, etc. needs an id made only of letters,
  digits and underscores (no dots) that is unique in the whole book.
* Use the typographic apostrophe `’` in the text and the proper accented
  letters (è, più, perché) everywhere, also inside the code strings.

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


## Authors and Copyright
See the `AUTHORS.md` file in the root of this repo. 
