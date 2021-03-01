# CAL

## A Linux-style calendar utility for Mike Riley's Elf/OS.

If your Elf system includes an RTC, typing `cal` on the command line
will show a calendar of the current month, with the current date
hilited. (The hiliting assumes a VT100/ANSI style terminal.)

```
   $ cal
    
    February               2021
    Sun Mon Tue Wed Thu Fri Sat
          1   2   3   4   5   6
      7   8   9  10  11  12  13
     14  15  16  17  18  19  20
     21  22  23  24  25  26  27
     <b>28</b>
   $ 
```

Even without an RTC, you can use cal to display a calendar of any month
between the year 1766 and 2499 by typing commands such as:

```
   cal February 2021
   cal feb 2021
   cal 2 21
```

The month name can be abbreviated to any unique month name prefix. `ja`
will get you January. `f` will retun February. `ju` won't work, but 
`jun` will return June and `jul` will return July.

Two digit year numbers between 01 and 99 are interpreted as 2001 to 
2099.

The source was assembled with a modified version of the A18 assembler.
(I like being able to use `dc` to define strings with the most
significant bit of the last character set.) The header files `bios.inc`
and `kernel.inc` are slightly modified versions of Mike Riley's files;
the `#ifdef...#endif` bits have been removed or unconditionally
included as appropriate, `#define`s changed to `equ`, and upper/lower
casing was made consistent.
