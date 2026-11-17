# Mapeamento e Padronização de Processos

- **Empresa:** Itaú Unibanco
- **Área:** Consignado
- **Período:** 2022 a 2024

## Contexto

A área de consignado executava dezenas de rotinas operacionais que existiam havia anos e
não tinham documentação formal. O conhecimento estava nas pessoas, não em um repositório
consultável. Quem precisava executar uma etapa perguntava para quem já fazia, e cada
pessoa explicava de um jeito diferente.

## Problema

Três consequências apareceram juntas.

A primeira foi dependência de conhecimento individual. Quando alguém saía de férias ou era
transferido, a rotina parava ou era executada de memória por outra pessoa.

A segunda foi risco de conformidade. Sem procedimento escrito, não havia como provar para
Controles Internos e auditoria que a etapa era executada sempre do mesmo jeito.

A terceira apareceu depois, e foi a mais útil: sem processo desenhado, ninguém conseguia
enxergar onde estava o desperdício. Não dá para melhorar o que não está descrito.

## O que foi feito

O trabalho seguiu cinco etapas, nesta ordem.

**Levantamento.** Conversei com os donos de cada rotina para entender o que era feito, em
que ordem, com quais sistemas e com quais exceções. Boa parte do processo real não estava
em nenhum lugar, só na cabeça das pessoas.

**Modelagem.** Desenhei cada processo em BPMN no Bizagi, com raias por responsável, pontos
de decisão e caminhos de exceção.

**Validação.** Levei cada mapa de volta para quem executava, para confirmar se o desenho
correspondia à realidade. Vários mapas voltaram corrigidos nesta etapa, porque o processo
descrito não era o processo praticado.

**Publicação.** Escrevi o procedimento de cada processo em linguagem de execução, com
passo a passo e critério de decisão, e publiquei no SharePoint da área, com versionamento
e controle de acesso.

**Governança.** Estabeleci rotina de revisão periódica e de registro de alteração, para o
manual não envelhecer em silêncio.

## Resultado

- 27 processos da área mapeados em BPMN
- Mais de 300 procedimentos operacionais produzidos e publicados
- Redução da dependência de conhecimento individual: a rotina passou a ser executável por
  qualquer pessoa da equipe, com o manual como referência
- Base documental que passou a sustentar as respostas a Controles Internos e auditorias
- Identificação, durante o próprio mapeamento, das etapas redundantes e das rotinas
  manuais repetitivas que viraram os projetos seguintes deste portfólio

## Por que este foi o projeto que destravou os outros

O mapa não serviu só para documentar. Ao desenhar os processos, ficou visível quais etapas
não geravam valor e quais eram manuais e repetitivas o suficiente para justificar
automação. Dois projetos nasceram daí: a eliminação de etapas em quatro processos e a
automação da conciliação de estornos.

Isso mostra a ordem correta de trabalho. Primeiro entender e documentar, depois simplificar,
e só então automatizar. Automatizar um processo que ninguém entende apenas acelera o
desperdício.

## Ferramentas

Bizagi (BPMN) | SharePoint | Excel

## Meu papel

Conduzi o mapeamento de ponta a ponta: levantei as rotinas com os donos de processo,
modelei em BPMN, validei os mapas com quem executava, redigi e publiquei os procedimentos
e mantive a rotina de revisão.

## O que aprendi

Documentar processo é atividade de escuta, não de desenho. O mapa que eu achava correto
voltava corrigido quase sempre, porque quem executa conhece exceções que não aparecem em
nenhuma entrevista inicial. Aprendi a validar antes de publicar, e isso mudou a qualidade
de tudo que veio depois.
