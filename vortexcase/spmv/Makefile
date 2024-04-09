# PROJECT = spmv

# SRCS = main.cc parboil_opencl.c args.c gpu_info.c file.c convert_dataset.c mmio.c ocl.c

# CXXFLAGS += -I.

# OPTS ?= 

# include ../common.mk

include ../common/make.config
TYPE = GPU
CC = clang++
CC_FLAGS = -g -O2 -std=c++11
CC_FLAGS += -I.
# parboil_opencl.o perfmon.o perf_util.o

%.o: %.[ch]
	$(CC) $(CC_FLAGS) -I$(OPENCL_INC) $< -c

spmv.out: args.o convert_dataset.o file.o gpu_info.o mmio.o ocl.o parboil_opencl.o
	$(CC) $(CC_FLAGS) main.cc $^ -o spmv.out -I$(OPENCL_INC) -L$(OPENCL_LIB) -lOpenCL -Wno-unused-result


clean:
	rm -f *.o *~ *.out *.linkinfo