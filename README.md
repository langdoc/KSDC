# Kola Saami Documentation Corpus (KSDC)
Current version: Alpha (not released yet)

This repository contains corpus data collected and further annotated by the Kola Saami Documentation Project.

KSDC is divided into three sub-corpora:
- [KSDC](https://github.com/langdoc/sjd/), the present repository, containing openly available corpus data
- [KSDC-fair](https://github.com/langdoc/sjd-fair/), containing data that we share with authorised collaborators and corpus users under restricted conditions
- [KSDC-bound](https://github.com/langdoc/sjd-bound/), containing data that we don't share outside the project.


## Authors and credits
The originator of the dataset and main administrator of the project is [Michael Rießler](https://uefconnect.uef.fi/michael.riesler/). [Ilia Egorov](https://www.finnougristik.uni-muenchen.de/personen/wiss_ma/ilia-egorov/) and [Evan Hansen](https://www.researchgate.net/profile/Evan-Hansen-5) are additional authors and administrators.

If you use KSDC data, please provide the URL of this README file. [Rießler & Wilbur 2007](https://edoc.hu-berlin.de/handle/18452/16) describe the beginnings of the Kola Saami Documentation Project, which laid the foundation for this corpus. [Rießler 2024](https://aclanthology.org/2024.iwclul-1.18) and [Hansen 2025](https://aclanthology.org/2025.iwclul-1.7/) describe different stages in the development of KSDC. Please refer to one of these papers until KSDC is described more thoroughly in a dedicated publication.


## License, data sharing, and collaboration
The present repository includes corpus data licensed openly (under CC-BY). This is possible because the underlying textual data are not protected by copyright, e.g. public-domain data or data not meeting the threshold of originality (book imprints, title pages, etc.), or licensing was cleared with the copyright holders.

The other two sub-corpora are found in [sjd-fair](https://github.com/langdoc/sjd-fair/) and [sjd-bound](https://github.com/langdoc/sjd-bound/), which are private repositories and visible only to project collaborators and other users invited by us. Note that these data must not be re-published or shared in any way outside this project because copyright applies. These data can, however, be analysed and processed by project collaborators.

The [Sessions overview](meta/sessions.md) provides more detailed information.

If you are interested in collaboration or using these data, contact [Michael Rießler](mailto:michael.riessler@uef.fi). Collaborators and other users must acknowledge the terms of use by signing the [Code of Conduct](CoC.md).


## Corpus and file structure
Every KSDC sub-corpus is divided further in parts for "written" and "spoken" data and further structured in folders and subfolders. The lowest subfolder is the actual corpus session including the data file, which has the file extension .eaf (ELAN, see below). Sometimes, a session includes more data files, but they are not documented yet.

File naming conventions
- The first three letters of the file name indicate the language using its ISO 639-3 language code.
- The second section indicates the known or estimated date of origin. It always consists of eight digits in the format YYYYMMDD. Unknown months or days are represented by 00.
- The third section, following an underscore, points to an entry in [KSDC.bib](https://github.com/langdoc/sjd/meta/KSDC.bib), which contains bibliographical information on the original source of texts originating from printed publications.
- A fourth section, where applicable and separated by a hyphen, identifies subsets of the source, e.g. individual chapters or topics.


## Data format
The corpus is modelled in the XLM-based [ELAN Annotation Format](https://archive.mpi.nl/tla/elan).

The minimal tier set includes:
- `ref@<SPEAKER>` - project-internal ID for each single sentence/utterance
- `orth(orig)@<SPEAKER>` - if applicable: original text in original script
- `orth@<SPEAKER>` - text in normalized orthography
- `ft-<LID>(orig)@<SPEAKER>` - if applicable: original language text on which a translation is based
- `ft-<LID>@<SPEAKER>` - if applicable: free translation.

The placeholder `<LID>` refers to an ISO language code; `<SPEAKER>` refers to a code for the speaker or text originator, see below.

More tiers are sometimes included, but they are not documented yet.


## Metadata
Basic metadata can be extracted from:
- the ELAN file name, which indicates the date of origin of the text or recording and, where applicable, the printed source from which the text originates;
- person IDs included in the ELAN annotation, which may indicate the year of birth and gender of an anonymised text originator or speaker.

For instance, the file name `sjd19951220_bazanov1996a` indicates a text created on 20 December 1995 and published in Askold Bazhanov's 1996 book Виллькесь пуаз. In this file name, `bazanov1996a` is the ID of the relevant BibTeX entry, which can be retrieved from the file KSDC.bib in the present repository. The ID AAA1932f identifies the creator of the Kildin Saami text as a female person born in 1932 (in this case, Bazhanov's Kildin Saami translator). Likewise, PAP1821m identifies a male person born in 1821 whose texts are found in files such as `sjd18760800_bibleMATTHEW1878a`. Here, 18760800 indicates August 1876, while 00 indicates that the exact day is unknown.

The [Speakers overview](meta/sessions.md) provides a list of non-anonymised speakers in the corpus and links to their Wikidata-entries.


## Work in progress
The [Sessions overview](meta/sessions.md) provides more detailed information on the included data.

Metadata
- Create metadata files in CMDI format under each session.

Statistics
- Create a dynamic visualisation for an overview of the included data
	- word tokens
	- speakers
	- dates