# PROJECT = blackscholes

# SRCS = main.cpp oclUtils.cpp shrUtils.cpp cmd_arg_reader.cpp oclBlackScholes_launcher.cpp oclBlackScholes_gold.cpp

CC_FLAGS += -I.

# OPTS ?= 

# include ../common.mk

include ../common/make.config
TYPE = GPU
CC = clang++
CC_FLAGS = -g -O2 -std=c++11
CC_FLAGS += -I.

blackscholes.out: oclUtils.o shrUtils.o cmd_arg_reader.o oclBlackScholes_launcher.o oclBlackScholes_gold.o
	$(CC) $(CC_FLAGS) main.cpp oclUtils.cpp shrUtils.o cmd_arg_reader.o oclBlackScholes_launcher.o oclBlackScholes_gold.o -o blackscholes.out -I$(OPENCL_INC) -L$(OPENCL_LIB) -lOpenCL -Wno-unused-result

%.o: %.[ch]
	$(CC) $(CC_FLAGS) $< -c

oclUtils.o: oclUtils.cpp 
	$(CC) $(CC_FLAGS) -I$(OPENCL_INC) oclUtils.cpp -c

shrUtils.o: shrUtils.cpp
	$(CC) $(CC_FLAGS) -I$(OPENCL_INC) shrUtils.cpp -c

cmd_arg_reader.o: cmd_arg_reader.cpp
	$(CC) $(CC_FLAGS) -I$(OPENCL_INC) cmd_arg_reader.cpp -c

oclBlackScholes_launcher.o: oclBlackScholes_launcher.cpp
	$(CC) $(CC_FLAGS) -I$(OPENCL_INC) oclBlackScholes_launcher.cpp -c

oclBlackScholes_gold.o: oclBlackScholes_gold.cpp
	$(CC) $(CC_FLAGS) -I$(OPENCL_INC) oclBlackScholes_gold.cpp -c
	
clean:
	rm -f *.o *~ *.out *.linkinfo