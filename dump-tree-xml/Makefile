# build dump-tree-xml plugin

# path to gcc source code
GCC_SRC = ~/gitlab/gcc/BUILD/gcc-4.8.3-20140911/

# path to gcc build
GCC_BUILD = ~/gitlab/gcc/BUILD/gcc-4.8.3-20140911/obj-x86_64-redhat-linux

INCLUDE  = -I../include \
    -I $(GCC_SRC)/gcc \
    -I $(GCC_BUILD)/gcc \
    -I $(GCC_BUILD)/gmp \
    -I $(GCC_SRC)/include \
    -I $(GCC_SRC)/libcpp/include

NAME = dump-tree-xml

$(NAME).so:	$(NAME).c	../include/parse-tree.h
	g++ $(INCLUDE) -shared -fPIC -o $(NAME).so $(NAME).c

test1:	$(NAME).so
	$(GCC_BUILD)/gcc/cc1 -fplugin=$(CURDIR)/$(NAME).so -fsyntax-only test1.c

