# SuttaNotation.db

This is a scrappy little table I’ve put together, largely based on the [tables](https://palistudies.blogspot.com/2020/02/sutta-number-to-pts-reference-converter.html) from the palistudies blog, with some manual corrections and additional columns, such as SuttaCentral bilara_data reference paths.

I’ve chosen to exclude suffixes like “sutta(ṃ),” “vaggo,” “pāḷi,” etc., from the names of relevant sections. In some cases (I'm looking at you, Vinaya) it isn’t obvious how to apply this or any convention, so I’m leaving that for later.

The table currently covers only the Nikāyas (with a subset of the KN) and the Vinaya, as these are what I’m chiefly interested in. PRs extending it to any other Pali-language texts would be very welcome.

## Schema

What follows is the schema of the database, which shows the tables and their columns.

```
CREATE TABLE IF NOT EXISTS "dn" (
"sutta_notation" TEXT,
  "titles" TEXT,
  "vagga" TEXT,
  "vagga_id" INTEGER,
  "sutta_id" INTEGER,
  "vagga_sutta_id" INTEGER,
  "pts_volume" INTEGER,
  "pts_page" INTEGER,
  "bilara_path" TEXT
);
CREATE TABLE IF NOT EXISTS "mn" (
"sutta_notation" TEXT,
  "titles" TEXT,
  "pannasa" TEXT,
  "pannasa_id" INTEGER,
  "vagga" TEXT,
  "vagga_id" INTEGER,
  "pannasa_vagga_id" INTEGER,
  "sutta_id" INTEGER,
  "pannasa_sutta_id" INTEGER,
  "vagga_sutta_id" INTEGER,
  "pts_volume" INTEGER,
  "pts_page" INTEGER,
  "bilara_path" TEXT
);
CREATE TABLE IF NOT EXISTS "sn" (
"section_notation" TEXT,
  "section_notation_alt" TEXT,
  "titles" TEXT,
  "mah_" TEXT,
  "mahavagga_id" INTEGER,
  "samyutta" TEXT,
  "samyutta_id" INTEGER,
  "culavagga" TEXT,
  "culavagga_id" INTEGER,
  "samyutta_culavagga_id" INTEGER,
  "sutta_id" REAL,
  "mahavagga_sutta_id" REAL,
  "samyutta_sutta_id" REAL,
  "culavagga_sutta_id" REAL,
  "pts_volume" INTEGER,
  "pts_page" INTEGER,
  "pts_page_alt" REAL,
  "bilara_path" TEXT
);
CREATE TABLE IF NOT EXISTS "an" (
"section_notation" TEXT,
  "titles" TEXT,
  "nipata" TEXT,
  "nipata_id" INTEGER,
  "pannasaka" TEXT,
  "pannasaka_id" REAL,
  "vagga" TEXT,
  "vagga_id" INTEGER,
  "nipata_vagga_id" INTEGER,
  "pannasaka_vagga_id" REAL,
  "sutta_id" INTEGER,
  "nipata_sutta_id" INTEGER,
  "pannasaka_sutta_id" INTEGER,
  "vagga_sutta_id" INTEGER,
  "pts_volume" INTEGER,
  "pts_page" INTEGER,
  "bilara_path" TEXT
);
CREATE TABLE IF NOT EXISTS "dhp" (
"section_notation" TEXT,
  "verse_notation" TEXT,
  "kn_section_notation" TEXT,
  "kn_verse_notation" TEXT,
  "vagga_notation" TEXT,
  "vagga" TEXT,
  "vagga_id" INTEGER,
  "verse_id" INTEGER,
  "vagga_verse_id" INTEGER,
  "pts_page" INTEGER,
  "bilara_path" TEXT
);
CREATE TABLE IF NOT EXISTS "ud" (
"section_notation" TEXT,
  "sutta_notation" TEXT,
  "kn_section_notation" TEXT,
  "kn_sutta_notation" TEXT,
  "titles" TEXT,
  "vagga" TEXT,
  "vagga_id" INTEGER,
  "sutta_id" INTEGER,
  "vagga_sutta_id" INTEGER,
  "pts_page" INTEGER,
  "bilara_path" TEXT
);
CREATE TABLE IF NOT EXISTS "iti" (
"section_notation" TEXT,
  "sutta_notation" TEXT,
  "kn_section_notation" TEXT,
  "kn_sutta_notation" TEXT,
  "titles" TEXT,
  "nipata" TEXT,
  "nipata_id" INTEGER,
  "vagga" TEXT,
  "vagga_id" INTEGER,
  "sutta_id" INTEGER,
  "vagga_sutta_id" INTEGER,
  "pts_page" INTEGER,
  "bilara_path" TEXT
);
CREATE TABLE IF NOT EXISTS "snp" (
"section_notation" TEXT,
  "sutta_notation" TEXT,
  "kn_section_notation" TEXT,
  "kn_sutta_notation" TEXT,
  "titles" TEXT,
  "vagga" TEXT,
  "vagga_id" INTEGER,
  "sutta_id" INTEGER,
  "vagga_sutta_id" INTEGER,
  "pts_page" INTEGER,
  "bilara_path" TEXT
);
CREATE TABLE IF NOT EXISTS "thag" (
"section_notation" TEXT,
  "sutta_notation" TEXT,
  "kn_section_notation" TEXT,
  "kn_sutta_notation" TEXT,
  "titles" TEXT,
  "nipata" TEXT,
  "nipata_id" INTEGER,
  "vagga" TEXT,
  "vagga_id" REAL,
  "sutta_id" INTEGER,
  "nipata_sutta_id" INTEGER,
  "verse_ids" TEXT,
  "pts_page" INTEGER,
  "bilara_path" TEXT
);
CREATE TABLE IF NOT EXISTS "thig" (
"section_notation" TEXT,
  "sutta_notation" TEXT,
  "kn_section_notation" TEXT,
  "kn_sutta_notation" TEXT,
  "titles" TEXT,
  "nipata" TEXT,
  "nipata_id" INTEGER,
  "sutta_id" INTEGER,
  "nipata_sutta_id" INTEGER,
  "verse_ids" TEXT,
  "pts_page" INTEGER,
  "bilara_path" TEXT
);
```