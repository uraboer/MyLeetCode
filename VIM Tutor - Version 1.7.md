## VIM Tutor - Version 1.7



h::arrow_left:

j::arrow_down:

k::arrow_up:

l::arrow_right:



q!:discards any changes you made

x:delete

i:insert

A:append at the end of line



wq:save the file with changes and exit vim



dw:until the start of the next word, EXCLUDING its first character

从光标处删除只下一个单词首字母前

de:to the end of the current word, INCLUDING the last character

从光标处删除至本单词结尾

d$:to the end of the line, INCLUDING the last character

从光标处删除至本行结尾



2w:move the cursor two words forward

光标所在单词，向前移动2个单词，光标至首字母处

3e:move the cursor to the end of the third word forward

光标所在单词为1，向前移动2个单词，光标至单词末字母处

0:move to the start of the line

光标移至行首处



d2w:delete the two UPPER CASE words



dd:delete the line

2dd:delete two lines



u:undo the last command executed

U:return the line to its original state

CTRL-R:undo the undo’s



p:put the line below the cursor

先dd一行，然后p粘贴在光标所在处



r:replace the character at the cursor



ce:change until the end of a word

删除至一个单词结尾，重新输入

c\$:同d\$



CTRL-g:a message will appear at the bottom of the page with the filename and the position in the file

G:to move to the bottom of the file

gg:to move the start of the file



/:search for the pharase

n:search for the same phrase again 

N:search for the same phrase in the opposite direction



?:search for a phrase in the backward direction



CTRL-o: go back to where you came from

CTRL-i: goes forward



%: find a matching ), ], }



:s/old/new：替换光标所在行第一个

:s/old/new/g：替换光标所在行所有子串



:#,#s/old/new/g：where #,# are the line numbers of the range of lines

:%s/old/new/g：to change every occurrence in the whole file 

全部替换

:%s/old/new/gc：to find every occurrencence in the whole file, with a prompt whether to substitute or not

查找，人工判断是否替换





！：allows you to execute any external shell command



v + :w TEST：write the selected lines to the file TEST



:r FILENAME：retrieves disk file FILENAME and puts it below the cursor position

:r !dir：reads the output of the dir command and puts it below the cursor position



o：open up a line BELOW the cursor and place you  in Insert mode

O：open up a line ABOVE the cursor



e：move to the next incomplete word

a：append text AFTER the cursor



R：替换模式，连续替换

r：替换当前



esc--v--y--p：选中，复制，粘贴



set ic：Ignore case

set noic



set nocp： Make sure Vim is not in compatible mode



















