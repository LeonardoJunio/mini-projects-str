CXX = g++
CXXFLAGS = -Wall -Wextra -Wpedantic -std=c++11

SRCDIR = src
BINDIR = bin

LDLIBS = -lpthread

SRCS = $(wildcard $(SRCDIR)/*/*.cpp)
OBJS = $(patsubst $(SRCDIR)/%,$(BINDIR)/%,$(SRCS:.cpp=.o))

.PHONY: all clean

all: $(BINDIR)/app

$(BINDIR)/app: $(OBJS)
	$(CXX) $(LDFLAGS) $^ -o $@ $(LDLIBS)

$(BINDIR)/%.o: $(SRCDIR)/%.cpp | $(BINDIR)
	$(CXX) $(CXXFLAGS) $(CPPFLAGS) -c $< -o $@

$(BINDIR):
	mkdir -p $(BINDIR)

clean:
	$(RM) -r $(BINDIR)

