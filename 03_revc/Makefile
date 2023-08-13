.PHONY: test

test:
	python -m pytest -xv --flake8 --pylint --pylint-rcfile=../pylintrc --mypy revc.py tests/revc_test.py

all:
	../bin/all_test.py revc.py
