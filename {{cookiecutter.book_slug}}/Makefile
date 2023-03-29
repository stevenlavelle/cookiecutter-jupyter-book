export SHELL := /bin/bash
.PHONY: venv sphinx-config install list-installed build build-help \
		check-links clean clean-build clean-html clean-sphinx-config \
		clean-venv serve 

help:
	@echo "create 	- create a new chapter"
	@echo "build 	- build the book from content files"
	@echo "serve 	- serve the built document"
	@echo "clean 	- remove the built document folder"

venv:
	rm -rf .venv; \
	python3 -m venv .venv

sphinx-config:
	source .venv/bin/activate; \
	jupyter-book config sphinx placeholder

install:
	source .venv/bin/activate; \
	python -m pip install --upgrade --requirement requirements.txt

list-installed:
	source .venv/bin/activate; \
	python -m pip list

build:
	source .venv/bin/activate; \
	jupyter-book build --all --verbose --builder html placeholder

build-help:
	source .venv/bin/activate; \
	jupyter-book build -W -n --keep-going placeholder/

check-links:
	source .venv/bin/activate; \
	jupyter-book build placeholder --builder linkcheck

clean:
	source .venv/bin/activate; \
	jupyter-book clean placeholder/

clean-html:
	source .venv/bin/activate; \
	jupyter-book clean --html placeholder/

clean-build:
	source .venv/bin/activate; \
	jupyter-book clean --all placeholder/

clean-sphinx-config:
	rm -f placeholder/conf.py

clean-venv:
	rm -rf .venv

serve:
	source .venv/bin/activate; \
	python -m http.server 8000 --bind 127.0.0.1 --directory placeholder/_build/html

# myst
# jupyter-book myst [OPTIONS] COMMAND [ARGS]...

# init
# jupyter-book myst init [OPTIONS] [PATH]...