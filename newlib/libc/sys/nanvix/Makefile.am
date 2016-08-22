AUTOMAKE_OPTIONS = cygnus
INCLUDES = $(NEWLIB_CFLAGS) $(CROSS_CFLAGS) $(TARGET_CFLAGS)
AM_CCASFLAGS = $(INCLUDES)
 
noinst_LIBRARIES = lib.a
 
if MAY_SUPPLY_SYSCALLS
extra_objs = \
	_exit.o close.o execve.o fork.o fstat.o \
	getpid.o gettimeofday.o isatty.o kill.o \
	link.o lseek.o open.o read.o sbrk.o     \
	signal.o stat.o times.o unlink.o wait.o \
	write.o environ.o ioctl.o
else                    
extra_objs =
endif
 
lib_a_SOURCES =
lib_a_LIBADD = $(extra_objs)
EXTRA_lib_a_SOURCES = \
	_exit.c close.c execve.c fork.c fstat.c \
	getpid.c gettimeofday.c isatty.c kill.c \
	link.c lseek.c open.c read.c sbrk.c     \
	signal.c stat.c times.c unlink.c wait.c \
	write.c environ.c ioctl.c crt0.c
lib_a_DEPENDENCIES = $(extra_objs)
lib_a_CCASFLAGS = $(AM_CCASFLAGS)
lib_a_CFLAGS = $(AM_CFLAGS)
 
if MAY_SUPPLY_SYSCALLS
all: crt0.o
endif
 
ACLOCAL_AMFLAGS = -I ../../..
CONFIG_STATUS_DEPENDENCIES = $(newlib_basedir)/configure.host