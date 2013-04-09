ghc-dist-custom
===============

customized ghc distributions.

Included
---------------



How to install a bindist
-----------------------------


use http://hackage.haskell.org/package/hsenv

````
$ cabal install hsenv
$ hsenv --ghc=ghc-7.7.20130318-x86_64-unknown-linux.tar.bz2 --name=7.7.20130318   
````

How to build your own bindist
-----------------------------

````
$ git clone http://darcs.haskell.org/ghc.git/
$ cd ghc
$ # optionally, git checkout <branch name>
$ ./sync-all --testsuite get
$ cp mk/build.mk.sample mk/build.mk
$ ### edit BuildFlavour to quick ###
$ ./boot
$ ./configure
$ make -jN # <N> is the number of cores you have.
$ make binary-dist
````
