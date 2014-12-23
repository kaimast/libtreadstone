## Copyright (c) 2014, Robert Escriva
## All rights reserved.
##
## Redistribution and use in source and binary forms, with or without
## modification, are permitted provided that the following conditions are met:
##
##     * Redistributions of source code must retain the above copyright notice,
##       this list of conditions and the following disclaimer.
##     * Redistributions in binary form must reproduce the above copyright
##       notice, this list of conditions and the following disclaimer in the
##       documentation and/or other materials provided with the distribution.
##     * Neither the name of libtreadstone nor the names of its contributors may
##       be used to endorse or promote products derived from this software
##		 without specific prior written permission.
##
## THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
## AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
## IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE
## ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT OWNER OR CONTRIBUTORS BE
## LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR
## CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF
## SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS
## INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN
## CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE)
## ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE
## POSSIBILITY OF SUCH DAMAGE.

ACLOCAL_AMFLAGS = -I m4 ${ACLOCAL_FLAGS}

AM_CPPFLAGS  = -I${abs_top_srcdir}/include
AM_CFLAGS    = -fvisibility=hidden $(WANAL_CFLAGS)
AM_CXXFLAGS  = -fvisibility=hidden -fvisibility-inlines-hidden $(WANAL_CXXFLAGS)
AM_MAKEFLAGS = --no-print-directory
AM_YFLAGS = -d

EXTRA_DIST =
EXTRA_DIST += LICENSE
EXTRA_DIST += doc/binary.txt

include_HEADERS = include/treadstone.h

noinst_HEADERS =
noinst_HEADERS += namespace.h
noinst_HEADERS += visibility.h

lib_LTLIBRARIES =
lib_LTLIBRARIES += libtreadstone.la

libtreadstone_la_SOURCES =
libtreadstone_la_SOURCES += treadstone.cc
libtreadstone_la_LIBADD = -le

pkgconfigdir = $(libdir)/pkgconfig
pkgconfig_DATA =
pkgconfig_DATA += libtreadstone.pc

noinst_PROGRAMS = treadstone-json-validate

treadstone_json_validate_SOURCES = treadstone-json-validate.cc
treadstone_json_validate_LDADD = libtreadstone.la -le

check_PROGRAMS =
check_PROGRAMS += test/transforms
check_PROGRAMS += test/validate-path

th_sources = test/th_main.cc test/th.cc test/th.h

test_transforms_SOURCES = test/transforms.cc $(th_sources)
test_transforms_LDADD = libtreadstone.la

test_validate_path_SOURCES = test/validate-path.cc $(th_sources)
test_validate_path_LDADD = libtreadstone.la

TESTS =
TESTS += test/transforms
TESTS += test/validate-path