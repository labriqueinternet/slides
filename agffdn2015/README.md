Steps :

Create your .tex file

configure po4a with your po4a.cfg (it's recommanded to have the same tree organisation as this one).

add in po4a/definitions the "commands and environments" you don't want to be interpreted by the translator (or else it will fail)

then translate

finally create a new translated tex file, compile it, you are good to go!






#generate pot file
po4a-gettextize -f latex -o definitions=po4a/definitions -m conf-labriqueinternet2.tex -p test.pot -M utf8

#generate the new translated tex
po4a po4a/po4a.cfg --verbose -k 0 -M utf8


