# stupid-c-repl

This is a stupid REPL for C and C++. It writes the program to a
temporary file and compiles it every time you press enter.

## Examples

Hello World!!!

    $ python3 crepl.py
    >>> #include <stdio.h>
    >>> printf("Hello World!!!\n");
    Hello World!!!
    >>> 

Hello World with C++

    $ CC=c++ python3 crepl.py
    >>> #include <iostream>
    >>> std::cout << "Hello World!\n";
    Hello World!
    >>> 

Variables

    $ python3 crepl.py
    >>> #include <stdio.h>
    >>> char s[] = "Hello World!"; \
    ... printf("%s\n", s);
    Hello World!
    >>> 

If, else, switch and case

    $ python3 crepl.py
    >>> #include <stdio.h>
    >>> int i = 1; \
    ... if (i == 1) { \
    ...     printf("It's working!\n"); \
    ... } else { \
    ...     printf("It's not working!\n"); \
    ... }
    It's working!
    >>> int i = 1; \
    ... switch (i) { \
    ... case 1: \
    ...     printf("It's working!\n"); \
    ...     break; \
    ... default: \
    ...     printf("It's not working!"); \
    ...     break; \
    ... }
    It's working!
    >>> 

Hello World with GTK+ 3

    $ CFLAGS="`pkg-config --cflags gtk+-3.0`" LIBS="`pkg-config --libs gtk+-3.0`" python3 crepl.py
    >>> #include <gtk/gtk.h>
    >>> gtk_init(&argc, &argv); \
    ... GtkWidget *window = gtk_window_new(GTK_WINDOW_TOPLEVEL); \
    ... gtk_container_add(GTK_CONTAINER(window), gtk_label_new("Hello!")); \
    ... g_signal_connect(window, "delete-event", gtk_main_quit, NULL); \
    ... gtk_widget_show_all(window); \
    ... gtk_main();
    >>> 

Hello World with Python

    $ CFLAGS="`pkg-config --cflags python3`" LIBS="`pkg-config --libs python3`" python3 crepl.py
    >>> Py_Initialize(); \
    ... PyRun_SimpleString("print('Hello World!')"); \
    ... Py_Finalize();
    Hello World!
    >>> 
