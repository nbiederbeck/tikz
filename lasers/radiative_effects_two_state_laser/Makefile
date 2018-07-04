all: build/main.pdf

build:
	mkdir -p build

build/main.pdf: main.tex tikz.tex | build
	lualatex --output-directory=build --interaction=nonstopmode --halt-on-error $<
