---
title: 1530 place name data dictionary
author: Will Hanley
---

This dataset is derived from two indexes: [Rumeli](http://www.devletarsivleri.gov.tr/assets/content/Yayinlar/elektronik-yayinlar/osmanli_yer_adlari_1.pdf) and [Anadolu](http://www.devletarsivleri.gov.tr/assets/content/Yayinlar/elektronik-yayinlar/osmanli_yer_adlari_2.pdf).

It contains the following fields:

- place_name: the head place name
- unit_type: there are approximately 400 of these, and the data requires more cleaning. I have removed most abbreviations.
- alt_place_name: up to 4 alternate place names. In some cases, these are the names given in "bakınız" (see also) entries, discussed below.
- Parent: these six fields are nesting series of parent administrative units. They do not align with unit type, though that alignment could be useful. Unit types remain abbreviated.
- Reference: a reference to one or more locations in the tahrir defters in the Prime Ministerial archives, giving page numbers within the defters.

## Bakınız
The dataset contains almost 6000 unique "bakınız" entries. I looked through a few dozen of these, and found that almost all of them represent alternate place names already entered under the main heading. I calculated that reconciling all off these references would be too costly an effort, so I removed them from the database. I've preserved this bakınız data in a separate file, loaded into the github repository.

