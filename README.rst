Arabic Translation of the Python Documentation
==============================================

Contributing to the Translation
-------------------------------

How to Contribute
~~~~~~~~~~~~~~~~~

You can contribute using:

- github (preferred solution)
- Or just by opening `an issue on github 


Contributing using Github
~~~~~~~~~~~~~~~~~~~~~~~~~

Prerequisites:

- A `github account <https://github.com/join>`_.
- ``git`` `installed <https://help.github.com/articles/set-up-git/>`_ (for windows, see
  https://gitforwindows.org/).
- A ``.po`` file editor (Use `poedit <https://poedit.net/>`_
  if you don't already have one).


Let's start:

You'll need to fork the `python-docs-fr
<https://github.com/python/python-docs-fr>`_ clicking its ``Fork``
button. This creates a copy of the whole project on your github
account: a place where you have the rights to do modifications.

Step by step:

.. code-block:: bash

    # Git clone your github fork using ssh (replace JulienPalard):
    git clone git@github.com:JulienPalard/python-docs-fr.git

    # Go to the cloned directory:
    cd py-docs-ar/


Now you're ready to start a work session, each time you'll start a new task, start here:

.. code-block:: bash

    # To work, we'll need a branch, based on an up-to-date (freshly fetched)
    # upstream/3.7 branch, let's say we'll work on glossary so we name
    # the branch "modules":
    git checkout -b modules

    # You can now work on the file, typically using poedit,
    # then commit your work with a nice explicit message:
    git commit -a -m "Working on modules."

    # Then push your modifications to your github clone,
    # as they are ephemeral branches, let's not configure git to track them all,
    # "origin HEAD" is a "special" syntax to say "Push on origin,
    # on a branch with the same name as the local one",
    # it's nice as it's exactly what we want:
    git push origin HEAD

    # Now you can open the pull request on github, just go to
    # https://github.com/abdur-rahmaanj/py-docs-ar/ and a nice "Compare & pull request"
    # button should appear after a few seconds telling you can ask for a pull request.

    # Now someone is reviewing your modifications, and you'll want to fix their
    # findings, get back to your branch
    # (in case you started something else on another branch):
    git checkout glossary
    # Fix the issues, then commit again:
    git commit -a -m "modules: small fixes."
    git push origin HEAD


You may have noted that this looks like a triangle, with a missing segment:

- You're fetching from upstream (public common repo on github)
- You're pushing to origin (your clone on github)

So yes it's the work of someone to add the last segment, from your
origin to the public upstream, to "close the loop", that's the role of
the people who merges pull requests after proofreading them.

You may also have noted you never ever commit on a version branch
(``3.6``, ``3.7``, ...), only pull from them, consider them read-only
you'll avoid problems.

Before commiting, you should use `grammalecte
<https://www.dicollecte.org/>`_ to check for your translations.


What to translate
~~~~~~~~~~~~~~~~~

You can start with easy tasks like reviewing fuzzy entries to help
keeping the documentation up to date (find them using ``make fuzzy``).

You can also proofread already translated entries, and finally
translate untranslated ones (find them using ``make todo``)..

- Do not translate content of ``:ref:...`` and ``:term:...``
- Put english words, if you have to use them, in *italics* (surrounded
  by stars).
- ``::`` at the end of some paragraphs have to be translated to `` :
  ::`` in French to place the space before the column.
- If you translate a link title, please translate the link too
  (typically if it's Wikipedia and the article has a translation). If
  no translation of the target exists, do not translate the
  title.


Where to get help
~~~~~~~~~~~~~~~~~

The coordinator for this translation is normally Abdur-rahmaanj

Feel free to ask your questions on the ``#python-docs`` channel on `freenode
<https://webchat.freenode.net/>`_ (does not require registration) or the
`AFPy traductions mailing list <https://lists.afpy.org/mailman/listinfo/traductions>`_.


Translation Resources
---------------------

[TOADD]


Glossary
--------

For consistency in our translations, here are some propositions and
reminders for frequent terms you'll have to translate, don't hesitate
to open an issue if you disagree.

========================== ===========================================
Term                       Proposed Translation
========================== ===========================================
-like                      
abstract data type         
argument                   
backslash                  
bound                      
bug                        
built-in                   
call stack                 
debugging                  
double quote               
e.g.                       
garbage collector          
identifier                 
immutable                  
interpreter                
library                    
list comprehension         
little-endian, big-endian  
mutable                    
namespace                  
parameter                  
prompt                     
raise                      
regular expression         
return                     
simple quote               
socket                     
statement                  
thread                     
underscore                 
========================== ===========================================


Project History
---------------

TOADD


Simplify git diffs
------------------

Git diffs are often crowded with useless line number changes, like:

.. code-block:: diff

    -#: ../Doc/library/signal.rst:406
    +#: ../Doc/library/signal.rst:408

To tell git they are not usefull information, you can do the following
after ensuring ``~/.local/bin/`` is in your ``PATH``.

.. code-block:: bash

    cat <<EOF > ~/.local/bin/podiff
    #!/bin/sh
    grep -v '^#:' "\$1"
    EOF

    chmod a+x ~/.local/bin/podiff

    git config diff.podiff.textconv podiff


Maintenance
-----------

TOADD


Merge pot files from CPython
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

TOADD


Find fuzzy strings
~~~~~~~~~~~~~~~~~~

TOADD


Run a test build locally
~~~~~~~~~~~~~~~~~~~~~~~~

TOADD


Synchronize translation with Transifex
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

NOTYET
