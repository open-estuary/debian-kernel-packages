PROGS = conf

include $(top_rulesdir)/Makefile.inc

common-objs	:= confdata.o expr.o symbol.o preprocess.o zconf.lex.o zconf.tab.o

conf: conf.o $(common-objs)

zconf.tab.c: zconf.lex.c

zconf.lex.o: zconf.tab.h

%.lex.c: %.l
	flex -o$@ -L $<

%.tab.c: %.y
	bison -o$@ -t -l $<

%.tab.h: %.y
	bison -o/dev/null --defines=$@ -t -l $<
