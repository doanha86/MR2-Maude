RSE-Maude: A Ring-Specification Environment on top of Maude
===========================================================

RSE-Maude is a

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
         sort Seq .
sort Config .
         op emp : -> Seq [ctor] .
         op __ : Seq Seq -> Seq [ctor assoc id: emp] .
         op <_> : Seq -> Config [ctor ring].
       endm)
```

The module `SIMPLE-RING` above defines the operator `<_>` as the wrapper of a sequence
that behaves as a bi-directional ring.

More information
----------------

The RSE-Maude manual and its theoretical foundations are available in the **doc** folder.

Please contact **doanha [@] jaist.ac.jp** for more information.