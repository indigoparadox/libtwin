
# vim: ft=make noexpandtab

SOURCES=ui/graphicu.c htmtree.c htmlrend.c
CHECKOBJ=
OBJECTS=$(subst .c,.o,$(SOURCES))
INCDIRS=-I../../camgraph/src -I../../camin/src -I../../libvcol/src
CFLAGS=-Wall $(INCDIRS)
LDFLAGS=

BIN_LIN=tw

MD=mkdir -v -p

$(BIN_LIN): CFLAGS += -g -DDEBUG
$(BIN_LIN): LDFLAGS += $(shell pkg-config --libs ncurses)
$(BIN_LIN): OBJDIR := ../obj/linux

all: $(BIN_LIN)

$(BIN_LIN): $(OBJECTS)
	$(CC) -o $@ $(addprefix $(OBJDIR)/,$^) $(LDFLAGS)

%.o: %.c
	$(MD) $(OBJDIR)/$(dir $@)
	$(CC) -c -o $(OBJDIR)/$@ $< $(CFLAGS)

.PHONY: clean

clean:
	rm -rf ../obj; \
	rm tests; \
	rm $(BIN_LIN);



