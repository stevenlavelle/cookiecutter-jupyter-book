export SHELL := /bin/bash
.PHONY: install install-dev list-installed build build-help \
		check-links clean clean-build clean-html clean-sphinx-config \
		clean-venv serve 

serve: build
	source .venv/bin/activate; \
	python -m http.server 8000 --bind 127.0.0.1 --directory {{cookiecutter.book_slug}}/_build/html

help:
	@echo "create 	- create a new chapter"
	@echo "build 	- build the book from content files"
	@echo "serve 	- serve the built document"
	@echo "clean 	- remove the built document folder"

.venv:
	rm -rf .venv; \
	python3 -m venv .venv

install: .venv
	source .venv/bin/activate; \
	python -m pip install --upgrade --requirement requirements.txt

install-dev: .venv
	source .venv/bin/activate; \
	python -m pip install --upgrade --requirement requirements-dev.txt

list-installed:
	source .venv/bin/activate; \
	python -m pip list

conf.py: install
	source .venv/bin/activate; \
	jupyter-book config sphinx {{cookiecutter.book_slug}}

build: conf.py
	source .venv/bin/activate; \
	jupyter-book build --all --verbose --builder html {{cookiecutter.book_slug}}

build-help:
	source .venv/bin/activate; \
	jupyter-book build -W -n --keep-going {{cookiecutter.book_slug}}/

check-links:
	source .venv/bin/activate; \
	jupyter-book build {{cookiecutter.book_slug}} --builder linkcheck

clean: clean-build clean-sphinx-config clean-venv  

clean-html:
	source .venv/bin/activate; \
	jupyter-book clean --html {{cookiecutter.book_slug}}/

clean-build:
	source .venv/bin/activate; \
	jupyter-book clean --all {{cookiecutter.book_slug}}/

clean-sphinx-config:
	rm -f {{cookiecutter.book_slug}}/conf.py

clean-venv:
	rm -rf .venv

# myst
# jupyter-book myst [OPTIONS] COMMAND [ARGS]...

# init
# jupyter-book myst init [OPTIONS] [PATH]...