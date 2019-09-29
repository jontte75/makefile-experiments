CXX := g++
CXXFLAGS += -Wall -std=c++17

LIBSRCS = $(filter-out ./main.cc,$(shell find -name \*.cc))
LIBOBJS = $(patsubst %.cc,%.o,$(LIBSRCS))
LDFLAGS += -L. -lproject

main: main.o libproject.a
	$(CXX) $(CPPFLAGS) $(CXXFLAGS) -o $@ $< $(LDFLAGS) 

libproject.a: $(LIBOBJS)
	ar rcs $@ $^

.PHONY: clean
clean:
	rm -f libproject.a $(LIBOBJS) main main.o

