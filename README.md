NAME
====

ncrsh - netcat reverse shell

SYNOPSIS
========

    ncrsh-server 12345

    ncrsh-client localhost 12345

DESCRIPTION
===========

_ncrsh_ allows to easily troubleshoot computers behind NAT. First,
start _ncrsh-server_ on the computer which will control the other one,
and then connect the other computer with it using _ncrsh-client_. The
computer with _ncrsh-server_ will control the one with _ncrsh-client_,
not the other way around (like in SSH). _ncrsh-client_ will print all
the things run by the _ncrsh-server_ back to the troubleshooted
computer so its user knows what is being done.

FAQ
===

**Q: Wouldn't a SSH tunnel suffice here?**

A: Yes, it would work. But you would have to give the troubleshooted
computer the login credentials to your computer and it's still more
complicated than sending a simple shell script (assuming netcat is
installed). As a bonus, _ncrsh_ allows both ends to see what is
happening without use of a terminal multiplexer like _screen_ or
_tmux_.

**Q: Is the connection encrypted?**

A: No, everything is sent in plaintext. You may use VPN or SSH tunnel
(I know, a bit ironic) to secure it.

**Q: May I run a curses or curses-like application via ncrsh?**

A: Yes and no. I've been successfully running Vim but there are quite
a few glitches. I would rather recommend sticking to alternatives like
_ed(1)_.

DEPENDENCIES
============

**ncrsh-server:**

* netcat
* rlwrap (optional; for readline support)

**ncrsh-client:**

* netcat
* zsh (for now; I'm going to rewrite it in bash)

AUTHOR
======

Wojciech 'vifon' Siewierski < wojciech dot siewierski at gmail dot com >

COPYRIGHT
=========

Copyright (C) 2012-2014  Wojciech Siewierski

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
