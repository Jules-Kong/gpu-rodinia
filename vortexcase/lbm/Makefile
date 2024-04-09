# PROJECT = lbm

# SRCS = main.cc args.c parboil_opencl.c gpu_info.c lbm.c ocl.c

# CXXFLAGS += -I.

# OPTS ?= 

# include ../common.mk


include ../common/make.config
TYPE = GPU
CC = clang++
CC_FLAGS = -g -O2 -std=c++11
CC_FLAGS += -I.

%.o: %.[ch]
	$(CC) $(CC_FLAGS) -I$(OPENCL_INC) $< -c

lbm.out: args.o gpu_info.o lbm.o ocl.o parboil_opencl.o
	$(CC) $(CC_FLAGS) main.cc $^ -o lbm.out -I$(OPENCL_INC) -L$(OPENCL_LIB) -lOpenCL -Wno-unused-result



# args.o: args.c
# 	$(CC) $(CC_FLAGS) -I$(OPENCL_INC) args.c -c

# gpu_info.o: gpu_info.c
# 	$(CC) $(CC_FLAGS) -I$(OPENCL_INC) gpu_info.c -c

# lbm.o: lbm.c
# 	$(CC) $(CC_FLAGS) -I$(OPENCL_INC) lbm.c -c

# ocl.o: ocl.c
# 	$(CC) $(CC_FLAGS) -I$(OPENCL_INC) ocl.c -c

# parboil_opencl.o: ocl.c
# 	$(CC) $(CC_FLAGS) -I$(OPENCL_INC) parboil_opencl.c -c

clean:
	rm -f *.o *~ *.out *.linkinfo