# Protocolo da revisão

A revisão seguiu as diretrizes de Kitchenham (2004) e de Kitchenham e Charters (2007).

## Objetivo e questões de pesquisa

Identificar estudos que abordem *code smells* (CS) e ferramentas de detecção de CS em aplicações web desenvolvidas em PHP, para elaborar uma lista dos CS relatados nesses estudos, um catálogo das ferramentas de detecção e as estratégias usadas para mitigar e prevenir esses problemas.

- **QP1:** Quais são os CS mais comuns em projetos PHP?
- **QP2:** Como os CS impactam a manutenibilidade e a evolução de aplicações PHP?
- **QP3:** Quais são as ferramentas mais utilizadas para a detecção de CS em PHP?
- **QP4:** Quais são as melhores práticas para mitigar e prevenir CS em projetos PHP?

## Busca

- **Bases:** IEEE Xplore, ACM Digital Library, ScienceDirect e SpringerLink.
- **Expressão:** `php AND (code smells OR semantic smells OR bad smells)`, aplicada da mesma forma nas quatro bases, sem aspas nos termos compostos.
- **Campos:** título, resumo e palavras-chave.
- **Período:** a busca foi feita no início da RSL, conduzida entre agosto e dezembro de 2024. A data exata de execução em cada base não foi registrada.
- **Resultados por base:** ACM 380, IEEE Xplore 363, ScienceDirect 171, SpringerLink 141 (total de 1.055).

## Critérios de seleção

- **CI:** estudos que contenham CS em PHP ou que relatem a manutenibilidade dos softwares com relação aos CS.
- **CE1:** é um livro ou coleção inteira de procedimentos.
- **CE2:** publicado antes de 2012.
- **CE3:** estudo incompleto, indisponível ou duplicado (versão igual ou atualizada; mantém-se a mais recente).
- **CE4:** não está escrito em português ou inglês.
- **CE5:** é resumo, resumo estendido, pôster ou RSL.
- **CE6:** não define *code smells*, *semantic smells* ou *bad smells*.

O CE5 foi revisto durante a elaboração do artigo. Na versão original do protocolo, ele excluía "artigos curtos", sem definir o termo. Para torná-lo verificável sem refazer a seleção, passou a excluir apenas resumos, resumos estendidos e pôsteres. Com a releitura dos textos completos, um estudo antes incluído (Raab, 2012) mostrou ser um pôster e foi excluído.

## Fases da seleção

| Fase | Atividade | Estudos avaliados | Excluídos |
|---|---|---|---|
| 1 | Aplicação dos critérios CE1 a CE5 | 1.055 | 351 |
| 2 | Leitura de títulos e palavras-chave (CE6) | 704 | 641 |
| 3 | Leitura de resumos e conclusões (CI) | 63 | 38 |
| 4 | Leitura completa | 25 | 2 |
| 5 | Casos de dúvida decididos pelo especialista | 23 | 0 |

Resultam **23 estudos incluídos**. As Fases 1 a 4 foram conduzidas pelo primeiro autor, e todas as decisões foram revisadas pelo segundo autor, que também atuou como especialista na Fase 5. As divergências foram resolvidas por consenso, sem cálculo de concordância. Das 2 exclusões da Fase 4, uma ocorreu na seleção original e a outra (Raab, 2012) na revisão do artigo.

## Avaliação de qualidade

Cada estudo incluído foi avaliado em quatro critérios, com nota 1 (atende), 0,5 (atende parcialmente) ou 0 (não atende); a nota do estudo é a soma, de 0 a 4:

- **QA1:** o objetivo do estudo está claramente definido?
- **QA2:** o método de pesquisa, incluindo a coleta e a análise dos dados, está descrito?
- **QA3:** o contexto do estudo (sistemas, linguagens e dados analisados) está descrito?
- **QA4:** os resultados respondem ao objetivo e são sustentados pelos dados apresentados?

A avaliação não foi usada como critério de exclusão, e sim para ponderar a confiança nas evidências. Ela foi feita depois da seleção e da extração, durante a revisão do artigo, com a leitura integral de cada estudo. As notas e as justificativas estão em `dados/avaliacao-qualidade.csv`.

## Extração

Para cada estudo, a planilha registra título, ano, autores, veículo, tipo de estudo, Qualis e nível de relevância para a RSL; trechos relevantes do texto (aba *Fixamento*); os CS relatados, com descrição e indicação de relação com o PHP; as ferramentas e as técnicas de detecção e de refatoração citadas; e as evidências associadas a cada questão de pesquisa.

## Construção do catálogo de CS

1. **Escopo:** entram os CS relatados nos estudos que têm PHP como foco (coluna `foco_php` de `dados/estudos.csv`).
2. **Sinônimos:** registros que descrevem o mesmo CS com nomes diferentes são unificados (por exemplo, *High Method Complexity* e *Cyclomatic Complexity*). O grupo de cada registro está na coluna `grupo_de_sinonimos` de `dados/code-smells-extraidos.csv`.
3. **Lado do cliente:** entram os CS de JavaScript e CSS embutidos no HTML gerado pelo servidor; ficam de fora as regras que se aplicam só a JavaScript isolado (como as do ESLint) e problemas exclusivos de JavaScript.
4. **Estudos com mais de um projeto:** só entram os CS medidos no projeto em PHP (caso de Soltanifar et al., 2016).
5. **Categorias:** PHP e aplicações web, tamanho, complexidade, herança e acoplamento, duplicação, código não utilizado, exceções, documentação e estilo. Violações de documentação e de estilo são mantidas, em categorias próprias.
6. **Especificidade:** cada CS recebe G (genérico), W (web) ou P (ligado ao PHP), conforme descrito no [README](README.md).

## Contagem de ferramentas (QP3)

A frequência de uso considera apenas ferramentas de mercado, contadas uma vez por estudo de PHP. Protótipos criados pelos próprios autores de um estudo (como o WebScent) e abordagens próprias sem ferramenta de detecção não entram na contagem.
