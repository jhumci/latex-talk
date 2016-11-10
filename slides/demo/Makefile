all:
	latexmk -pdf example
	latexmk -pdf arbeit
	latexmk -pdf thesis-titlepage

clean:
	latexmk -pdf -c arbeit
	rm -f arbeit.bbl
	latexmk -pdf -c example
	latexmk -pdf -c thesis-titlepage

.PHONY: all clean