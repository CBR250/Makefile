Makefile
====================================

Purpose
-----------------
```
If source code don't include Makefile.
Please put the above file into your source code.
```

Edit Makefile.in 
------------------
```
Modify 
  BIN = I2C
  SRC_C = I2C.c
to
  BIN = <Any file name>
  SRC_C = <Any file name>.c <Any file name 2>.c  ... etc.
```
```
1. modify install - indicate file where want to install it
install: all
        mkdir -p $(DESTDIR)$(BINDIR) $(DESTDIR)$(MAN8DIR)
        mkdir -p $(DESTDIR)$(SYSCONFDIR)
        mkdir -p $(DESTDIR)$(RCDIR)
        install -D I2C                  $(DESTDIR)$(BINDIR)/I2C
to
install: all
        mkdir -p $(DESTDIR)$(BINDIR) $(DESTDIR)$(MAN8DIR)
        mkdir -p $(DESTDIR)$(SYSCONFDIR)
        mkdir -p $(DESTDIR)$(RCDIR)
        install -D <Any file name>                  $(DESTDIR)$(BINDIR)/<Any file name>
```
```
2. modify clean   - indicate file where want to delete it
clean:
        rm -f *.o
        rm -f ipband
to
clean:
        rm -f *.o
        rm -f <Any file name>
```
Start to work
------------------
Execute ./configure , then create Makefile for you source code
