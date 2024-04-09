# PROJECT = sgemm

# SRCS = main.cc

# OPTS ?= -n32

# include ../common.mk

include ../common/make.config
TYPE = GPU
CC = clang++
CC_FLAGS = -g -O2 -std=c++11
CC_FLAGS += -I.

sgemm.out: 
	$(CC) $(CC_FLAGS) main.cc -o sgemm.out -I$(OPENCL_INC) -L$(OPENCL_LIB) -lOpenCL -Wno-unused-result

%.o: %.[ch]
	$(CC) $(CC_FLAGS) $< -c

clean:
	rm -f *.o *~ *.out *.linkinfo