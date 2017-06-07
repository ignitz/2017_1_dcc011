OUTPUT_NAME=DCC011_EX8_Yuri_Diego_Santos_Niitsuma.pdf
INPUT_FILES=00_head.md

all:
	@make clean
	@make open

$(OUTPUT_NAME):
	@echo 'Converting to PDF'
	@pandoc $(INPUT_FILES) -s -V geometry:margin=1in --mathjax -o "$(OUTPUT_NAME)"

clean:
	@echo 'Removing files'
	@if [ -f "$(OUTPUT_NAME)" ]; \
	then \
		rm "$(OUTPUT_NAME)" ; \
	fi

open: $(OUTPUT_NAME)
	@echo 'Opening PDF'
	@(xdg-open "$(OUTPUT_NAME)" > /dev/null)
