#!/usr/bin/make

all: $(patsubst %.Rmd,%.html,$(wildcard *.Rmd)) 

%.html: %.Rmd
	Rscript -e 'library(rmarkdown); rmarkdown::render("$<", output_file = "$@")'
	mv "$@" index.html

new: all
	firefox *.html

homepage: all
	cp *.html ~/Projects/homepage/teaching/2021-spring/TDIS

clean:
	rm *.html
	rm -r *_files
	rm -r *_cache

.PHONY: clean all
