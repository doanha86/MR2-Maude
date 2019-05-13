RSE-Maude: A Ring-Specification Environment on top of Maude
===========================================================

RSE-Maude is a Full Maude extension for easily specifying robots algorithms in ring
topologies. Its main features are:

1. It provides a `ring` attribute that makes sequences work module symmetry and rotation.
It also provides `cring` and `aring` for clockwise and anti-clockwise rings, respectively,
which only work modulo rotation.
2. It provides three different predefined ways to specify ring modules.
3. It provides facilities for easily model-checking ring algorithm. In particular, it
eases the verification of exploration algorithms.

Getting the tool
----------------

The code of 'RSE-Maude' is contained in a GIT repository on GitHub, whose URL is
https://github.com/doanha86/RSE-Maude. To get a copy of the repository you only
have to write in your Linux/MacOS console:

    $ git clone https://github.com/doanha86/RSE-Maude

This will create an RSE-Maude folder containing the source code of the tool as well as
several examples.

Using the tool
--------------

1. RSE-Maude requires Maude 2.7 and Full Maude 2.7 to be installed in your computer.
The Maude system is available [here](http://maude.cs.illinois.edu/w/index.php/The_Maude_System).

2. Go to the **src** folder and start Maude while loading **maude-ring.maude**:

    $ maude maude-ring.maude

3. Now, Full Maude modules using the **ring** attribute can be introduced.
For example,

```
(mod SIMPLE-RING is
         sorts Seq Config .
         op emp : -> Seq [ctor] .

         op __ : Seq Seq -> Seq [ctor assoc id: emp] .
         op <_> : Seq -> Config [ctor ring].
       endm)
```

The module `SIMPLE-RING` above defines the operator `<_>` as the wrapper of a sequence
that behaves as a bi-directional ring.

Examples
--------

The folder **src/examples** contains several examples that can be directly used to
get a glimpse of how RSE-Maude works. In order to execute them, just start RSE-Maude
as indicated in the previous section. Then, go to the **examples** folder

    $ cd examples/

and load any of the files. For example, the **exploration.maude** file presents
how to model check the exploration property.

More information
----------------

The RSE-Maude manual and its theoretical foundations are available in the **doc** folder.

Please contact **doanha [@] jaist.ac.jp** for more information.