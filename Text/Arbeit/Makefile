.RECIPEPREFIX = >

DOCNAME = Master_PA.pdf

MAINFILE = Arbeit_Main.tex

MAINFILE_NO_EXTENSION = Arbeit_Main

PICS = Grafiken/hl-logo.pdf 

SOURCES = $(MAINFILE) Bibliographie/Bibli.bib Glossar/Arbeit_Glossar.tex \
	Inhalt/Titelseite.tex Inhalt/LeereSeite.tex Inhalt/Erklaerung.tex \
	Inhalt/Abstract.tex $(PICS)

OUTDIR = Ausgabe

FINDIR = Enddokument

# VIEWER = atril
# VFLAGS = -w

enddoc/$(DOCNAME) : $(SOURCES)
> pdflatex -output-directory=$(OUTDIR) $(MAINFILE)
> makeglossaries -d $(OUTDIR) $(MAINFILE_NO_EXTENSION)
> bibtex $(OUTDIR)/$(MAINFILE_NO_EXTENSION)
> pdflatex -output-directory=$(OUTDIR) $(MAINFILE)
> pdflatex -output-directory=$(OUTDIR) $(MAINFILE)
> cp $(OUTDIR)/$(MAINFILE_NO_EXTENSION).pdf $(FINDIR)/$(DOCNAME)

.PHONY: clean set

set : $(SOURCES)
> pdflatex -output-directory=$(OUTDIR) $(MAINFILE)
> cp $(OUTDIR)/$(MAINFILE_NO_EXTENSION).pdf $(FINDIR)/$(DOCNAME)

clean :
> rm $(OUTDIR)/$(MAINFILE_NO_EXTENSION).*
> rm $(FINDIR)/$(DOCNAME)

#view : enddoc/$(DOCNAME)
#> nohup $(VIEWER) $(VFLAGS) $(FINDIR)/$(DOCNAME) > $(OUTDIR)/nohup.out

