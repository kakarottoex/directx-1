### Generated by Winemaker


SRCDIR                = .
SUBDIRS               =
DLLS                  =
EXES                  = triangle.exe



### Common settings

CEXTRA                = -mno-cygwin
CXXEXTRA              = -mno-cygwin
RCEXTRA               =
INCLUDE_PATH          =
DLL_PATH              =
LIBRARY_PATH          =
LIBRARIES             = -ld3d9


### triangle.exe sources and settings

triangle_exe_MODULE   = triangle.exe
triangle_exe_C_SRCS   =
triangle_exe_CXX_SRCS = triangle.cpp
triangle_exe_RC_SRCS  =
triangle_exe_LDFLAGS  = -mwindows \
			-mno-cygwin
triangle_exe_DLL_PATH =
triangle_exe_DLLS     = odbc32 \
			ole32 \
			oleaut32 \
			winspool
triangle_exe_LIBRARY_PATH=
triangle_exe_LIBRARIES= uuid

triangle_exe_OBJS     = $(triangle_exe_C_SRCS:.c=.o) \
			$(triangle_exe_CXX_SRCS:.cpp=.o) \
			$(triangle_exe_RC_SRCS:.rc=.res)



### Global source lists

C_SRCS                = $(triangle_exe_C_SRCS)
CXX_SRCS              = $(triangle_exe_CXX_SRCS)
RC_SRCS               = $(triangle_exe_RC_SRCS)


### Tools

CC = winegcc
CXX = wineg++
RC = wrc


### Generic targets

all: $(SUBDIRS) $(DLLS:%=%.so) $(EXES:%=%.so)

### Build rules

.PHONY: all clean dummy

$(SUBDIRS): dummy
	@cd $@ && $(MAKE)

# Implicit rules

.SUFFIXES: .cpp .rc .res
DEFINCL = $(INCLUDE_PATH) $(DEFINES) $(OPTIONS)

.c.o:
	$(CC) -c $(CFLAGS) $(CEXTRA) $(DEFINCL) -o $@ $<

.cpp.o:
	$(CXX) -c $(CXXFLAGS) $(CXXEXTRA) $(DEFINCL) -o $@ $<

.cxx.o:
	$(CXX) -c $(CXXFLAGS) $(CXXEXTRA) $(DEFINCL) -o $@ $<

.rc.res:
	$(RC) $(RCFLAGS) $(RCEXTRA) $(DEFINCL) -fo$@ $<

# Rules for cleaning

CLEAN_FILES     = y.tab.c y.tab.h lex.yy.c core *.orig *.rej \
                  \\\#*\\\# *~ *% .\\\#*

clean:: $(SUBDIRS:%=%/__clean__) $(EXTRASUBDIRS:%=%/__clean__)
	$(RM) $(CLEAN_FILES) $(RC_SRCS:.rc=.res) $(C_SRCS:.c=.o) $(CXX_SRCS:.cpp=.o)
	$(RM) $(DLLS:%=%.so) $(EXES:%=%.so) $(EXES:%.exe=%)

$(SUBDIRS:%=%/__clean__): dummy
	cd `dirname $@` && $(MAKE) clean

$(EXTRASUBDIRS:%=%/__clean__): dummy
	-cd `dirname $@` && $(RM) $(CLEAN_FILES)

### Target specific build rules
DEFLIB = $(LIBRARY_PATH) $(LIBRARIES) $(DLL_PATH)

$(triangle_exe_MODULE).so: $(triangle_exe_OBJS)
	$(CXX) $(triangle_exe_LDFLAGS) -o $@ $(triangle_exe_OBJS) $(triangle_exe_LIBRARY_PATH) $(DEFLIB) $(triangle_exe_DLLS:%=-l%) $(triangle_exe_LIBRARIES:%=-l%)


