
include ../makefile.rule


MACRO_FLAG =  -DCHANNEL_8_MAC -D_FILE_OFFSET_BITS=64 -D_LARGE_FILES -D_GNU_SOURCE



INC_PATH +=-I../include -I./libarm_sqlite/include
INC_PATH += -I../common

CFLAGS += -O0 -Wall   $(INC_PATH) $(MACRO_FLAG) -L./ -L../../lib/3519v101-lib/ -lmpi  -L./libarm_sqlite/lib -L/root/libarm5000_jpeg/lib

LIBDIR=../lib

SRCS    :=  $(wildcard *.cpp)
OBJS    :=  $(SRCS:%.cpp=%.o)


MY_OBJS := libfacesqlite.o

TARGET :=  libfacesqlite.so
.PHONY : clean all

#$(TARGET):$(OBJS)
$(TARGET):$(SRCS)
	$(CC)  -fPIC -shared  $(CFLAGS) -lpthread -lm -lsqlite3 -o $@ $^ $(LIBS) 
	$(STRIP)  $(TARGET)


clean:
	@rm -f $(TARGET)
	@rm -f $(OBJS)


