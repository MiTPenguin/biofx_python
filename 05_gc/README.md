# Finding GC Content in Sequences

http://rosalind.info/problems/gc/

Write a Python program called `cgc.py` that takes a single positional argument which should be a readable text file.

The program should print a "usage" statement for `-h` or `--help` flags:

```
$ ./cgc.py -h
usage: cgc.py [-h] FILE

Compute GC content

positional arguments:
  FILE        Input sequence file

optional arguments:
  -h, --help  show this help message and exit
```

The input file will be in FASTA format:

```
$ cat tests/inputs/1.fa
>Rosalind_6404
CCTGCGGAAGATCGGCACTAGAATAGCCAGAACCGTTTCTCTGAGGCTTCCGGCCTTCCC
TCCCACTAATAATTCTGAGG
>Rosalind_5959
CCATCGGTAGCGCATCCTTAGTCCAATTAAGTCCCTATCCAGGCGCTCCGCCGAAGGTCT
ATATCCATTTGTCAGCAGACACGC
>Rosalind_0808
CCACCCTCGTGGTATGGCTAGGCATTCAGGAACCGGAGAACGCTTCAGACCAGCCCGGAC
TGGGAACCTGCGGGCAGTAGGTGGAAT
```

The output should be the sequence ID with the highest GC content along with that GC content as a floating-point value to 6 significant digits:

```
$ ./cgc.py tests/inputs/1.fa
Rosalind_0808 60.919540
```

A fully passing test suite looks like the following:

```
$ make test
python3 -m pytest -xv --disable-pytest-warnings --flake8 --pylint 
--mypy cgc.py tests/cgc_test.py
============================ test session starts ============================
...

cgc.py::FLAKE8 SKIPPED                                                [  9%]
cgc.py::mypy PASSED                                                   [ 18%]
cgc.py::test_gc PASSED                                                [ 27%]
tests/cgc_test.py::FLAKE8 SKIPPED                                     [ 36%]
tests/cgc_test.py::mypy PASSED                                        [ 45%]
tests/cgc_test.py::test_exists PASSED                                 [ 54%]
tests/cgc_test.py::test_usage PASSED                                  [ 63%]
tests/cgc_test.py::test_bad_input PASSED                              [ 72%]
tests/cgc_test.py::test_good_input1 PASSED                            [ 81%]
tests/cgc_test.py::test_good_input2 PASSED                            [ 90%]
::mypy PASSED                                                         [100%]
=================================== mypy ====================================

Success: no issues found in 2 source files
======================= 9 passed, 2 skipped in 1.39s ========================
```

## Author

Ken Youens-Clark <kyclark@gmail.com>

## Notes:
Couple of interesitng solutions that are interesting. I ended up using the Collections package, and the counter method
to just create quick dictionaries, then count the GC content that I care about. I wonder how fast that is compare to
some of the solutions.

StdIn works, but not in commandline, which somehow pytest always seems to call automatically. 

The sorted, and the filter function with lambda are usueful things to keep in mind. Then there are a lot of testing 
fns and shortcuts. Like I didn't know you can use empty string as boolean value. That's quick way to guard against 
empty string input. 

Hmm, then the BioSeq is the common way to parse sequencing data. I think that's also the most useful way to go through
things like .bam files in python. 

The argm=parse stuff I keeps forgetting still. it's not the biggest obstacle, but it is a bit annoying.