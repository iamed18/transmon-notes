# Makefile to create separate PNG image files for all
#     TEX files in the present directory. The clean
#     command will remove all TeX remnants including
#     the output PDF (change the flag from -CA to -c
#     if you want to keep the PDFs).

TEX_FILES := $(wildcard *.tex)
PDF_FILES := $(TEX_FILES:.tex=.pdf)
PNG_FILES := $(TEX_FILES:.tex=.png)

.PHONY: all clean
all: $(PNG_FILES) clean 


$(PNG_FILES): $(PDF_FILES)
	convert -density 192 -quality 85 $< $@  


$(PDF_FILES):
	latexmk -pdf -pdflatex="pdflatex -interaction=nonstopmode" -use-make $<


clean:
	latexmk -CA
    # latexmk -c