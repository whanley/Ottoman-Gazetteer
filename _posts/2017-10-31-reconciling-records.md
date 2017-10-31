---
title: "Reconciling place names"
layout: single
date: 2017-10-31
tags:
  - duplication
  - dating
  - GREL
---
Today I'm archiving (what I hope will be) the final non-RDF version of the Ottoman gazetteer. This version, [Ottgaz-data-8](https://github.com/whanley/Ottoman-Gazetteer/blob/master/data/archived-versions/ottgaz-data-8.tsv), includes the dating work described in my [last post](http://ottgaz.org/dating-periodo/), as well as wikidata, geonames, and periodo links.

It also contains a `Duplicate?` column, in which I mark 147 records that will be discarded in future versions of the gazetteer. Each of these records is an exact duplicate of another record in the dataset filed under a different lead placenames. The only difference is the order of placenames. Sezen required this redundancy in order to make his paper-based index useable, but this digital gazetteer does not.

I found a good shortcut to identify duplicates. I created a column based on the `placename_1` column using the GREL command `forEach(cross(cell,"Ottgaz_rdf","Placename_2@tr"),r,r.cells["Placename_2@tr"].value).join("|")`, which fetched values whenever it found a value in `placename_2` that matched `placename_1`. I then created temporary keys by concatenating several `Admin_unit` and `Belongs_to` columns. A text facet on these keys showed me matching pairs and sets, which often corresponded to duplicate entries, which shared the same attributes.

I would guess that 200-300 more duplicate records remain in the database. I have retained these duplicates because they differ in more than just the name order. Two entries that concern the same place might differ slightly in one of their dates. In other cases, the differences are larger. An RDF database can tolerate and isolate inconsistencies of this sort. I will work to reconcile these duplicates once the RDF database is up and running.

The next step is to finalize the RDF skeleton (but I won't manage to have it ready in time for Halloween).
