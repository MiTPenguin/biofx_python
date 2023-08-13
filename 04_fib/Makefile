.PHONY: test

test:
	python -m pytest -xv --flake8 --pylint --pylint-rcfile=../pylintrc --mypy fib.py tests/fib_test.py

all:
	../bin/all_test.py fib.py
