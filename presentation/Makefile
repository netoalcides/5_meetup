realtime:
	inotifywait -q -m -e close_write --format %e tensorflow.md | \
	while read events; do \
			make reveal; \
	done

reveal:
	pandoc -t revealjs \
		--section-divs --standalone --self-contained \
		--variable theme="night" \
		--variable transition="linear" \
		--variable section-titles="true" \
		tensorflow.md -o tensorflow.html

pdf:
	pandoc -t beamer \
	--variable theme="AnnArbor" \
	--variable colortheme="beaver" \
	--variable fonttheme="structurebold" \
	tensorflow.md -o tensorflow.pdf

serve:
	python -m http.server

clean:
	rm tensorflow.html
	rm tensorflow.pdf