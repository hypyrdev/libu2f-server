# Copyright (c) 2014 Yubico AB
# All rights reserved.
#
# Redistribution and use in source and binary forms, with or without
# modification, are permitted provided that the following conditions are
# met:
#
# # Redistributions of source code must retain the above copyright
# notice, this list of conditions and the following disclaimer.
#
# # Redistributions in binary form must reproduce the above
# copyright notice, this list of conditions and the following
# disclaimer in the documentation and/or other materials provided
# with the distribution.
#
# THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
# "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
# LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
# A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT
# OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
# SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT
# LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
# DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY
# THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
# (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
# OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

AM_CFLAGS = $(WARN_CFLAGS)
AM_CFLAGS += -DMAKE_CHECK
AM_CPPFLAGS=-I$(srcdir)/.. -I$(builddir)/..
AM_CPPFLAGS+=$(LIBSSL_CFLAGS) $(LIBCRYPTO_CFLAGS)

AM_LDFLAGS = -no-install

if ENABLE_COV
AM_CFLAGS += --coverage
AM_LDFLAGS += --coverage
endif

LDADD = $(top_builddir)/u2f-server/libu2f-server.la
LDADD += $(CHECK_LIBS) $(LIBSSL_LIBS) $(LIBCRYPTO_LIBS)

check_PROGRAMS = basic core openssl
dist_check_SCRIPTS = u2f-server-test.sh
TESTS = $(check_PROGRAMS) u2f-server-test.sh

TEST_EXTENSIONS = .sh
SH_LOG_COMPILER = $(SHELL)
AM_SH_LOG_FLAGS =
