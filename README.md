# hihex
The hihex utility works like the 'hexdump' command with a special addition.  It allows you to view the character output of ASCII values that have the high bit set.

This is particularly useful for examining binary files from older computers, such as the Apple II, where they would commonly use the high bit versions of characters to display text in other modes such as inverse.  

Also great for diffs!


#Still don't get it

Here's a quick example.  Look at this file with hexdump... 

    $ hexdump -C binfile
    00000000  48 45 4c 4c 4f 20 57 4f  52 4c 44 21 21 21 21 21  |HELLO WORLD!!!!!|
    00000010  d3 c5 c3 d2 c5 d4 a0 cd  c5 d3 d3 c1 c7 c5 ba a9  |................|
    00000020

See how the second line is filled with periods?  LAME!!!

Now you can see the whole picture with hihex...

    $ hihex ~/binfile
    002000  48 45 4C 4C 4F 20 57 4F 52 4C 44 21 21 21 21 21  HELLO WORLD!!!!!
    002010  D3 C5 C3 D2 C5 D4 A0 CD C5 D3 D3 C1 C7 C5 BA A9  SECRET MESSAGE:)

