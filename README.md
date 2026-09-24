# Pacote de replicação: Uma Revisão Sistemática da Literatura sobre Code Smells em Aplicações Web Baseadas em PHP

Charles de Azevedo Júnior e Wilkerson L. Andrade, Universidade Federal de Campina Grande (UFCG).

Este pacote reúne os dados da revisão sistemática da literatura (RSL) descrita no artigo: os estudos selecionados, os *code smells* (CS) extraídos de cada um, o catálogo final de CS, a avaliação de qualidade dos estudos e a planilha de extração original. O protocolo completo está em [PROTOCOLO.md](PROTOCOLO.md).

*English summary: replication package for a systematic literature review on code smells in PHP web applications. It contains the selected studies, every code smell extracted from them with the grouping decisions, the final catalog, the quality assessment of each study and the original data-extraction spreadsheet. All files are UTF-8 CSV; texts are in Brazilian Portuguese.*

## Conteúdo

| Arquivo | O que contém |
|---|---|
| [PROTOCOLO.md](PROTOCOLO.md) | Questões de pesquisa, busca, critérios de seleção, fases, avaliação de qualidade, extração e regras de construção do catálogo. |
| `dados/estudos.csv` | Os estudos incluídos (S01–S23) e o excluído durante a revisão do artigo, com o motivo; dados bibliográficos e DOI, tipo de estudo, se o estudo tem PHP como foco e as ferramentas de detecção usadas. O estudo excluído na Fase 4 da seleção original está apenas em `extracao-original/estudos.csv`. |
| `dados/avaliacao-qualidade.csv` | Notas dos critérios QA1 a QA4 de cada estudo incluído, nota total (0 a 4) e a justificativa, que aponta as seções e tabelas do estudo e, quando cabe, a nota alternativa considerada. |
| `dados/code-smells-extraidos.csv` | Cada registro de CS extraído dos estudos, com o grupo de sinônimos, a categoria, se entrou no catálogo, com que nome, a especificidade e a decisão tomada (por exemplo, "fora do catálogo: estudo não é de PHP"). |
| `dados/catalogo-cs.csv` | O catálogo final: cada CS, sua categoria, especificidade, descrição e os estudos em que aparece. |
| `extracao-original/*.csv` | As abas da planilha de extração, exportadas sem alterações de conteúdo. |

As colunas `estudo_id` e `id` ligam os arquivos entre si; a coluna `chave` corresponde às chaves das referências no artigo.

## Especificidade dos CS

A coluna `especificidade` do catálogo indica a relação de cada CS com o PHP:

- **G** (genérico): existe em qualquer linguagem orientada a objetos.
- **W** (web): próprio de aplicações que geram HTML no servidor, qualquer que seja a linguagem.
- **P** (PHP): depende de funções ou de convenções do ecossistema PHP, como o PHPDoc e os padrões de codificação verificados pelo PHP_CodeSniffer.

O catálogo reúne os CS *relatados em estudos sobre PHP*, e não apenas CS exclusivos da linguagem.

## Diferenças em relação à planilha de extração original

A pasta `extracao-original/` reproduz a planilha como foi preenchida durante a RSL. A revisão do artigo, com a releitura dos textos completos, corrigiu alguns pontos. As correções estão em `dados/` e não na planilha:

- **Soltanifar et al. (2016)** analisaram dois projetos: um em Java, com o PMD, e outro em PHP e JavaScript, com o PHP_CodeSniffer e o JSHint. A planilha marca como PHP os 20 CS do estudo, mas só os do projeto PHP entram no catálogo; dois CS desse projeto que não constavam da planilha foram acrescentados a partir do artigo original.
- **Raab (2012)** é um pôster (trilha *Poster and Demos* do VL/HCC) e foi excluído pelo critério CE5. Ele aparece em `dados/estudos.csv` como excluído.
- **Nguyen et al. (2012)** passou a contar como estudo de PHP: analisa aplicações web PHP, embora a planilha marque seus CS como não específicos.
- **Bessghaier et al. (2020)** foi publicado em anais de conferência (LNCS 12409), e não em periódico.
- Na aba *Fixamento*, os dois trechos atribuídos a Saranya et al. (2023) descrevem, na verdade, o CodeSmellExplorer de Raab (2012).
- A coluna *CS Específico do PHP* da planilha significa, na prática, "relatado em estudo de PHP". Em `dados/code-smells-extraidos.csv` ela aparece como `marcado_como_php_na_extracao`, e a classificação usada no artigo está em `especificidade`.

Os links para os PDFs dos estudos foram retirados da planilha exportada, porque os artigos têm direitos autorais. Use os DOIs de `dados/estudos.csv`.

## Como citar

Cite o artigo: AZEVEDO JÚNIOR, C.; ANDRADE, W. L. *Uma Revisão Sistemática da Literatura sobre Code Smells em Aplicações Web Baseadas em PHP*. [referência completa a definir após a publicação]

## Licença

[a definir pelos autores; para dados, a licença CC BY 4.0 é a opção mais comum no Zenodo]
