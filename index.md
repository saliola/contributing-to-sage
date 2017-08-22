========================
Contributing to SageMath
========================

    |
    | Everybody who uses Sage is
    | encouraged to contribute
    | something back to Sage
    | at some point.
    |
    | - `Sage Developer's Guide <http://doc.sagemath.org/html/en/developer/index.html>`__


You could:
==========

* Add examples to the documentation
* Find bugs or typos
* Fix a bug
* Implement a new function
* Contribute a useful tutorial for a mathematical topic
* Translate an existing document to a new language
* Create a new class, create a fast new C library, etc.

Brief Overview
==============

.. class:: incremental

    * `Trac server account <http://doc.sagemath.org/html/en/developer/trac.html#section-trac-account>`__:
      used to create bug reports, discuss issues, propose changes, share
      code, ...

    ..

    * `Source code <http://doc.sagemath.org/html/en/installation/source.html>`__:
      You need your own copy of Sage's source code to change it.

    .. *(You can also do this on CoCalc.)*

    * `Conventions and guidelines <http://doc.sagemath.org/html/en/developer/coding_basics.html>`__:
      document outlining Sage's conventions and guidelines for code and
      documentation.

    ..

    * `Git <https://try.github.io/levels/1/challenges/1>`__:
      To share changes with the Sage community, you will need to learn
      about *revision control*; here is a `git cheat sheet <git-cheat-sheet.pdf>`__.


trac server
===========

.. Let's explore the trac server and a few tickets:

* `trac server <https://trac.sagemath.org>`__

* `#23622 <https://trac.sagemath.org/ticket/23622>`__

* `#9280 <https://trac.sagemath.org/ticket/9280>`__

* `#23446 <https://trac.sagemath.org/ticket/23446>`__

* `#23131 <https://trac.sagemath.org/ticket/23131>`__

* `#23568 <https://trac.sagemath.org/ticket/23568>`__

* `#23573 <https://trac.sagemath.org/ticket/23573>`__


git workflow
============

.. class:: incremental

    * configure git and obtain the source code ...

    * create *or* download a branch::

        git branch
        git clone URL

    * make changes: edit; rebuild; test; save (``git commit``)

    * share changes::

        git push
        git pull


git-trac workflow
=================


.. class:: incremental

    * configure git, obtain the source code, **configure git-trac** ...

    * create *or* checkout a **ticket**::

        git trac create 'fix bug in Sage'
        git trac checkout TICKETNUMBER

    * make changes: edit; rebuild (``sage -br``); test

    * share changes::

        git commit
        git trac push [TICKETNUMBER]
        git trac pull


Overview of the review process
==============================

:tiny:`(click image to enlarge)`

.. image:: images/flowchart.png
    :target: images/flowchart.svg
    :align: center
    :scale: 90%


Getting Ready 1: Sign up for a trac account
===========================================

Send an email to

    `sage-trac-account@googlegroups.com <mailto:sage-trac-account@googlegroups.com>`_

with:

    - your full name
    - preferred username
    - contact email
    - and reason for needing a trac account

Getting Ready 2: Generate and link SSH Keys
===========================================

- `Generate SSH keys for your computer <http://doc.sagemath.org/html/en/developer/trac.html#generating-your-ssh-keys>`_::

    ssh-keygen

- `Link your SSH keys with your trac account <http://doc.sagemath.org/html/en/developer/trac.html#linking-your-public-key-to-your-trac-account>`_:

  #. Go to http://trac.sagemath.org
  #. Log in with your trac username/password
  #. Click on "Preferences"
  #. Go to the "SSH Keys" tab
  #. Paste the content of your public key file (e.g. ``~/.ssh/id_rsa.pub``)
  #. Click on "Save changes"

:tiny:`(You will need to do this once for each computer that you will use for
Sage development, including CoCalc projects if you choose to use CoCalc for
Sage development).`

Getting Ready 3: Configure git and git-trac
===========================================

- install and configure `git <https://git-scm.com>`_::

    git config --global user.name "Your Name"
    git config --global user.email you@yourdomain.example.com

- install `git-trac <https://github.com/sagemath/git-trac-command.git>`_::

    git clone https://github.com/sagemath/git-trac-command.git
    cd git-trac-command
    python setup.py install

- configure ``git-trac``::

    git trac config --user username --pass password

Getting Ready 4: Get the Sage source code
=========================================

- get a copy of (the development version) of the Sage source code::

    git clone git@trac.sagemath.org:sage.git
    cd sage
    git checkout develop

- build Sage::

    make start

  :tiny:`(this command will build Sage and test that Sage starts, but it will
  *not* build the documentation)`

- while Sage builds, visit the `trac server <http://trac.sagemath.org>`__ and
  look for tickets that you would like to try, review, work, ... or create
  new tickets!

