**`onenetd`** is single-source-file utility that acts as a one-port `inetd`. 

Listens on a TCP port, accepts connections, and hooks them up to `stdin`/`stdout` 
(and optionally also `stderr`) of a program or script of your choice, just like
`inetd` used to in the Bad Old days. 

Great for faking a network service via a simple script for testing, demo, or 
hacking purposes. Environment variables passed into the subprogram let you 
track source and destination IPs and ports, as well as a unique sequence number 
for each connection.

Run `onenetd -h` for help, or see the included manual page. 

Get precompiled Linux binaries (glibc and musl-static) from [Releases](https://github.com/pducklin/onenetd/releases).

---

Original code from the early 2000s by Adam Sampson <ats@offog.org>

Tweaked from 1.11 to 1.11c by Paul Ducklin <pducklin@outlook.com> 

The `c` in the version string stands for `CONNCOUNT`. Search for the
text `CONNCOUNT` in the code and the man page for an explanation.

---

To build, `clang -O2 -o onenetd onenetd.c` should do the trick on most 
Unix-flavoured OSes. You can `strip onenetd` afterwards if you wish. 
That's all there is to it. If you prefer the GNU C compiler, just use 
`gcc` instead of `clang`.

To install, if that is not too dramatic a word for it, put `onenetd` 
somewhere in your path, and `onenetd.1` somewhere in your manpath. 

(This code used to have a configure script and a sea of autoconf stuff that
was ripped out in favour of the one-line build instruction above :-)
