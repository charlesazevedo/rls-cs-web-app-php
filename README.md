# Replication package: A Systematic Literature Review of Code Smells in PHP-Based Web Applications

Charles de Azevedo Júnior and Wilkerson L. Andrade, Federal University of Campina Grande (UFCG), Brazil.

This package contains the data of the systematic literature review (SLR) described in the paper: the selected studies, the code smells extracted from each one, the final code smell catalog, the quality assessment of the studies, and the original data-extraction spreadsheet. The full protocol is in [PROTOCOL.md](PROTOCOL.md). All files are UTF-8 CSV.

## Contents

| File | What it contains |
|---|---|
| [PROTOCOL.md](PROTOCOL.md) | Research questions, search, selection criteria, phases, quality assessment, extraction, and the rules used to build the catalog. |
| `data/studies.csv` | The included studies (S01–S23) and the study excluded during the revision of the paper, with the reason; bibliographic data and DOI, publication type (the basis for EC5), study type, whether the study focuses on PHP, languages analyzed, detection tools actually used (read in the full texts), tools cited (as recorded in the spreadsheet), and the research questions (RQs) the study contributes to in the paper. The study excluded in Phase 4 of the original selection is only in `original-extraction/studies.csv`. |
| `data/quality-assessment.csv` | Scores of criteria QA1 to QA4 for each included study, total score (0 to 4), and the justification, which points to the sections and tables of the study and, where applicable, the alternative score considered. |
| `data/extracted-code-smells.csv` | Every code smell record extracted from the studies, with its synonym group, category, whether it entered the catalog and under which name, its specificity, and the decision taken (for example, "outside the catalog: not a PHP study"). |
| `data/catalog.csv` | The final catalog: each code smell, its category, specificity, description, and the studies in which it appears. |
| `original-extraction/*.csv` | The sheets of the data-extraction spreadsheet, exported without changes to their content (in Portuguese; see below). |

The columns `study_id` and `id` link the files; the column `key` matches the reference keys used in the paper.

## Code smell specificity

The `specificity` column of the catalog indicates how each code smell relates to PHP:

- **G** (generic): exists in any object-oriented language.
- **W** (web): specific to applications that generate HTML on the server, whatever the language.
- **P** (PHP): depends on functions or conventions of the PHP ecosystem, such as PHPDoc and the coding standards checked by PHP_CodeSniffer.

The catalog gathers the code smells *reported in studies on PHP*, not only code smells exclusive to the language.

## The original extraction spreadsheet

The data extraction was carried out in Portuguese. The folder `original-extraction/` reproduces the spreadsheet as it was filled in during the SLR, including its Portuguese column names and texts; the files in `data/` are the curated English version. Each file comes from one sheet:

| File | Sheet | Columns (Portuguese → English) |
|---|---|---|
| `studies.csv` | Estudos | Título (title), Ano (year), Nível de Importância (relevance level), Lido? (read?), Incluso? (included?), Autores (authors), Publicado em (published in), Tipo de Estudo (study type), Qualis (Brazilian CAPES venue rating) |
| `excerpts.csv` | Fixamento | Fixamento (excerpt quoted from the study), Artigo (paper), Comentário (extractor's comment) |
| `code-smells.csv` | Code Smells | Nome do Code Smell (code smell name), CS Específico do PHP (PHP-specific code smell), Descrição (description), Artigo citado (source paper), Texto relevante (relevant excerpt) |
| `tools.csv` | Ferramentas | Nome da ferramenta (tool name), Para PHP (for PHP), Descrição (description), Artigo citado (source paper), Texto relevante (relevant excerpt) |
| `techniques.csv` | Técnicas | Técnica (technique), Descrição (description), Artigo citado (source paper), Texto relevante (relevant excerpt) |
| `rq2.csv` | Q2 | Impáctos do Code Smell (impacts of the code smell), Artigo citado (source paper), Texto relevante (relevant excerpt) |

In `data/extracted-code-smells.csv`, the column `name_in_study` gives the name used by the study: where the spreadsheet recorded a name in Portuguese, it was replaced by the study's own name (for example, *Scattered Sources* for "Fontes dispersas", from Nguyen et al., 2012). The `row_in_original_spreadsheet` column points to the corresponding row of `original-extraction/code-smells.csv`.

## Differences from the original extraction spreadsheet

The revision of the paper, with the rereading of the full texts, corrected some points. The corrections are in `data/`, not in the spreadsheet:

- **Soltanifar et al. (2016)** analyzed two projects: one in Java, with PMD, and another in PHP and JavaScript, with PHP_CodeSniffer and JSHint. The spreadsheet marks all 20 code smells of the study as PHP, but only those of the PHP project enter the catalog; two code smells of that project that were missing from the spreadsheet were added from the original paper.
- **Raab (2012)** is a poster (*Poster and Demos* track of VL/HCC) and was excluded by criterion EC5. It appears in `data/studies.csv` as excluded.
- **Nguyen et al. (2012)** now counts as a PHP study: it analyzes PHP web applications, although the spreadsheet marks its code smells as not specific.
- **Bessghaier et al. (2020)** was published in conference proceedings (LNCS 12409), not in a journal.
- In the *Fixamento* sheet, the two excerpts attributed to Saranya et al. (2023) actually describe Raab's (2012) CodeSmellExplorer.
- The spreadsheet column *CS Específico do PHP* means, in practice, "reported in a PHP study". In `data/extracted-code-smells.csv` it appears as `marked_as_php_in_extraction`, and the classification used in the paper is in `specificity`.

The links to the PDFs of the studies were removed from the exported spreadsheet, because the papers are copyrighted. Use the DOIs in `data/studies.csv`.

## How to cite

Package available at <https://github.com/charlesazevedo/rls-cs-web-app-php>.

Cite the paper: AZEVEDO JÚNIOR, C.; ANDRADE, W. L. *A Systematic Literature Review of Code Smells in PHP-Based Web Applications*. [full reference to be added after publication]

## License

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/): you may copy, adapt, and redistribute the data, including for commercial purposes, as long as you credit the source. The excerpts quoted from the analyzed studies, in the folder `original-extraction/` (column "Fixamento" and the "Texto relevante" columns), belong to their authors and are not covered by the license. Details in [LICENSE](LICENSE).
