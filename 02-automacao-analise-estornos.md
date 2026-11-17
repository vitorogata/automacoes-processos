# Automação da Análise de Estornos de Consignado (v1, macro no-code)

- **Empresa:** Itaú Unibanco
- **Área:** Consignado
- **Período:** 2023
- **Status:** a macro foi entregue e passou a ser usada na rotina diária da área. A versão em
Python é apenas um plano, descrita na última seção deste documento.

## Contexto

No consignado, as parcelas do empréstimo são descontadas direto na folha do cliente. Quando
um cliente antecipava parcelas, o desconto podia continuar acontecendo por engano, gerando
valor a ser estornado.

Chegava uma base diária com os clientes que deveriam ter sido estornados, contendo nome, CPF
e valor da parcela. Era preciso verificar, caso por caso, se o estorno havia sido aplicado.

## Problema

A verificação era 100% manual. Para cada linha da base, o ciclo era:

1. Abrir a planilha e localizar nome, CPF e valor da parcela
2. Acessar o sistema do banco
3. Buscar o cliente pelo nome e CPF
4. Abrir o extrato do cliente
5. Procurar no extrato o valor da parcela daquela linha
6. Classificar como "conforme" se encontrasse o valor, ou "não conforme" se não encontrasse

A base diária tinha milhares de linhas. O trabalho era repetitivo e dependia de atenção visual
constante. Erro de leitura tinha consequência financeira dos dois lados: classificar como
conforme um estorno que não aconteceu mantém o cliente cobrado indevidamente; classificar como
não conforme um estorno válido gera estorno indevido.

## A decisão de solução, e o caminho que foi bloqueado

Antes de automatizar, avaliei duas rotas.

**Rota ideal: cruzamento de bases.** A solução definitiva era cruzar a base de estornos com a
base que alimenta o sistema de extratos, comparando valores por chave. Isso eliminaria a
abertura de tela por tela.

**Por que não foi possível naquele momento:** os dois bloqueios não eram técnicos.
Primeiro, identificar quem eram os donos dessas bases dentro de um banco de grande porte,
com muitas áreas e muitas pessoas, não era simples para quem estava na ponta.
Segundo, extrato é dado sensível e confidencial, com acesso restrito. Para um estagiário,
obter esse acesso não era viável no prazo do problema.

**Rota escolhida: automação de interface com macro no-code.** Enquanto a negociação de acesso
seguia, implementei a alternativa viável: uma macro no JitBit que aprende o caminho dentro do
sistema e executa a validação CPF por CPF.

## O que foi feito

- Mapeamento do processo manual etapa por etapa, para identificar onde estava o esforço e onde
  estava o risco de erro
- Escolha de ferramenta no-code compatível com as permissões do banco naquele momento
- Configuração da macro para executar a sequência de busca e validação em cada registro
- Validação da saída da macro contra a conferência manual, em amostra, para confirmar que a
  classificação estava correta
- Ajuste das regras conforme as exceções apareciam

## Resultado

- Redução de 80% no tempo de análise desse processo
- Fim da digitação manual e da busca visual cliente por cliente
- Classificação padronizada, sem variação de critério entre execuções

## Limitação conhecida da solução

A macro rodava em primeiro plano, então o computador ficava ocupado durante a execução. Era um
trade-off aceito conscientemente: ganho de velocidade imediato com custo de máquina bloqueada.
A limitação ficou registrada como ponto de melhoria para a próxima versão.

## Próximo passo, ainda não executado

A solução definitiva continua sendo o cruzamento de bases. Com IA generativa disponível e
autorizada, a reconstrução pode ser feita em Python: leitura da base de estornos, cruzamento
por chave composta com a base de extratos, classificação automática em conforme e não
conforme, e relatório dos casos que exigem tratamento manual.

Registro aqui como próximo passo planejado, não como o que foi feito na empresa.

## Ferramentas

JitBit (macro no-code) | Excel | consulta a sistema interno | Bizagi para o mapeamento prévio

## Meu papel

Responsável pelo processo de ponta a ponta: identifiquei a oportunidade durante o mapeamento da
área, avaliei as rotas de solução, documentei o bloqueio de acesso a dados, construí a macro,
validei o resultado contra o processo manual e mantive a automação em operação.

## Aprendizado que carrego

Antes de automatizar, é preciso entender e simplificar o processo. Automatizar um fluxo que
ninguém entende apenas acelera o desperdício. Esse projeto foi o ponto de partida do meu
interesse por automação como disciplina, e não como ferramenta.
