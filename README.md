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

Dependencies
------------

Python 3.2 is required to run isz-tool

Author
------

Olivier Serres - olivier.serres@gmail.com

Links
-----
[1] http://en.wikipedia.org/wiki/UltraISO#ISZ_format

