
# vim: ft=make noexpandtab

SOURCES=htmtree.c htmlrend.c
OBJECTS=$(subst .c,.o,$(SOURCES))
INCDIRS=-I../../camgraph/src -I../../camin/src -I../../libvcol/src
CFLAGS=-Wall $(INCDIRS)

MD=mkdir -v -p
AR=ar

../bin/Debug-Linux-Allegro/libtwin.a: CFLAGS += -g -DDEBUG -DUSE_ALLEGRO
../bin/Debug-Linux-Allegro/libtwin.a: OBJDIR := ../obj/linux

all: ../bin/Debug-Linux-Allegro/libtwin.a

../bin/Debug-Linux-Allegro/libtwin.a: $(OBJECTS) ui/graphicu.o
	$(MD) ../bin/Debug-Linux-Allegro
	$(AR) rcs $@ $(addprefix $(OBJDIR)/,$^)

%.o: %.c
	$(MD) $(OBJDIR)/$(dir $@)
	$(CC) -c -o $(OBJDIR)/$@ $< $(CFLAGS)

.PHONY: clean

clean:
	rm -rf ../obj; \
	rm -rf ../bin



