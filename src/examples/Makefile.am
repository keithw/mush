AM_CPPFLAGS = $(CXX17_FLAGS) $(SSL_CFLAGS) -I$(srcdir)/../util -I$(srcdir)/../http -I$(srcdir)/../aws
AM_CXXFLAGS = $(PICKY_CXXFLAGS)

LAMBDA_FLAGS = -ldl -static -Wl,--whole-archive -lpthread -Wl,--no-whole-archive

bin_PROGRAMS = fun cat udp-reflect udp-receiver aws-fun

fun_SOURCES = fun.cc
fun_LDADD = ../http/libmushhttp.a ../util/libmushutil.a $(SSL_LIBS) $(srcdir)/../util/elf-info.ld

cat_SOURCES = cat.cc
cat_LDADD = ../util/libmushutil.a $(SSL_LIBS)

udp_reflect_SOURCES = udp-reflect.cc
udp_reflect_LDADD = ../util/libmushutil.a $(srcdir)/../util/elf-info.ld
udp_reflect_LDFLAGS = $(LAMBDA_FLAGS)

udp_receiver_SOURCES = udp-receiver.cc
udp_receiver_LDADD = ../util/libmushutil.a

aws_fun_SOURCES = aws-fun.cc
aws_fun_LDADD = ../aws/libmushaws.a ../http/libmushhttp.a ../util/libmushutil.a $(SSL_LIBS) $(srcdir)/../util/elf-info.ld
