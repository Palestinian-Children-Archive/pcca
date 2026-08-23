# Palestinian Children and Community Archive — Collection Data

The digital collection site for the [Palestinian Children and Community Archive](https://palestinian-children-archive.github.io/), publishing the dataset that documents Palestinian childhood during the British Mandate of Palestine.

**Live site:** <https://palestinian-children-archive.github.io/pcca/>

The two sites link to each other: the main archive links here from its menu, home page, and footer, and every page here links back via the "Main Archive" nav item.

## What's in it

`_data/pcca_processed.csv` holds 6,388 catalogue records — newspapers, government and court papers, correspondence, photographs, maps, and recorded interviews — drawn from nineteen holding institutions including the National Library of Israel, the British Library's Qatar Digital Library, the Knesset archive, Yale University, Columbia University, and the British National Archives.

Records are descriptive metadata with links out to the holding institution; the items themselves are not hosted here.

| | |
|---|---|
| Records | 6,388 |
| Dated range | 1830s – mid-20th century |
| Languages | 27 languages or combinations, chiefly Arabic, English, Hebrew |
| Resource types | text, image, map, video, interview |

## Built with

[CollectionBuilder-GH](https://github.com/CollectionBuilder/collectionbuilder-gh) — a Jekyll static site generated from a metadata CSV, served by GitHub Pages. Upstream is MIT licensed; see `LICENSE`.

GitHub Pages rebuilds the site automatically on every push to `main`.

## Working on it locally

```bash
bundle install
bundle exec jekyll serve
```

The build reads the whole metadata CSV, so a full build takes roughly three to four minutes.

### Configuration

| File | Controls |
|---|---|
| `_config.yml` | Site title, description, `baseurl`, which CSV is the metadata source |
| `_data/theme.yml` | Colours, fonts, navbar, home page and per-page options |
| `_data/config-nav.csv` | Navigation items |
| `_data/config-metadata.csv` | Fields shown on item pages |
| `_data/config-browse.csv` | Fields shown on browse cards |
| `_data/config-search.csv` | Fields indexed and displayed in search |
| `_data/config-table.csv` | Columns on the Data page |
| `_data/config-theme-colors.csv` | Bootstrap theme colours |
| `_sass/_custom.scss` | Site styling, as a token and mixin design system |

Field names in the `config-*.csv` files must match columns that exist in the metadata CSV. Fields that do not exist render as blank or `n/a`.

### A note on build cost

`_includes/index/featured-terms.html` counts terms with a `where_exp` scan per unique term, so its cost is O(unique × total). It is fine for `subject` (785 unique terms) but not for `lcsh` (2,901 unique across ~50,000 instances), which pushes the build past the ten-minute GitHub Pages timeout. The same applies to the subject cloud: `subjects-min` in `_data/theme.yml` trims the long tail of single-occurrence terms.

## Notes on the data

The Locations and Map pages are not enabled: the metadata has no location or latitude/longitude columns for them to draw on. Adding those columns and re-enabling the pages in `_data/config-nav.csv` is all that is needed.
