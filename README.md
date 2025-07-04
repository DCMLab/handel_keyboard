![Version](https://img.shields.io/github/v/release/DCMLab/handel_keyboard?display_name=tag)
[![DOI](https://zenodo.org/badge/473145734.svg)](https://doi.org/10.5281/zenodo.14996996)
![GitHub repo size](https://img.shields.io/github/repo-size/DCMLab/handel_keyboard)
![License](https://img.shields.io/badge/license-CC%20BY--NC--SA%204.0-9cf)


This is a README file for a data repository originating from the [DCML corpus initiative](https://github.com/DCMLab/dcml_corpora)
and serves as welcome page for both 

* the GitHub repo [https://github.com/DCMLab/handel_keyboard](https://github.com/DCMLab/handel_keyboard) and the corresponding
* documentation page [https://dcmlab.github.io/handel_keyboard](https://dcmlab.github.io/handel_keyboard)

For information on how to obtain and use the dataset, please refer to [this documentation page](https://dcmlab.github.io/handel_keyboard/introduction).

When you use (parts of) this dataset in your work, please read and cite the accompanying data report:

_Hentschel, J., Rammos, Y., Neuwirth, M., & Rohrmeier, M. (2025). A corpus and a modular infrastructure for the 
empirical study of (an)notated music. Scientific Data, 12(1), 685. https://doi.org/10.1038/s41597-025-04976-z_

# Georg Friedrich Händel – Grobschmied Variations (The Harmonious Blacksmith), HWV 430 (A corpus of annotated scores)


This corpus of annotated [MuseScore](https://musescore.org) files has been created within
the [DCML corpus initiative](https://github.com/DCMLab/dcml_corpora) and employs
the [DCML harmony annotation standard](https://github.com/DCMLab/standards). It represents the 
_Air and Variations_ movement from Händel's Suite no. 5 in E Major, HWV 430, published in 1720 and
popularly called _The Harmonious Blacksmith_. The title (translated into German as _Grobschmied_) 
refers to the spurious 19th-century rumour that the repeated high B in the Air was inspired by the 
sound of a blacksmith's anvil. In actuality the melody was likely based upon one from Händel's 1704
opera _Almira_. Händel's intricate soprano-bass counterpoint results in florid harmonic elaborations
whose elaboration throughout the five Variations our annotations reflect.

## Getting the data

* download repository as a [ZIP file](https://github.com/DCMLab/handel_keyboard/archive/main.zip)
* download a [Frictionless Datapackage](https://specs.frictionlessdata.io/data-package/) that includes concatenations
  of the TSV files in the four folders (`measures`, `notes`, `chords`, and `harmonies`) and a JSON descriptor:
  * [handel_keyboard.zip](https://github.com/DCMLab/handel_keyboard/releases/latest/download/handel_keyboard.zip)
  * [handel_keyboard.datapackage.json](https://github.com/DCMLab/handel_keyboard/releases/latest/download/handel_keyboard.datapackage.json)
* clone the repo: `git clone https://github.com/DCMLab/handel_keyboard.git` 


## Data Formats

Each piece in this corpus is represented by five files with identical name prefixes, each in its own folder. 
For example, the first section, *Aria* has the following files:

* `MS3/hwv430d_Grobschmied_Aria.mscx`: Uncompressed MuseScore 3.6.2 file including the music and annotation labels.
* `notes/hwv430d_Grobschmied_Aria.notes.tsv`: A table of all note heads contained in the score and their relevant features (not each of them represents an onset, some are tied together)
* `measures/hwv430d_Grobschmied_Aria.measures.tsv`: A table with relevant information about the measures in the score.
* `chords/hwv430d_Grobschmied_Aria.chords.tsv`: A table containing layer-wise unique onset positions with the musical markup (such as dynamics, articulation, lyrics, figured bass, etc.).
* `harmonies/hwv430d_Grobschmied_Aria.harmonies.tsv`: A table of the included harmony labels (including cadences and phrases) with their positions in the score.

Each TSV file comes with its own JSON descriptor that describes the meanings and datatypes of the columns ("fields") it contains,
follows the [Frictionless specification](https://specs.frictionlessdata.io/tabular-data-resource/),
and can be used to validate and correctly load the described file. 

### Opening Scores

After navigating to your local copy, you can open the scores in the folder `MS3` with the free and open source score
editor [MuseScore](https://musescore.org). Please note that the scores have been edited, annotated and tested with
[MuseScore 3.6.2](https://github.com/musescore/MuseScore/releases/tag/v3.6.2). 
MuseScore 4 has since been released which renders them correctly but cannot store them back in the same format.

### Opening TSV files in a spreadsheet

Tab-separated value (TSV) files are like Comma-separated value (CSV) files and can be opened with most modern text
editors. However, for correctly displaying the columns, you might want to use a spreadsheet or an addon for your
favourite text editor. When you use a spreadsheet such as Excel, it might annoy you by interpreting fractions as
dates. This can be circumvented by using `Data --> From Text/CSV` or the free alternative
[LibreOffice Calc](https://www.libreoffice.org/download/download/). Other than that, TSV data can be loaded with
every modern programming language.

### Loading TSV files in Python

Since the TSV files contain null values, lists, fractions, and numbers that are to be treated as strings, you may want
to use this code to load any TSV files related to this repository (provided you're doing it in Python). After a quick
`pip install -U ms3` (requires Python 3.10 or later) you'll be able to load any TSV like this:

```python
import ms3

labels = ms3.load_tsv("harmonies/hwv430d_Grobschmied_Aria.harmonies.tsv")
notes = ms3.load_tsv("notes/hwv430d_Grobschmied_Aria.notes.tsv")
```


## Version history

See the [GitHub releases](https://github.com/DCMLab/handel_keyboard/releases).

## Questions, Suggestions, Corrections, Bug Reports

Please [create an issue](https://github.com/DCMLab/handel_keyboard/issues) and/or feel free to fork and submit pull requests.

## Cite as

> Hentschel, J., Rammos, Y., Neuwirth, M., & Rohrmeier, M. (2025). A corpus and a modular infrastructure for the empirical study of (an)notated music. Scientific Data, 12(1), 685. https://doi.org/10.1038/s41597-025-04976-z

## License

Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License ([CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)).

![cc-by-nc-sa-image](https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png)


## Overview
|       file_name        |measures|labels|standard|                annotators                 |reviewers|
|------------------------|-------:|-----:|--------|-------------------------------------------|---------|
|hwv430d_Grobschmied_Aria|       9|    51|2.3.0   |Adrian Nagel (2.1.0), Davor Krkljus (2.3.0)|DK       |
|hwv430d_Grobschmied_Var1|       8|    56|2.3.0   |Adrian Nagel (2.1.0), Davor Krkljus (2.3.0)|DK       |
|hwv430d_Grobschmied_Var2|       8|    58|2.3.0   |Adrian Nagel (2.1.0), Davor Krkljus (2.3.0)|DK       |
|hwv430d_Grobschmied_Var3|       8|    56|2.3.0   |Adrian Nagel (2.1.0), Davor Krkljus (2.3.0)|DK       |
|hwv430d_Grobschmied_Var4|       8|    68|2.3.0   |Adrian Nagel (2.1.0), Davor Krkljus (2.3.0)|DK       |
|hwv430d_Grobschmied_Var5|      12|    61|2.3.0   |Adrian Nagel (2.1.0), Davor Krkljus (2.3.0)|DK       |


*Overview table automatically updated using [ms3](https://ms3.readthedocs.io/).*
