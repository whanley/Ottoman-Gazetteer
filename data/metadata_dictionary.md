This gazetteer is a transformation of tables in Tahir Sezen's *Osmanlı Yer Adları* (Ottoman Place Names), available [here](http://www.os-ar.com/osmanli_yer_isimleri.pdf) and in many other places.

It uses the following fields:

1. **Placename@tr** (Sezen: İdârî Birimin Yeni Harflerle Adı) The name of the administrative unit in the Roman alphabet. While many places have just one name given, others have two or more variants, each of which appears in its own field (named Placename@tr 2, 3, 4, or 5). The current name of the place is given in all caps. There is also a `Placename_notes` field, containing Sezen's comments. In many cases, this field should be amalgamated with the `admin_unit_#_notes` field.
2. **Placename@ott** (Sezen: Eski Harflerle Adı) The name of the administrative unit in the Arabic alphabet. Only one name is given here, corresponding to the entry in `placename@tr`.
3. **Wikidata_url** A link to the Wikidata page which corresponds (more or less) to the place in question. The lat/long coordinates and other data can be scraped from this link.
4. **Admin_unit_#** (Sezen: Unvan) This field describes the position that the place occupied in the Ottoman administative hierarchy. The lowest numbers (i.e. `Admin_unit_1`) indicate earlier designations, the higher numbers (up to `Admin_unit_14`) indicate later designations. A dictionary of these terms appears below. In many cases, a year (or approximate year, or century) is given (`admin_unit_#_year`), corresponding to the date at which the place began to occupy its function. `admin_unit_#_notes` contains any notes that Sezen gives associated with this particular place and position. 
5. **Belongs_to_#-#** (Sezen: Bagli Olduğu Nahiye, Kaza, Sancak, Eyâlet veya Vilâyet) This field lists the superior administrative unit(s) to which the place in question belongs. I have broken each of these out into its own field, and they appear in sequence from subsidiary to superior. So, for instance, `Belongs_to_1-1` contains `Belongs_to_1-2`.

### Unvan Dictionary
The administrative units, roughly in order of frequency, with certain weblinks embedded.

Turkish|Ottoman|English|notes
---|---|---|---
[Nahiye](https://tr.wikipedia.org/wiki/Bucak_%28idari_birim%29)|ناحيه|[Subdistrict](https://en.wikipedia.org/wiki/Nahiye_%28Ottoman%29)|Subsidiary to kaza
Kaza|قضا|[District](https://en.wikipedia.org/wiki/Kaza)|Subsidiary to sancak
[Sancak](https://tr.wikipedia.org/wiki/Sancak_%28y%C3%B6netim_b%C3%B6l%C3%BCm%C3%BC%29)|سنجق|[Subprovince](https://en.wikipedia.org/wiki/Sanjak)|Subsidiary to eyalet or vilayet
Köy|كوى|Village|used principally in the 20th century
Kasaba|قصبه|Town|used principally in the 20th century
Nahiye merkezi|ناحيه مركزى|Subdistrict seat|
Kaza merkezi|قضا مركزى|District seat|
Eyâlet|ايالت|[Province](https://en.wikipedia.org/wiki/Eyalet)|before 1867
Vilâyet|ولايت|[Province](https://en.wikipedia.org/wiki/Vilayet)|after 1867
Eyâlet merkezi|ايالت مركزى|Province seat|before 1867
Sancak merkezi|سنجق مركزى|Subprovince seat|
Vilâyet merkezi|ولايت مركزى|Provincial seat|after 1867
Şehir|شهر|City|here, typically outside of the Ottoman empire
Ada|آطه|Island|often also a sancak or kaza
Müdiriyet|مديريت|Department|of Egypt
Antik şehir||Ancient city|
Başkent||Capital city|
Kale|قلعه|Fortress|
Müstakil sancak||"Independent" subprovince|
Müdiriyet merkezi||Department seat|of Egypt
Başşehir||Capital city|
Bölge|بولكه|Region|
Semt|سمت|Quarter|i.e. of a city
Liman şehri||Port city|
Muhafızlık|||
Antik kasaba|||
Takımada|||
Ülke|||
Mahalle|||
Beylik merkezi|||
Geçit|||
Hanlık|||
Köy ve göl|||
Kaymakamlık|||
Kontluk|||
Krallık|||
Muhtar idare|||

###Usage notes

Generally speaking, id numbers 100-199 are for major provinces, 200-499 for other first order administrative units, 500-999 for cities, 1000-1999 for second order administrative units (sancaks).

Sezen's list contains a lot of material about foreign states and especially about the administrative hierarchy of the Turkish Republic. I have used the field `Ott_or_not` to tag these two entities. For the most part, I have done this by hand. I have excluded batches of sites that are listed as `merkez` in their first listing, however. This designation was particular to the Republic, as far as I can see. Under the Republican scheme, every province had a _merkez ilçe_ (subprovince) with the same name as the province, and the same practice was used for districts as well. So, for the most part, I've labeled such places as part of the Republic of Turkey (thus not part of the Ottoman hierarchy).