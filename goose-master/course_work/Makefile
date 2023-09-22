PDFLATEX = xelatex
COURSE_WORK_PDF = course_work_report
BIBTEX = bibtex
MAKEINDEX = makeindex
RM = rm -f


all: $(COURSE_WORK_PDF).pdf

fast: *.tex ../*.tex ../*.bib
	latexmk -pdf -xelatex $(DIPLOMA_REPORT_PDF)


$(COURSE_WORK_PDF).pdf: *.tex ../*.tex ../*.bib
	$(PDFLATEX) $(COURSE_WORK_PDF)
	$(MAKEINDEX) $(COURSE_WORK_PDF).nlo -s nomencl.ist -o $(COURSE_WORK_PDF).nls
	$(BIBTEX) $(COURSE_WORK_PDF).aux
	# Used for master paper only
	# $(BIBTEX) My.aux
	$(PDFLATEX) $(COURSE_WORK_PDF)
	$(PDFLATEX) $(COURSE_WORK_PDF)
	# Citations count fixing
	$(PDFLATEX) $(COURSE_WORK_PDF)

cleanall: clean
	$(RM)  *.pdf

.PHONY: clean cleanall
clean:
	$(RM) *.aux *.log *.out *.toc *.gz *.gz\(busy\) *.blg *.bbl *.nlo *.nls *.fls *.xdv *.fdb_latexmk *.ilg