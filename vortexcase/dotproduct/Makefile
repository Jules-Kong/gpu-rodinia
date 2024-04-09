# PROJECT = dotproduct

# SRCS = main.cc oclUtils.cpp shrUtils.cpp cmd_arg_reader.cpp

# OPTS ?= -n64

# include ../common.mk


include ../common/make.config
TYPE = GPU
CC = clang++
CC_FLAGS = -g -O2 -std=c++11
CC_FLAGS += -I.

dotproduct.out: oclUtils.o shrUtils.o cmd_arg_reader.o
	$(CC) $(CC_FLAGS) main.cc oclUtils.cpp shrUtils.o cmd_arg_reader.o -o dotproduct.out -I$(OPENCL_INC) -L$(OPENCL_LIB) -lOpenCL -Wno-unused-result

%.o: %.[ch]
	$(CC) $(CC_FLAGS) $< -c

oclUtils.o: oclUtils.cpp 
	$(CC) $(CC_FLAGS) -I$(OPENCL_INC) oclUtils.cpp -c

shrUtils.o: shrUtils.cpp
	$(CC) $(CC_FLAGS) -I$(OPENCL_INC) shrUtils.cpp -c

cmd_arg_reader.o: cmd_arg_reader.cpp
	$(CC) $(CC_FLAGS) -I$(OPENCL_INC) cmd_arg_reader.cpp -c


clean:
	rm -f *.o *~ *.out *.linkinfo