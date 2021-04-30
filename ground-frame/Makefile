FileName=main
OutputDirectory=build
TexOptions=--lualatex --halt-on-error --interaction=nonstopmode --output-directory=$(OutputDirectory)

all: $(OutputDirectory)/$(FileName).png

$(OutputDirectory)/$(FileName).png: $(OutputDirectory)/$(FileName).pdf
	pdftocairo $< -png -singlefile $(OutputDirectory)/$(FileName)

$(OutputDirectory)/$(FileName).pdf: $(FileName).tex | $(OutputDirectory)
	latexmk $(TexOptions) $(FileName).tex

preview: FORCE | $(OutputDirectory)
	latexmk -pvc $(TexOptions) $(FileName).tex

$(OutputDirectory):
	mkdir -p $@

clean:
	rm -rf $(OutputDirectory)

FORCE:
