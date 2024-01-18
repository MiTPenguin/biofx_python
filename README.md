# Mastering Python for Bioinformatics

This is the repository for the book [Mastering Python for Bioinformatics](https://learning.oreilly.com/library/view/mastering-python-for/9781098100872/) (O'Reilly, 2021, ISBN 9781098100889).

See [O'Reilly's website](https://get.oreilly.com/ind_mastering-python-for-bioinformatics-ch1.html) for a free dowload of the preface and first chapter.

# Author

Ken Youens-Clark <kyclark@gmail.com>


### Notes on running this tutorial on windows

we can't seem to run `.py` scripts directly. it has to be preceeded with `python`. pytest works directly. This seems to
be because the shebang is not really run 

Starting new program `new -fp "<purpose>" <program>.py`

I'm still getting kinda confused by the argparser stuff. It's just to get the input to be parsed neatly. but the precise
arguments needed is a bit garbled.

There are some issues where the test can't always test all the different inputs. For example, from commandline, or from
reading the parameters from files.

I just haven't done using pylint or other files.

At some point, we'll have to run the tests on linux subsystem. I just haven't set up conda on that yet. 

The pytest format is different between the unittest class and the ones used by this tutorial. The ideas are similar, but
one has assert called from itself (inherited from class), and the other uses assert as a generic function. 

### outstanding assignment that could be cool

* find multiple alignments of sequences. Could be useful for hamming distance
* k-mer extraction. Look at Neal's code, and see if we can replicate something similar.
* understand how the argparse module works to parse out the modules, and what each of the basic argumetn does. I wonder
if this can be used in other context, instead of writing a scripts from commandline
* Practice more with HOF writings. the k-mer exercise could be useful to explore.