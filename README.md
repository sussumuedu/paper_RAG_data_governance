# Artigo 1574318 – Inteligência artificial generativa na governança de dados em saúde: estudo comparativo com recuperação documental
XXI Congresso Brasileiro de Informática em Saúde – CBIS’26
23 a 25 de setembro de 2026 - Brasília/DF - Brasil

Artefatos de pesquisa utilizados na avaliação do impacto da Retrieval-Augmented Generation na qualidade de respostas sobre governança de dados em saúde.

# Avaliação de Retrieval-Augmented Generation para Governança de Dados em Saúde

Este repositório contém os artefatos de uma pesquisa comparativa sobre o uso de Retrieval-Augmented Generation (RAG) no domínio da governança de dados em saúde.

O estudo investiga se uma arquitetura baseada em RAG melhora a qualidade percebida das respostas quando comparada à geração sem recuperação documental. A avaliação considera um domínio especializado, no qual as respostas precisam ser corretas, completas, aderentes às fontes, úteis e claras.

## Contexto do estudo

Large Language Models (LLMs) apresentam potencial para apoiar a recuperação, síntese e interpretação de informações em saúde. Entretanto, seu uso em contextos especializados e regulatórios envolve riscos como alucinação, contextualização incompleta e desalinhamento com documentos específicos do domínio.

A abordagem RAG busca reduzir essas limitações ao combinar a geração de respostas por LLMs com a recuperação semântica de informações em uma coleção documental externa. Neste estudo, avaliamos se essa abordagem agrega valor prático à geração de respostas sobre governança de dados em saúde.

## Objetivo

Avaliar se respostas geradas com RAG apresentam maior qualidade percebida do que respostas geradas sem suporte de recuperação documental no contexto da governança de dados em saúde.

## Desenho do estudo

Foi elaborado um conjunto de 30 perguntas relacionadas à governança de dados em saúde. Para cada pergunta, foram geradas duas respostas:

- uma resposta com Retrieval-Augmented Generation;
- uma resposta sem recuperação documental.

O processo resultou em 60 respostas organizadas em 30 pares comparáveis.

As respostas foram avaliadas em um procedimento duplo-cego. Os avaliadores não sabiam se cada resposta havia sido gerada com ou sem RAG. Dentro de cada par, as respostas foram randomizadas e apresentadas como alternativas A e B.

## Avaliação

Participaram da avaliação:

- dois especialistas humanos com experiência em governança de dados em saúde;
- um avaliador automatizado baseado no paradigma LLM-as-a-judge, utilizando o Claude Opus 4.6.

Cada resposta foi avaliada em cinco dimensões ordinais, utilizando escala Likert de 1 a 5:

- Acurácia;
- Completude;
- Aderência;
- Utilidade;
- Clareza.

Para cada par de respostas, os avaliadores também indicaram uma preferência global entre:

- Com RAG;
- Sem RAG;
- Empate.

Ao todo, foram produzidos:

- 900 julgamentos ordinais;
- 90 julgamentos de preferência global.

## Análise estatística

As avaliações ordinais foram analisadas por meio de cumulative link mixed models (CLMMs), com um modelo ajustado para cada dimensão. Os modelos estimaram a associação entre a condição experimental e a probabilidade de obtenção de avaliações mais altas na escala Likert.

A preferência global foi analisada por meio de regressão logística multinomial, tendo o avaliador como preditor. Como análise de sensibilidade, foi ajustado um modelo adicional com intercepto aleatório por pergunta.

A concordância entre os avaliadores foi examinada utilizando:

- kappa de Cohen ponderado com pesos quadráticos para as dimensões Likert;
- alfa de Krippendorff ordinal para os três avaliadores em conjunto;
- kappa nominal para a preferência global;
- alfa de Krippendorff nominal para a preferência global conjunta.

A interpretação considerou a direção e a magnitude dos efeitos estimados, seus intervalos de confiança e a natureza exploratória do estudo.

## Arquivos do repositório

### `avaliacao_comparativa_all_judges`

Base consolidada contendo as perguntas, as respostas com e sem RAG e as avaliações realizadas pelos dois especialistas humanos e pelo LLM judge.

### `comparativo_experts_llms_judge`

Notebook principal das análises estatísticas comparativas, incluindo os modelos ordinais, a análise de preferência global e as análises de sensibilidade.

### `concordancia_avaliadores_likert`

Tabela com as medidas de concordância das cinco dimensões Likert, incluindo kappas ponderados pareados, alfa de Krippendorff ordinal e respectivos intervalos de confiança.

### `concordancia_avaliadores_pref`

Tabela com as medidas de concordância da preferência global, incluindo kappas nominais pareados, alfa de Krippendorff nominal e respectivos intervalos de confiança.

### `Experts_is_a_judge_human1`

Arquivo utilizado na avaliação das respostas pelo primeiro especialista humano.

### `Experts_is_a_judge_human2`

Arquivo utilizado na avaliação das respostas pelo segundo especialista humano.

### `LLM_is_a_judge_20260408`

Notebook utilizado para executar a avaliação automatizada com o Claude Opus 4.6, incluindo os prompts, parâmetros e procedimentos de avaliação.

### `questions_llms`

Arquivo contendo as perguntas utilizadas no estudo e os dados associados à geração das respostas com e sem RAG.


### `material_suplementar_diagnosticos_modelos`

Arquivo contendo todos os materiais suplementares, referenciados no manuscrito.

### `README`

Documento com a descrição do estudo, da organização do repositório e dos principais artefatos disponibilizados.