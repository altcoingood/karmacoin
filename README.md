Karmacoin integration/staging tree
================================

http://www.karmacoin.info

Copyright (c) 2009-2013 Bitcoin Developers
Copyright (c) 2011-2013 Litecoin Developers
Copyright (c) 2011-2014 Karmacoin Developers

What is Karmacoin?
----------------

Karmacoin is a lite version of Bitcoin using scrypt as a proof-of-work algorithm.  It is designed to reward early miners more heavily than those who join later

 - 1 minute block targets
 - subsidy halves in 2.1M blocks (~4 years)
 - ~92 billion total coins
 - 10,000 coins per block with an additional bonus based on what block is being mined

 - Reward calculation
	- 0-10,000 blocks => 10,000 + up to 2,000,000 bonus
	- 10,000-25,000 blocks => 10,000 + up to 1,500,000 bonus
	- 25,000-50,000 blocks => 10,000 + up to 1,000,000 bonus
	- 50,000-100,000 blocks => 10,000 + up to 500,000 bonus
	- 100,000-200,000 blocks => 10,000 + up to 200,000 bonus
 	- 200,000-300,000 blocks => 10,000 + up to 50,000 bonus
	- 300,000-400,000 blocks => 10,000 + up to 20,000 bonus
	- 500,000+ blocks => 10,000 coins
 - 240 blocks to retarget difficulty

For more information, as well as an immediately useable, binary version of
the Karmacoin client sofware, see http://www.karmacoin.info


License
-------

Karmacoin is released under the terms of the MIT license. See `COPYING` for more
information or see http://opensource.org/licenses/MIT.

Development process
-------------------

Developers work in their own trees, then submit pull requests when they think
their feature or bug fix is ready.

If it is a simple/trivial/non-controversial change, then one of the Karmacoin
development team members simply pulls it.

If it is a *more complicated or potentially controversial* change, then the patch
submitter will be asked to start a discussion (if they haven't already) on the
[mailing list](http://sourceforge.net/mailarchive/forum.php?forum_name=bitcoin-development).

The patch will be accepted if there is broad consensus that it is a good thing.
Developers should expect to rework and resubmit patches if the code doesn't
match the project's coding conventions (see `doc/coding.txt`) or are
controversial.

The `master` branch is regularly built and tested, but is not guaranteed to be
completely stable. [Tags](https://github.com/bitcoin/bitcoin/tags) are created
regularly to indicate new official, stable release versions of Amcecoin.

Testing
-------

Testing and code review is the bottleneck for development; we get more pull
requests than we can review and test. Please be patient and help out, and
remember this is a security-critical project where any mistake might cost people
lots of money.

### Automated Testing

Developers are strongly encouraged to write unit tests for new code, and to
submit new unit tests for old code.

Unit tests for the core code are in `src/test/`. To compile and run them:

    cd src; make -f makefile.unix test

Unit tests for the GUI code are in `src/qt/test/`. To compile and run them:

    qmake BITCOIN_QT_TEST=1 -o Makefile.test bitcoin-qt.pro
    make -f Makefile.test
    ./karmacoin-qt_test

