---
title: About
layout: about
permalink: /about.html
# include CollectionBuilder info at bottom
credits: true
---

{% include feature/jumbotron.html objectid="/assets/img/archive-hero.png" %}

{% include feature/nav-menu.html sections="About the Collection;Using the Collection;Sources and Rights" %}

## About the Collection

This is the dataset behind the [Palestinian Children and Community Archive](https://palestinian-children-archive.github.io/), a project documenting Palestinian childhood during the British Mandate of Palestine.

It gathers **{{ site.data[site.metadata] | size }} records** describing newspapers, government and court papers, correspondence, photographs, maps, and recorded interviews held by archives and libraries around the world. Dated material in the collection runs from the 1830s to the mid-twentieth century, concentrated on the Mandate period.

Each record is a catalogue entry rather than a copy of the item itself. Records carry a title, date, subject terms, Library of Congress Subject Headings, resource type, language, and the holding institution, and most link out to that institution's own catalogue where the material can be consulted.

## Using the Collection

- **[Browse]({{ '/browse.html' | relative_url }})** — page through every record, filter by keyword, and sort by title or date.
- **[Subjects]({{ '/subjects.html' | relative_url }})** — a term cloud sized by how often each subject appears; select a term to see its records.
- **[Timeline]({{ '/timeline.html' | relative_url }})** — records arranged by date.
- **[Data]({{ '/data.html' | relative_url }})** — the full metadata as a sortable table, downloadable as CSV, JSON, or Excel.

The search box in the navigation bar searches titles, dates, subjects, summaries, and subject headings.

## Sources and Rights

Records are drawn from nineteen recorded origins, the largest being the National Library of Israel newspaper collections, the British Library's Qatar Digital Library, the Knesset archive, Yale University, Columbia University, Open Jerusalem, and the British National Archives. Material is catalogued in twenty-seven languages or language combinations, most often Arabic, English, and Hebrew.

Rights in the described material remain with the holding institutions. This site publishes descriptive metadata and links; it does not host the items themselves. Please consult the linked institution for reproduction and reuse terms.

The metadata is released for reuse — see the [Data]({{ '/data.html' | relative_url }}) page for machine-readable exports.
