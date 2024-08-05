
# Compiler
CC=g++

# Directories
INCLUDE_DIR := .
SRC := .
LIB_DIR := lib
OBJ_DIR := obj

# Compiler flags
CFLAGS = -shared -std=c++11 -g

# Library
LIB_DATA := libdata.so

# Targets
all: libdir objdir $(LIB_DATA)

$(LIB_DATA): $(OBJ_DIR)/data_handler.o $(OBJ_DIR)/data.o
	$(CC) $(CFLAGS) -o $(LIB_DIR)/$(LIB_DATA) $(OBJ_DIR)/*.o

$(OBJ_DIR)/data_handler.o: $(SRC)/data_handler.cpp
	$(CC) -fPIC $(CFLAGS) -o $(OBJ_DIR)/data_handler.o -I$(INCLUDE_DIR) -c $(SRC)/data_handler.cpp

$(OBJ_DIR)/data.o: $(SRC)/data.cpp
	$(CC) -fPIC $(CFLAGS) -o $(OBJ_DIR)/data.o -I$(INCLUDE_DIR) -c $(SRC)/data.cpp

libdir:
	mkdir -p $(LIB_DIR)

objdir:
	mkdir -p $(OBJ_DIR)

clean:
	rm -rf $(LIB_DIR)
	rm -rf $(OBJ_DIR)

