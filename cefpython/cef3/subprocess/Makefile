# -g - extra debug information
# -O1 - more precise backtraces
# -fPIC - required when using -shared option, required for use with Cython
# -Wall - show important warnings
# -Werror - treat warnings as errors

INC = -I./../ -I/usr/include/python2.7 -I/usr/include/gtk-2.0 \
	-I/usr/include/glib-2.0 -I/usr/lib/i386-linux-gnu/gtk-2.0/include \
	-I/usr/lib/i386-linux-gnu/glib-2.0/include -I/usr/include/cairo \
	-I/usr/include/pango-1.0 -I/usr/include/gdk-pixbuf-2.0 \
	-I/usr/include/atk-1.0 -I/usr/lib/x86_64-linux-gnu/glib-2.0/include \
	-I/usr/lib/x86_64-linux-gnu/gtk-2.0/include

LIB = -L./../linux/setup/lib_64bit -L./../linux/setup/lib_32bit \
	-L./../linux/binaries_64bit -L./../linux/binaries_32bit

CCFLAGS = -g -Wall -Werror -DRENDERER_PROCESS

subprocess:
	# -fPIC is required only for libraries included by Cython.
	g++ $(CCFLAGS) $(INC) $(LIB) main.cpp cefpython_app.cpp \
		v8function_handler.cpp v8utils.cpp javascript_callback.cpp \
		-lcef_dll_wrapper -lcef -o subprocess -Wl,-rpath,.
