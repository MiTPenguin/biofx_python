.PHONY: test_all

test_all:
	python -m pytest -xv --disable-pytest-warnings --flake8 --pylint --pylint-rcfile=../pylintrc --mypy hamm.py tests/hamm_test.py

test_pytest:
	python -m pytest tests/hamm_test.py

all:
	../bin/all_test.py hamm.py
