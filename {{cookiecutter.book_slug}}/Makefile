export SHELL := /bin/bash
.PHONY: venv install list-installed build serve

help:
	@echo "create 	- create a new chapter"
	@echo "build 	- build the book from content files"
	@echo "serve 	- serve the built document"
	@echo "clean 	- remove the built document folder"

venv:
	rm -rf .venv; \
	python3 -m venv .venv

install:
	source .venv/bin/activate; \
	python -m pip install --upgrade --requirement requirements.txt

list-installed:
	source .venv/bin/activate; \
	python -m pip list

build:
	source .venv/bin/activate; \
	jupyter-book build --all {{cookiecutter.book_slug}}

build-help:
	source .venv/bin/activate; \
	jupyter-book build -W -n --keep-going {{cookiecutter.book_slug}}/

clean:
	source .venv/bin/activate; \
	jupyter-book clean {{cookiecutter.book_slug}}/

serve:
	source .venv/bin/activate; \
	python -m http.server 8000 --bind 127.0.0.1 --directory {{cookiecutter.book_slug}}/_build/html