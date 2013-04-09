ghc-dist-custom
===============

customized ghc distributions.

Included
---------------

*ghc-7.7.20130222-x86_64-unknown-linux.tar.bz2*  
- a ghc-7.7 build.

*ghc-7.4.2-eden.tar.gz*
- a parallel programming extension to ghc. http://www.mathematik.uni-marburg.de/~eden/



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
