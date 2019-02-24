pypacc
======

A Python utility to read the contents of a PAC/FPC Closed Caption (subtitle) file.


Usage
=====

Additions by Vikram Bahl (23/02/2019):

Use the following method to generate the SRT subtitle file:

1) Enter the following line in bash (ensure directory paths are correct):
  
  ```
  python readPac.py --outformat=SRT FNAME.PAC --encoding=utf-8 >> FNAME.srt

  ```

  where FNAME is the name of the PAC file. It is important that the name of
  the output srt file is the same as  the name of the video file.

2) Make sure ```cat FNAME.srt``` displays the subtitles in the right format

-------------------------- xxxx -------------------------- 

Takes a PAC/FPC file as an argument with specific encoding as an optional argument.

```
Usage: python readPac.py [options] pac_file

Options:
    -h, --help      show this help message and exit
    -e CODEPAGE, --encoding=CODEPAGE
                    encoding: latin, thai, chinese, cyrillic, utf-8
    -t, --text      write out text only
    -f, --outformat     output format (SRT)
    -o, --outfile      file to save output to
```

If no encoding is provided, the program will attempt to determine the proper
character set.


Author(s)
=========

- Ethan Hart
    - ported PAC decoding logic from C# to Python
    - wrote auto-dection/verification steps, rest of code

- Nikolaj Olsson
    - wrote the PAC decoding logic


Information
===========

This script will read the contents of a PAC/FPC subtitle file and can output
timing information and text. It does not retain alignment, justification, and
other formatting information. As of now, this converter works with PAC files
encoded using Latin (iso-8859-1), Chinese (big5), Cyrillic (iso-8859-5), Thai
(cp874), and UTF-8 character sets. Note: UTF-8 is likely only valid for FPC
files (a variation of the PAC format which uses Unicode as a standard).

The PAC format was developed by Screen Electronics.
This parser is based on code written by Nikolaj Olsson under the GNU General
Public License. I have simply ported the PAC file parsing components from C#
to Python. Please check out and support his project over at
http://www.nikse.dk/SubtitleEdit/

This work is sponsered by AppTek http://www.apptek.com
