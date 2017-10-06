---
title: "Transforming the Osmanlı Yer Adları"
author: Will Hanley
date: 2017-10-06
layout: post
categories: ocr openrefine sezen archived
---

I began to generate the base data for this gazetteer using a PDF that I found online.

## 0.1
The first step was to get a workable table out of the OCRed version of the PDF. Initially this was challenging, because the multiple lines of the tables were not conforming to the column arrangement when imported into a spreadsheet. I found a solution by using changes in font size to split the table into three columns, one for the modern Turkish placename, one for the Ottoman placename, and one for the notes that located the place in the administrative hierarchy.

## 0.2
I then used OpenRefine to format and clean the data. This was a laborious process, and went through several iterations. I've archived all of these iterations on Github, though I expect that they will be of little interest or use to anyone. The first iteration contains all of the bagli hierarchical names in a single column, which is to say that it does not have a single row for each placename. It contains XX rows. I used this iteration to standardize placenames and dates.

## 0.3
The second iteration contains only one line for every place, and begins to develop the hierarchical structure. It contains 80 columns

## 0.4
The third iteration converts the headings into English, continuing the cleaning and standardization.

## 0.5
The fourth iteration begins to implement some internal references, by adding a field for ID numbers, and beginning to reference IDs in the hierarchy. It also adds a Place_type field, differentiating between cities and regions, and an Ott_or_not field, a boolean category to isolate those records which situate the place in a hierarchy entirely outside of modern Turkey.

## 0.6
The current iteration, which I'm working on now, should be the last produced in OpenRefine. It integrates wikidata and geonames references and contains an RDF skeleton.
