# Else exists specifically for clang
ifeq ($(CXX),g++)
    EXTRA_FLAGS = --no-gnu-unique
else
    EXTRA_FLAGS =
endif

CXXFLAGS ?= -O2
CXXFLAGS += -shared -fPIC -std=c++2b

TARGET = hyprwinwrap.so

all:
	$(CXX) $(CXXFLAGS) $(LDFLAGS) $(EXTRA_FLAGS) main.cpp -o $(TARGET) \
	`pkg-config --cflags --libs pixman-1 libdrm hyprland pangocairo libinput libudev wayland-server xkbcommon`

clean:
	rm -f ./$(TARGET)
