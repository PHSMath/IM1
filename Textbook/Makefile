TESTFOLDER=tests

all: bookmain

bookmain:
	latexmk $(LATEXMKSWITCHES) -pretex="\def\all{1}" $@.tex
	# Update current number of pages in README.md
	A=$$(pdfinfo bookmain.pdf | awk '/^Pages:/ {print $$2}'); \
	sed -i "s/Current.*/Current number of pages: $$A./g" README.md

force:
	$(MAKE) LATEXMKSWITCHES=-gg all

clean:
	$(MAKE) LATEXMKSWITCHES=-C all

.PHONY: all bookmain boxes clean force