#!/usr/bin/env make
#
# help - makefile for calc help files
#
# Copyright (C) 1999-2006,2017,2021-2023  Landon Curt Noll
#
# Suggestion: Read the ../HOWTO.INSTALL file.
#
# Calc is open software; you can redistribute it and/or modify it under
# the terms of the version 2.1 of the GNU Lesser General Public License
# as published by the Free Software Foundation.
#
# Calc is distributed in the hope that it will be useful, but WITHOUT
# ANY WARRANTY; without even the implied warranty of MERCHANTABILITY
# or FITNESS FOR A PARTICULAR PURPOSE.	See the GNU Lesser General
# Public License for more details.
#
# A copy of version 2.1 of the GNU Lesser General Public License is
# distributed with calc under the filename COPYING-LGPL.  You should have
# received a copy with calc; if not, write to Free Software Foundation, Inc.
# 51 Franklin Street, Fifth Floor, Boston, MA  02110-1301, USA.
#
# Under source code control:	1991/07/23 06:47:57
# File existed as early as:	1991
#
# This calculator first developed by David I. Bell with help/mods from others.
#
# chongo <was here> /\oo/\	http://www.isthe.com/chongo/
# Share and enjoy!  :-)		http://www.isthe.com/chongo/tech/comp/calc/


# SUGGESTION: Instead of modifying this file, consider adding
#	      statements to modify, replace or append Makefile
#	      variables in the ../Makefile.local file.


###########################################
# Files used or included by this Makefile #
###########################################

# Normally certain files depend on the Makefile.  If the Makefile is
# changed, then certain steps should be redone.  If MAKE_FILE is
# set to Makefile, then these files will depend on Makefile.  If
# MAKE_FILE is empty, then they won't.
#
# If in doubt, set MAKE_FILE to Makefile
#
MAKE_FILE= Makefile

# Calc configuration and compile configuration values
#
CONFIG_MKF= ../Makefile.config

# Host targets that are shared in common with both Makefile
# and custom/Makefile.
#
TARGET_MKF= ../Makefile.target

# Host target information.
#
LOCAL_MKF= ../Makefile.local

# The set of Makefiles
#
MK_SET= ${MAKE_FILE} ${CONFIG_MKF} ${TARGET_MKF} ${LOCAL_MKF}


#######################################################
# Calc configuration and compile configuration values #
#######################################################
include ${CONFIG_MKF}


###############################
# host target section include #
###############################
include ${TARGET_MKF}


##########################################################################
#=-=-=-=-=- Be careful if you change something below this line -=-=-=-=-=#
##########################################################################

# Makefile debug
#
# Q=@	do not echo internal Makefile actions (quiet mode)
# Q=	echo internal Makefile actions (debug / verbose mode)
#
# H=@:	do not report hsrc file formation progress
# H=@	do echo hsrc file formation progress
#
# S= >/dev/null 2>&1	silence ${CC} output during hsrc file formation
# S=			full ${CC} output during hsrc file formation
#
# E= 2>/dev/null	silence command stderr during hsrc file formation
# E=			full command stderr during hsrc file formation
#
# V=@:	do not echo debug statements (quiet mode)
# V=@	do echo debug statements (debug / verbose mode)
#
#Q=
Q=@
#
S= >/dev/null 2>&1
#S=
#
E= 2>/dev/null
#E=
#
#H=@:
H=@
#
V=@:
#V=@


##################################
# Files managed by this Makefile #
##################################

STD_HELP_FILES_1= intro overview
BLT_HELP_FILES_1a= calc

STD_HELP_FILES_2= assoc
BLT_HELP_FILES_3= builtin
STD_HELP_FILES_4= command config custom define environment
BLT_HELP_FILES_5= errorcodes
STD_HELP_FILES_6= expression file history interrupt list mat
# because obj is built special (due to confusion with it as
# a symlink for some built environments, we treat obj specially
# and call it obj.file
#
SPECIAL_HELP_7= obj.file
STD_HELP_FILES_8= operator
BLT_HELP_FILES_9= resource
STD_HELP_FILES_10= script statement types unexpected variable

BLT_HELP_FILES_11= bindings custom_cal libcalc new_custom cscript

STD_HELP_FILES_12= archive
BLT_HELP_FILES_13= bugs changes contrib
STD_HELP_FILES_14= todo wishlist

STD_HELP_FILES_15= credit
# copyright is printed by help.c is from the Copyright string found in version.c
BLT_HELP_FILES_16= COPYING COPYING-LGPL questions releases

STD_HELP_FILES_17= help

# These files are used in the following order to construct full
#
FULL_HELP_FILES= ${STD_HELP_FILES_1} ${BLT_HELP_FILES_1a} \
		 ${STD_HELP_FILES_2} \
		 ${BLT_HELP_FILES_3}  ${STD_HELP_FILES_4} \
		 ${BLT_HELP_FILES_5}  ${STD_HELP_FILES_6} \
		 ${SPECIAL_HELP_7}    ${STD_HELP_FILES_8} \
		 ${BLT_HELP_FILES_9}  ${STD_HELP_FILES_10} \
		 ${BLT_HELP_FILES_11} ${STD_HELP_FILES_12} \
		 ${BLT_HELP_FILES_13} ${STD_HELP_FILES_14} \
		 ${STD_HELP_FILES_15} ${BLT_HELP_FILES_16} \
		 ${STD_HELP_FILES_17}

# These full files are those who are not built or constructed
#
STD_HELP_FILES= ${STD_HELP_FILES_1}  ${STD_HELP_FILES_2} \
		${STD_HELP_FILES_4}  ${STD_HELP_FILES_6} \
		${STD_HELP_FILES_8}  ${STD_HELP_FILES_10} \
		${STD_HELP_FILES_12} ${STD_HELP_FILES_14} \
		${STD_HELP_FILES_15} ${STD_HELP_FILES_17}

# These full files are those who are built by this Makefile
#
# Note that ${SPECIAL_HELP_7} is not included in this list
# because of problems with its name.
#
BLT_HELP_FILES= ${BLT_HELP_FILES_1a} \
		${BLT_HELP_FILES_3}  ${BLT_HELP_FILES_5} \
		${BLT_HELP_FILES_9}  ${BLT_HELP_FILES_11} \
		${BLT_HELP_FILES_13} ${BLT_HELP_FILES_16}

# The detailed list of help files to install
#
# This list is produced by the detaillist rule when no WARNINGS are detected.
#
# Please use:
#
#	make clobber >/dev/null && make detail_help_list
#
# to keep this list in nice sorted order.
#
DETAIL_HELP= abs access acos acosh acot acoth acovercos acoversin \
	acrd acsc acsch address aexcsc aexsec agd ahacovercos ahacoversin \
	ahavercos ahaversin append appr arg argv arrow asec asech asin asinh \
	assign atan atan2 atanh avercos aversin avg base base2 bernoulli bit \
	blk blkcpy blkfree blocks bround btrunc calc_tty calclevel calcpath \
	cas catalan ceil cfappr cfsim char cis cmdbuf cmp comb conj cos cosh \
	cot coth count covercos coversin cp crd csc csch ctime d2dm d2dms d2g \
	d2r delete den dereference det digit digits display dms2d dp epsilon \
	errcount errmax errno error errsym estr euler eval excsc exp exsec \
	fact factor fclose fcnt feof ferror fflush fgetc fgetfield fgetfile \
	fgetline fgets fgetstr fib files floor fopen forall fpathopen fprintf \
	fputc fputs fputstr frac free freebernoulli freeeuler freeglobals \
	freeredc freestatics frem freopen fscan fscanf fseek fsize ftell g2d \
	g2gm g2gms g2r gcd gcdrem gd getenv gms2g h2hm h2hms hacovercos \
	hacoversin hash havercos haversin head highbit hmean hms2h hnrmod \
	hypot ilog ilog10 ilog2 im indices inputlevel insert int inverse iroot \
	isalnum isalpha isassoc isatty isblk iscntrl isconfig isdefined \
	isdigit iserror iseven isfile isgraph ishash isident isint islist \
	islower ismat ismult isnull isnum isobj isobjtype isodd isprime \
	isprint isptr ispunct isqrt isrand israndom isreal isrel issimple \
	isspace issq isstr istype isupper isxdigit jacobi join lcm lcmfact \
	lfactor ln log log2 logn lowbit ltol makelist matdim matfill matmax \
	matmin matsum mattrace mattrans max memsize meq min minv mmin mne mod \
	modify name near newerror nextcand nextprime norm null num oldvalue \
	ord param perm pfact pi pix places pmod polar poly pop popcnt pound \
	power prevcand prevprime printf prompt protect ptest push putenv quo \
	quomod r2d r2g rand randbit random randombit randperm rcin rcmul rcout \
	rcpow rcsq re remove reverse rewind rm root round rsearch runtime \
	saveval scale scan scanf search sec sech seed segment select sgn sha1 \
	sin sinh size sizeof sleep sort sqrt srand srandom ssq stoponerror str \
	strcasecmp strcat strcmp strcpy strerror strlen strncasecmp strncmp \
	strncpy strpos strprintf strscan strscanf strtolower strtoupper substr \
	sum swap system systime tail tan tanh test time trunc usertime vercos \
	versin version xor

# This list is of files that are clones of DETAIL_HELP files.  They are
# built from DETAIL_HELP files.
#
DETAIL_CLONE= copy ilogn

# Singular files
#
# These files are copies of their plural form.
#
PLURAL_FILES= bindings bugs changes errorcodes types
SINGULAR_FILES= binding bug change errorcode type

# These files are found (but not built) in the distribution
#
DISTLIST= ${STD_HELP_FILES} ${DETAIL_HELP} ${MAKE_FILE} \
	obj.file builtin.top builtin.end funclist.sed

# These files are used to make (but not built) a calc .a link library
#
CALCLIBLIST=

# complete list of files that may be created as part of the build process
#
# Used by chk_tree via make prep
#
BUILD_ALL= ${BLT_HELP_FILES} ${SINGULAR_FILES} ${DETAIL_CLONE} \
	   full funclist${EXT} funclist.c funclist.o

# rules that are not also names of files
#
PHONY= all distlist buildlist distdir calcliblist detail_help_list \
	echo_inst_files clean clobber install uninstall


############################################################
# Allow Makefile.local to change any of the above settings #
############################################################
include ${LOCAL_MKF}


###########################################
# all - First and default Makefile target #
###########################################

all: ${FULL_HELP_FILES} full ${DETAIL_HELP} ${DETAIL_CLONE} \
     ${SINGULAR_FILES} .all


###############################
# additional Makefile targets #
###############################

.PHONY: ${PHONY}

# used by the upper level Makefile to determine of we have done all
#
# NOTE: Due to bogus shells found on one common system we must have
#	an non-empty else clause for every if condition.  *sigh*
#
.all:
	${RM} -f .all
	${TOUCH} .all

bindings: ../cal/bindings
	${RM} -f $@
	${CP} ../cal/bindings $@
	${CHMOD} 0444 $@
	-@if [ -z "${Q}" ]; then \
	    echo ''; \
	    echo '=-=-= skipping the ${CAT} of help/$@ =-=-='; \
	    echo ''; \
	else \
	    ${TRUE}; \
	fi

resource: ../cal/README
	${RM} -f $@
	${CP} ../cal/README $@
	${CHMOD} 0444 $@
	-@if [ -z "${Q}" ]; then \
	    echo ''; \
	    echo '=-=-= skipping the ${CAT} of help/$@ =-=-='; \
	    echo ''; \
	else \
	    ${TRUE}; \
	fi

changes: ../CHANGES
	${RM} -f $@
	${CP} ../CHANGES $@
	${CHMOD} 0444 $@
	-@if [ -z "${Q}" ]; then \
	    echo ''; \
	    echo '=-=-= skipping the ${CAT} of help/$@ =-=-='; \
	    echo ''; \
	else \
	    ${TRUE}; \
	fi

libcalc: ../LIBRARY
	${RM} -f $@
	${SED} -e 's:$${LIBDIR}:${LIBDIR}:g' \
	       -e 's:$${CALC_INCDIR}:${CALC_INCDIR}:g' < ../LIBRARY > $@
	${CHMOD} 0444 $@
	-@if [ -z "${Q}" ]; then \
	    echo ''; \
	    echo '=-=-= skipping the ${CAT} of help/$@ =-=-='; \
	    echo ''; \
	else \
	    ${TRUE}; \
	fi

bugs: ../BUGS
	${RM} -f $@
	${CP} ../BUGS $@
	${CHMOD} 0444 $@
	-@if [ -z "${Q}" ]; then \
	    echo ''; \
	    echo '=-=-= skipping the ${CAT} of help/$@ =-=-='; \
	    echo ''; \
	else \
	    ${TRUE}; \
	fi

contrib: ../CONTRIB-CODE
	${RM} -f $@
	${CP} ../CONTRIB-CODE $@
	${CHMOD} 0444 $@
	-@if [ -z "${Q}" ]; then \
	    echo ''; \
	    echo '=-=-= skipping the ${CAT} of help/$@ =-=-='; \
	    echo ''; \
	else \
	    ${TRUE}; \
	fi

errorcodes: ../errcode${EXT}
	${RM} -f $@
	../errcode${EXT} -e > $@
	${CHMOD} 0444 $@
	-@if [ -z "${Q}" ]; then \
	    echo ''; \
	    echo '=-=-= skipping the ${CAT} of help/$@ =-=-='; \
	    echo ''; \
	else \
	    ${TRUE}; \
	fi

calc: ../calc.usage
	${RM} -f $@
	${CP} ../calc.usage $@
	${CHMOD} 0444 $@
	-@if [ -z "${Q}" ]; then \
	    echo ''; \
	    echo '=-=-= skipping the ${CAT} of help/$@ =-=-='; \
	    echo ''; \
	else \
	    ${TRUE}; \
	fi

../calc.usage:
	(cd ..; ${MAKE} -f ${MAKE_FILE} calc.usage)

custom_cal: ../custom/CUSTOM_CAL
	${RM} -f $@
	${CP} ../custom/CUSTOM_CAL $@
	${CHMOD} 0444 $@
	-@if [ -z "${Q}" ]; then \
	    echo ''; \
	    echo '=-=-= skipping the ${CAT} of help/$@ =-=-='; \
	    echo ''; \
	else \
	    ${TRUE}; \
	fi

new_custom: ../custom/HOW_TO_ADD
	${RM} -f $@
	${CP} ../custom/HOW_TO_ADD $@
	${CHMOD} 0444 $@
	-@if [ -z "${Q}" ]; then \
	    echo ''; \
	    echo '=-=-= skipping the ${CAT} of help/$@ =-=-='; \
	    echo ''; \
	else \
	    ${TRUE}; \
	fi

copy: blkcpy
	${RM} -f $@
	${CP} blkcpy $@
	${CHMOD} 0444 $@
	-@if [ -z "${Q}" ]; then \
	    echo ''; \
	    echo '=-=-= skipping the ${CAT} of help/$@ =-=-='; \
	    echo ''; \
	else \
	    ${TRUE}; \
	fi

COPYING: ../COPYING
	${RM} -f $@
	${CP} ../COPYING $@
	${CHMOD} 0444 $@
	-@if [ -z "${Q}" ]; then \
	    echo ''; \
	    echo '=-=-= skipping the ${CAT} of help/$@ =-=-='; \
	    echo ''; \
	else \
	    ${TRUE}; \
	fi

COPYING-LGPL: ../COPYING-LGPL
	${RM} -f $@
	${CP} ../COPYING-LGPL $@
	${CHMOD} 0444 $@
	-@if [ -z "${Q}" ]; then \
	    echo ''; \
	    echo '=-=-= skipping the ${CAT} of help/$@ =-=-='; \
	    echo ''; \
	else \
	    ${TRUE}; \
	fi

questions: ../QUESTIONS
	${RM} -f $@
	${CP} ../QUESTIONS $@
	${CHMOD} 0444 $@
	-@if [ -z "${Q}" ]; then \
	    echo ''; \
	    echo '=-=-= skipping the ${CAT} of help/$@ =-=-='; \
	    echo ''; \
	else \
	    ${TRUE}; \
	fi

cscript: ../cscript/README
	${RM} -f $@
	${CP} ../cscript/README $@
	${CHMOD} 0444 $@
	-@if [ -z "${Q}" ]; then \
	    echo ''; \
	    echo '=-=-= skipping the ${CAT} of help/$@ =-=-='; \
	    echo ''; \
	else \
	    ${TRUE}; \
	fi

../cscript/README: ../cscript/README.src
	${Q} echo "forming cscript/README"
	${Q} ${RM} -f $@
	(cd ../cscript; ${MAKE} -f Makefile README)

releases: ../README.RELEASE
	${RM} -f $@
	${CP} ../README.RELEASE $@
	${CHMOD} 0444 $@
	-@if [ -z "${Q}" ]; then \
	    echo ''; \
	    echo '=-=-= skipping the ${CAT} of help/$@ =-=-='; \
	    echo ''; \
	else \
	    ${TRUE}; \
	fi

ilogn: ilog
	${RM} -f $@
	${CP} ilog $@
	${CHMOD} 0444 $@
	-@if [ -z "${Q}" ]; then \
	    echo ''; \
	    echo '=-=-= skipping the ${CAT} of help/$@ =-=-='; \
	    echo ''; \
	else \
	    ${TRUE}; \
	fi

full: ${FULL_HELP_FILES} ${MAKE_FILE}
	${Q} echo "forming full"
	${Q} ${RM} -f $@
	-${Q} for i in ${FULL_HELP_FILES}; do \
	    if [ Xintro != X"$$i" ]; then \
		echo ""; \
	    else \
		${TRUE}; \
	    fi; \
	    if [ Xobj.file = X"$$i" ]; then \
		j=obj; \
	    else \
		j=$$i; \
	    fi; \
	    echo "*************"; \
	    echo "* $$j"; \
	    echo "*************"; \
	    echo ""; \
	    ${CAT} $$i; \
	done > $@
	${Q} echo "full formed"
	-@if [ -z "${Q}" ]; then \
	    echo ''; \
	    echo '=-=-= skipping the ${CAT} of help/$@ =-=-='; \
	    echo ''; \
	else \
	    ${TRUE}; \
	fi

# Singular files are the same files as their plural form.
#
${SINGULAR_FILES}: ${PLURAL_FILES}
	${Q} for i in ${SINGULAR_FILES} /dev/null; do \
	    if [ X"$$i" != X"/dev/null" ]; then \
		echo "${RM} -f $${i}"; \
		${RM} -f $${i}; \
		echo "${CP} $${i}s $${i}"; \
		${CP} $${i}s $${i}; \
	    fi; \
	done
	-@if [ -z "${Q}" ]; then \
	    echo ''; \
	    echo '=-=-= skipping the ${CAT} of help/SINGULAR_FILES =-=-='; \
	    echo ''; \
	else \
	    ${TRUE}; \
	fi

# Form the builtin file
#
# We have a "chicken-and-egg" problem.  We want the builtin help file to
# accurately reflect the function list.	 It would be nice if we could
# just execute calc show builtin, but calc may not have been built or
# build-able at this point.  The hack-a-round used is to convert ../func.c
# into a stand-alone program that generates a suitable function list
# that is sandwiched between the top and bottom builtin help text.
#
# We form funclist.c by sed-ing out unwanted stuff from builtins table,
# converting NUMBER* and VALUE into harmless types and converting
# the showbuiltins() function into main().  Combined with the -DFUNCLIST
# we will avoid all of the complex calc types, macros and defines and
# be left with just main() and a minimal builtins table.
#
# Building funclist.o a portable fashion is ugly because some systems
# do not treat -I.. correctly!
#
builtin: builtin.top builtin.end ../func.c funclist.sed
	${Q} echo "forming builtin help file"
	${Q} ${RM} -f funclist.c
	${Q} ${SED} -n -f funclist.sed ../func.c > funclist.c
	${Q} ${RM} -f funclist.o funclist${EXT}
	${Q} ${LCC} ${ICFLAGS} -DFUNCLIST -I/usr/include \
	    -I.. funclist.c -c ${S}
	${Q} ${LCC} ${ILDFLAGS} funclist.o -o funclist${EXT} ${S}
	${Q} ${RM} -f builtin
	${Q} ${GREP} -E -v '^#'  builtin.top > builtin
	${Q} ./funclist${EXT} | \
	    ${SED} -e 's/^/	/' -e 's/[	 ][	 ]*$$//' >> builtin
	${Q} ${CAT} builtin.end >> builtin
	${Q} echo "builtin help file formed"
	-@if [ -z "${Q}" ]; then \
	    echo ''; \
	    echo '=-=-= skipping the ${CAT} of help/$@ =-=-='; \
	    echo ''; \
	else \
	    ${TRUE}; \
	fi

##
#
# File list generation.	 You can ignore this section.
#
#
# We will form the names of source files as if they were in a
# sub-directory called calc/help.
#
##

distlist: ${DISTLIST}
	${Q} for i in ${DISTLIST} /dev/null; do \
	    if [ X"$$i" != X"/dev/null" ]; then \
		echo help/$$i; \
	    fi; \
	done | fgrep -v '.bak' | LANG=C ${SORT}

buildlist:
	${Q} for i in ${BUILD_ALL} /dev/null; do \
	    if [ X"$$i" != X"/dev/null" ]; then \
		echo help/$$i; \
	    fi; \
	done | fgrep -v '.bak' | LANG=C ${SORT}

distdir:
	${Q} echo help

calcliblist:
	${Q} for i in ${CALCLIBLIST} /dev/null; do \
	    if [ X"$$i" != X"/dev/null" ]; then \
		echo help/$$i; \
	    fi; \
	done

# These next rule help form the ${DETAIL_HELP} makefile variables above.
#
# NOTE: The ${DETAIL_HELP} list does not include special help files.
#
detail_help_list:
	${Q} -(find .  -mindepth 1 -maxdepth 1 -type f \
	         ! -name Makefile ! -name '.Makefile.swp' \
		 ! -name archive ! -name assoc ! -name builtin.end \
		 ! -name builtin.top ! -name command ! -name config \
		 ! -name contrib ! -name credit ! -name custom ! -name define \
		 ! -name environment ! -name expression ! -name file \
		 ! -name funclist.c ! -name funclist.sed ! -name help \
		 ! -name history ! -name interrupt ! -name intro ! -name list \
		 ! -name mat ! -name obj.file ! -name operator \
		 ! -name overview ! -name script ! -name statement \
		 ! -name todo ! -name types ! -name unexpected \
		 ! -name variable ! -name wishlist ! -name questions \
		 -print | \
	   while read i; do \
		if [ X"$$i" != X"/dev/null" ]; then \
		    echo $$i; \
		fi; \
	done; \
	echo '--first_line--') | \
	    ${SED} -e 's:^\./::' | LANG=C ${SORT} | ${FMT} -70 | \
	    ${SED} -e '1s/--first_line--/DETAIL_HELP=/' -e '2,$$s/^/	/' \
		   -e 's/$$/ \\/' -e '$$s/ \\$$//'

##
#
# rpm rules
#
##

echo_inst_files:
	${Q} for i in ${STD_HELP_FILES} full ${BLT_HELP_FILES} \
		  builtin ${DETAIL_HELP} ${SINGULAR_FILES} /dev/null; do \
	    if [ X"$$i" != X"/dev/null" ]; then \
		echo __file__ ${HELPDIR}/$$i; \
	    fi; \
	done
	${Q} echo __file__ ${HELPDIR}/obj

##
#
# Utility rules
#
##

clean:
	${RM} -f obj mkbuiltin funclist.c funclist.o funclist${EXT}
	${RM} -f COPYING COPYING-LGPL questions

clobber: clean
	${RM} -f ${BLT_HELP_FILES} full .all calc
	${RM} -f ${SINGULAR_FILES} ${DETAIL_CLONE}
	-${Q} if [ -e .DS_Store ]; then \
	    echo ${RM} -rf .DS_Store; \
	    ${RM} -rf .DS_Store; \
	fi

# install everything
#
# NOTE: Keep the uninstall rule in reverse order to the install rule
#
install: all
	-${Q} if [ ! -d ${T}${CALC_SHAREDIR} ]; then \
	    echo ${MKDIR} -p ${T}${CALC_SHAREDIR}; \
	    ${MKDIR} -p ${T}${CALC_SHAREDIR}; \
	    if [ ! -d "${T}${CALC_SHAREDIR}" ]; then \
		echo ${MKDIR} -p "${T}${CALC_SHAREDIR}"; \
		${MKDIR} -p "${T}${CALC_SHAREDIR}"; \
	    fi; \
	    echo ${CHMOD} 0755 ${T}${CALC_SHAREDIR}; \
	    ${CHMOD} 0755 ${T}${CALC_SHAREDIR}; \
	else \
	    ${TRUE}; \
	fi
	-${Q} if [ ! -d ${T}${HELPDIR} ]; then \
	    echo ${MKDIR} -p ${T}${HELPDIR}; \
	    ${MKDIR} -p ${T}${HELPDIR}; \
	    if [ ! -d "${T}${HELPDIR}" ]; then \
		echo ${MKDIR} -p "${T}${HELPDIR}"; \
		${MKDIR} -p "${T}${HELPDIR}"; \
	    fi; \
	    echo ${CHMOD} 0755 ${T}${HELPDIR}; \
	    ${CHMOD} 0755 ${T}${HELPDIR}; \
	else \
	    ${TRUE}; \
	fi
	-${Q} for i in ${STD_HELP_FILES} ${BLT_HELP_FILES} builtin \
		  full ${DETAIL_HELP} ${SINGULAR_FILES} /dev/null; do \
	    if [ "$$i" = "/dev/null" ]; then \
		continue; \
	    fi; \
	    if ${CMP} -s $$i ${T}${HELPDIR}/$$i; then \
		${TRUE}; \
	    else \
		${RM} -f ${T}${HELPDIR}/$$i.new; \
		${CP} -f $$i ${T}${HELPDIR}/$$i.new; \
		${CHMOD} 0444 ${T}${HELPDIR}/$$i.new; \
		${MV} -f ${T}${HELPDIR}/$$i.new ${T}${HELPDIR}/$$i; \
		echo "installed ${T}${HELPDIR}/$$i"; \
	    fi; \
	done
	-${Q} if ${CMP} -s obj.file ${T}${HELPDIR}/obj; then \
	    ${TRUE}; \
	else \
	    ${RM} -f ${T}${HELPDIR}/obj.new; \
	    ${CP} -f obj.file ${T}${HELPDIR}/obj.new; \
	    ${CHMOD} 0444 ${T}${HELPDIR}/obj.new; \
	    ${MV} -f ${T}${HELPDIR}/obj.new ${T}${HELPDIR}/obj; \
	    echo "installed ${T}${HELPDIR}/obj"; \
	fi
	-${Q} if [ -f "${T}${HELPDIR}/sha" ]; then \
	    ${RM} -f ${T}${HELPDIR}/sha; \
	    echo "removed old ${T}${HELPDIR}/sha"; \
	fi;
	-${Q} if [ -f "${T}${HELPDIR}/md5" ]; then \
	    ${RM} -f ${T}${HELPDIR}/md5; \
	    echo "removed old ${T}${HELPDIR}/md5"; \
	fi;

# Try to remove everything that was installed
#
# NOTE: Keep the uninstall rule in reverse order to the install rule
#
uninstall:
	-${Q} if [ -f "${T}${HELPDIR}/obj" ]; then \
	    ${RM} -f "${T}${HELPDIR}/obj"; \
	    if [ -f "${T}${HELPDIR}/obj" ]; then \
		echo "cannot uninstall ${T}${HELPDIR}/obj"; \
	    else \
		echo "uninstalled ${T}${HELPDIR}/obj"; \
	    fi; \
	fi
	-${Q} for i in ${SINGULAR_FILES} ${DETAIL_HELP} full builtin \
	    ${BLT_HELP_FILES} ${STD_HELP_FILES} /dev/null; do \
	    if [ "$$i" = "/dev/null" ]; then \
		continue; \
	    fi; \
	    if [ -f "${T}${HELPDIR}/$$i" ]; then \
		${RM} -f "${T}${HELPDIR}/$$i"; \
		if [ -f "${T}${HELPDIR}/$$i" ]; then \
		   echo "cannot uninstall ${T}${HELPDIR}/$$i"; \
		else \
		   echo "uninstalled ${T}${HELPDIR}/$$i"; \
		fi; \
	    fi; \
	done
	-${Q} for i in ${HELPDIR} ${CALC_SHAREDIR}; do \
	    if [ -d "${T}$$i" ]; then \
		${RMDIR} "${T}$$i" 2>/dev/null; \
		echo "cleaned up ${T}$$i"; \
	    fi; \
	done
