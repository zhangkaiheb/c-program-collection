

CC = gcc
AR = ar
RM = rm -f


INCLUDES = -I./ -Iinclude
#LIBINCLUDES = -L.
CFLAGS += -O2 $(INCLUDES)
LINKFLAGS =

C_SOURCES = $(wildcard *.c)
C_OBJS = $(patsubst %.c, %.c, $(C_SOURCES))

OBJS_1 = encrypt.o aes.o
OBJS_2 = decrypt.o aes.o
LIBS = -lcrypto

TARGET_1 = encrypt
TARGET_2 = decrypt


all:$(TARGET_1) $(TARGET_2)

$(TARGET_1):$(OBJS_1)
	$(CC) $(LINKFLAGS) -o $(TARGET_1) $^ $(LIBS)

$(TARGET_2):$(OBJS_2)
	$(CC) $(LINKFLAGS) -o $(TARGET_2) $^ $(LIBS)


%.o:%.c
	$(CC) -c $(CFLAGS) $< -o $@

.c.o:
	$(CC) -c -o $*.o $(CFLAGS) $(INCLUDES) $*.c

clean:
	-$(RM) *.o $(TARGET_1) $(TARGET_2)

#gcc lsblk.c -I. -L. libsmartcols.a libmount.a libblkid.a libuuid.a


