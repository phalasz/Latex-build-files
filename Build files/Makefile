.SUFFIXES: .dvi .pdf .tex .show

all:
	for F in *.tex; do \
	latex $$F;\
	bibtex $$(basename $$F .tex); \
	- makeindex $$F; \
	latex $$F;\
	latex $$F; \
	done

%.pdf: %.dvi
	dvipdf $<

%.dvi: %.tex
	latex $<
#	bibtex $$(basename $< .tex)
	- makeindex $<
	latex $<
	latex $<

%.show: %.pdf
	xpdf $<

clean:
	rm -fr *.nav *.snm *.out *.bbl *.ind *.blg *.ilg *.lof *.log *.pdf *.toc *.aux .*.swp
