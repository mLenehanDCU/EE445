.PHONY: typeset

FILES=`cat index.txt`

typeset:
	pandoc -s                         \
	  --from         markdown       \
	  --to           latex          \
	  --template     template.tex   \
	  --out          report-bib.tex \
	  --latex-engine   xelatex        \
	  --bibliography References/biblio.bib     \
	  --biblatex             \
	  $(FILES)
	xelatex report-bib.tex
	bibtex report-bib.aux
	xelatex report-bib.tex
	xelatex report-bib.tex
