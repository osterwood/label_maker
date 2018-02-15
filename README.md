Label Maker
========

A simple ruby script for generating machine and human readable labels.

Installation
------------

    bundle install

This will install the required gems, [prawn][prawn], [barby][barby], and [combine_pdf][combine_pdf], .

Usage and Ouput
---------------

    ./label add 29b1e28c2b96 LED0603 Red AP1608SRCPRV
    ./label add 42096fa6ad42 LED0603 Yellow LTST-C190YKT
    ./label add 1656d67b0908 LED0603 Green LTST-C190KGKT

Running these commands will generate a PDF with 3 pages (1 per label), which looks like this.  The first "word" after `add` becomes the barcode, while all other text is printed on the line below.

![Sample Barcode Labels](img/example.png?raw=true "Sample Barcode Labels")

Once you print the labels, you can delete the PDF with:

    ./label clear

I'm using this script generate labels for [SMT part binders][book] like this:

![SMT Book](img/book.jpg?raw=true "SMT Book")

Currently, I'm printing labels with a Brother PT-D600 (this script allows me to avoid their horrible software), and using [Adafruit's barcode scanner][scanner].  

The Brother printer wastes about 1" of label every time you print, so it's best to queue up a whole bunch of labels into a many page PDF (instead of printing each label one at a time).

Printing
---------------

On Mac OS, you'll have to create a custom page size that is the same as your label size (here 3/8" x 2.5"). Orientation has to be set to landscape, and I also select "High resolution".

![Mac OS Print Settings](img/settings.png?raw=true "Mac OS Print Settings")

On Windows and Linux you'll likely have to do something similar to directly print these PDFs to the Brother label printer.


[combine_pdf]:https://github.com/boazsegev/combine_pdf
[prawn]:https://github.com/prawnpdf/prawn
[barby]:https://github.com/toretore/barby
[book]:https://www.adafruit.com/product/520
[scanner]:https://www.adafruit.com/product/1203