# Osmanli Yer Adlari

## 1. PDF to 3-column plain text spreadsheet

I copied the text of a pdf of Tahir Sezen's 1996 [Osmanlı Yer Adları](http://www.os-ar.com/osmanli_yer_isimleri.pdf) and pasted it into a word processor document, then used find and replace with regular expressions to turn it into tab-delineated lines, as follows:

1. replace $ with # (to remove all line breaks)
2. delete ##[0-9]* (to remove page numbers)
3. replace [[:::CharHeight=11::]] with \n& (to create a line break between each "new alphabet" administrative unit name, which are all given in 11pt font).
4. replace [[:::CharHeight=12::]] with \t&\t (to create tabs before and after every "old alphabet" administrative unit name, which are given in 12 point foint).

Note: It took me a while to figure out this method; couldn't seem to parse it by all caps and the alphabet switch. Luckily I realized that the font sizes differed. For some reason these find and replace operations took _forever_ in Libreoffice. When I broke the document into 8,000 word pieces, it went a lot faster.

I pasted the results into a spreadsheet and cleaned up a few errors manually. There were about 6400 records, in three columns: New alphabet name, old alphabet name, and a single field containing title and district containing it (Unvan ve Bağlı Olduğu Nahiye, Kaza, Sancak, Eyâlet veya Vilâyet).

## 2. Cleaning data in OpenRefine

The initial task was to produce a single line for each administrative unit, with the title/district pairs broken out. Almost half of the units have only one pair. Kozan has 14 (!) pairs. It took a bit more than a day to do this.

May 15: The current spreadsheet has many dozens of columns. I have standardized the containing district language (which contained a lot of errors--some remain no doubt). I have given set each nesting unit in its own column. "Bagli 1" is the largest district containing the place in question (typically a province), and Bagli 2 etc are subunits. I have also broken out dates into their own columns, and standardized the titles (unvanlar), which will form part of the ontology of the gazetteer. Also, I have amalgamated "unvan" notes and "bagli" notes into a single column.

# Next:

- I will combine rows which refer to the same place (many places are listed twice, under different names).
- I will give each administrative unit a number
- I will substitute the appropriate number for each "containing district" (bağlı olduğu...) field
- I will produce an RDF skeleton and export the data, conforming to the Pelagios [Gazetteer Interchange Format](https://github.com/pelagios/pelagios-cookbook/wiki/Pelagios-Gazetteer-Interconnection-Format)
- I will wrangle this onto the [ottgaz.org] server, using [OntoWiki](http://r.duckduckgo.com/l/?kh=-1&uddg=http%3A%2F%2Faksw.org%2FProjects%2FOntoWiki) at least initially

