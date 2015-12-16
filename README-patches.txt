My order of patching:
--------------------------
1) sytray
2) scratchpad
3) shiftview
4) monocle-count
5) pertag
6) my personal config

To start patching switch to branch 'my-dwm-6.1' and run 'rebase -i <branchname-for-patch>' for each patch.

Misc:
--------------------------
- for dwm 6.1 you additionally need libxft-dev. For example under Debian:
  $ sudo apt-get install --no-install-recommends libxft-dev

- do not forget to remove "config.h" before compilation (otherwise "config.h" is used instead of "config.def.h")
- standard workflow:
  $ rm config.h
  $ make clean
  $ make dwm
  $ sudo make install

- to introduce new patch:
  - if not happened before, add new remote:
  $ git remote add github git@github.com:<your_username>/<your_repository_name>.git

  - then:
  $ git checkout master
  $ git checkout -b <new_patch_name>
  [.. inject your patch and commit]
  $ git push --set-upstream github

- for debugging purposes run dwm in "Xephyr":
  - install:
  $ sudo apt-get install xserver-xephyr

  - run:
  $ Xephyr -ac -noreset -screen 1366x768 :1

  - in a different shell run: 
  $ export DISPLAY=:1.0
  $ ./dwm

  - do NOT forget to catch keyboard and mouse by pressing Ctrl+SHIFT
    otherwise not all keycombinations will be sent to the dwm/Xephyr instance to be tested
