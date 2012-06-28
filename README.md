isz-tool
========

isz-tool is a command line utility to manipulate ISZ files (.isz), including
.isz to .iso conversion

Overview
--------

ISZ files (.isz) are compressed ISO files (also called ISO Zipped). They can be
opened by software such as Alcohol 120%, Daemon Tools and UltraISO [1].

The main goal of this tool is to be able to convert ISZ files to ISO files.
At the time of writing isz-tool, I couldn't find any program able to handle
ISZ files under GNU/Linux.

ISZ files support the following features :
 - Decompression (using zlib or bzip2)
 - Split files support (.isz, .i01, .i02, ...)
 - CRC checksums of both compressed an uncompressed data

ISZ tool is a small command line tool currently able to :
 - Display informations about an ISZ file (uncompressed size, encryption
     type...)
 - Verify the file checksum
 - Extract the file to an .iso file

Currently not supported :
 - Encryption
 - Creation of an .isz file (before creating an .isz file, take into
   consideration that a .iso.bz2 is much more portable)

Usage
-----

./isz-tool.py info file.isz
  Print general information about file.isz

./isz-tool.py verify file.isz
  Verify the CRC of file.isz

./isz-tool.py verify --slow file.isz
  Attempt to decompress and verify the CRC of file.isz

./isz-tool.py isz2iso file.isz file.iso
  Convert file.isz to an ISO file

License
-------

ISZ-tool is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

ISZ-tool is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with ISZ-tool.  If not, see <http://www.gnu.org/licenses/>.

See gpl.txt for the license

Dependencies
------------

Python 3.2 is required to run isz-tool

Author
------

Olivier Serres - olivier.serres@gmail.com

Links
-----
[1] http://en.wikipedia.org/wiki/UltraISO#ISZ_format

