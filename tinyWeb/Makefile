ICC = gcc
CXX = g++
CFLAGS = -g -O0  -Wall 
CXXFLAGS = $(CFLAGS)

INCLDIR =-I. 
LIBDIR = -L. 
LIBS =  -lrt -lstdc++ -lpthread -lmysqlclient

EXE = server

OBJS=\
	$(patsubst %.c,%.o,$(wildcard *.c)) \
	$(patsubst %.cpp,%.o,$(wildcard *.cpp)) \
	$(patsubst %.cxx,%.o,$(wildcard *.cxx)) \
	$(patsubst %.cc,%.o,$(wildcard *.cc))


.SUFFIXES: .c .cpp .cxx .cc .o

.c.o:
	$(CC) $(CPPFLAGS) $(CFLAGS) $(ASFLAGS) -c $*.c $(INCLDIR)

.cpp.o:
	$(CXX) $(CPPFLAGS) $(CXXFLAGS) $(ASFLAGS) -c $< $(INCLDIR)

.cxx.o:
	$(CXX) $(CPPFLAGS) $(CXXFLAGS) $(ASFLAGS) -c $*.cxx $(INCLDIR)

.cc.o:
	$(CXX) $(CPPFLAGS) $(CXXFLAGS) $(ASFLAGS) -c $*.cc $(INCLDIR)



all : $(EXE)

$(EXE) : $(OBJS)
	$(CXX) $(LDFLAGS) -o $(EXE) $(OBJS) $(LIBDIR) $(LIBS)


clean:
	rm -f $(EXE) $(OBJS)
