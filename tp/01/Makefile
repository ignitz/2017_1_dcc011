OUTPUT_NAME=DCC011_TP1_Yuri_Diego_Santos_Niitsuma.pdf
INPUT_FILES=00_head.md A_enunciado.md A/01.md A/02.md A/03.md A/04.md A/05.md B_enunciado.md B/01.md B/02.md B/03.md B/04.md B/05.md B/10.md C/01.md C/02.md C/03.md C/04.md C/05.md

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
