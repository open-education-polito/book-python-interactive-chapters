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
