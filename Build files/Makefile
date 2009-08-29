
.SUFFIXES: .dvi .pdf .tex .show

all:
	for F in *.tex; do \
	latex $$F; \
	bibtex $$(basename $$F .tex); \
	- makeindex $$F; \
	latex $$F; \
	latex $$F; \
	done

.tex.pdf:
	pdflatex $<

.tex.dvi:
	latex $<
	bibtex $$(basename $< .tex)
	- makeindex $<
	latex $<
	latex $<

%.show: %.pdf
	acroread $<

clean:
	rm -fr *.bbl *.blg *.ilg *.ind *.lof *.log *.pdf *.toc *.aux .*.swp 

