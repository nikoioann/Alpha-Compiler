DEPS = Symbol.h HashTable.h quad.h instructions.h 
obj = parser.o scanner.o Symbol.o HashTable.o quad.o instructions.o
FLAGS = -std=c++11 -g
CC = g++

%.o: %.cpp $(DEPS)
	$(CC) -c $(FLAGS) $< -o $@ 

al: $(obj) $(DEPS)
	$(CC) $(FLAGS) $^ -o $@ -g
	cp al ../

parser.cpp: parser.y
	bison --yacc --defines --output=parser.cpp parser.y -v

scanner.cpp : scanner.l
	flex scanner.l

clean:	
	rm parser.cpp scanner.cpp parser.hpp parser.output *.o
	rm al ../al

