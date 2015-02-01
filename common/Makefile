include LaTeX.mk

# http://stevenrbrandt.com/wordpress/?p=96
check:
	aspell --encoding=iso8859-1 -t -l fr --add-extra-dicts=./custom_dict.aspell -c $(addsuffix .tex,$(LU_MASTERS))
aspell-create-wordlist:
	aspell -t list --encoding=iso8859-1 -l fr -a < $(addsuffix .tex,$(LU_MASTERS)) | sort -u > ./custom_word_list.txt
aspell-create-dict:
	aspell --lang fr create master ./custom_dict.aspell < ./custom_word_list.txt

wc:
	grep -A 1000 "begin{abstract}" $(addsuffix .tex,$(LU_MASTERS)) | grep -B 1000 "end{abstract}" | grep -v "{abstract}" | wc -w

.PHONY: swf
translate:
	po4a po4a/po4a.cfg --verbose -k 0 -M utf8

