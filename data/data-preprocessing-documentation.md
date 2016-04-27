# PDF to 3-column plain text spreadsheet

I copied the text of Tahir Sezen's 1996 [Osmanli Yer Adalari](http://www.os-ar.com/osmanli_yer_isimleri.pdf) pdf.

I pasted it into a word processor document, then used find and replace with regular expressions to turn it into tab-delineated lines, as follows:
1. replace $ with # (to remove all line breaks)
2. delete ##[0-9]* (to remove page numbers)
3. replace [[:::CharHeight=11::]] with \n& (to create a line break between each "new alphabet" place name, which are all given in 11pt font).
4. replace [[:::CharHeight=12::]] with \t&\t (to create tabs before and after every "old alphabet" place name, which are given in 12 point foint).

Note: for some reason these find and replace operations took _forever_ in Libreoffice. When I broke the document into 8,000 word pieces, it went a lot faster.

I pasted the results into a spreadsheet and cleaned up a few errors manually. There were about 6400 records, in three columns: New alphabet name, old alphabet name, and title and locations (all in a single field).

# Cleaning data in OpenRefine

