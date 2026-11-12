# O Guia Turístico Preguiçoso

Roteamento de baixo esforço físico em Ouro Preto (MG) com A* e uma heurística híbrida.

Projeto desenvolvido na disciplina de Inteligência Artificial da UFOP, aplicado à mobilidade urbana
em relevo acidentado, com a cidade histórica de Ouro Preto como estudo de caso.

## Sobre o projeto

Sistemas de GPS tradicionais otimizam distância ou tempo. Em uma cidade de ladeiras, o caminho mais
curto costuma ser o mais cansativo. O Guia Turístico Preguiçoso busca o roteiro entre os pontos
turísticos que exige **menos esforço físico**, mesmo que isso signifique caminhar um pouco mais no plano.

A aplicação usa o algoritmo A* modificado para considerar o esforço de vencer subidas e compara seu
desempenho com o Dijkstra.

O sistema foi testado em tempo real por estudantes de mestrado, para verificar se as rotas funcionavam
na prática.
<!-- TODO: quantas pessoas, em que condições e o que observaram. -->

### Quando a volta não compensa

O desvio pelo plano só vale enquanto reduz o esforço de forma relevante. Quando o trecho plano passa a
custar cerca do dobro do caminho pelo morro, o esforço total fica parecido e o desvio é descartado.
<!-- TODO: confirmar o critério exato (dobro de quê: distância ou custo?) e onde está no código. -->

## A heurística híbrida

O diferencial do trabalho é a heurística `h(n)`, que pondera dois fatores:

| Fator | O que mede |
|---|---|
| **Preguiça (j)** | Distância de Haversine em linha reta até o destino |
| **Esforço (i)** | Custo do desnível positivo (subida) acumulado |
| **Alpha (α)** | Parâmetro que define o perfil do usuário: de **Atleta** (α = 0) a **Morrofóbico** (α = 1) |

<!-- TODO: colar aqui a fórmula exata de h(n), como está no notebook. -->

## Resultados

Avaliação em **210 rotas simuladas** entre pontos reais de Ouro Preto:

| Métrica | Resultado |
|---|---|
| Rotas avaliadas | 210 |
| Rotas em que o algoritmo escolheu um trajeto mais longo, porém mais plano | **40,5%** |
| Redução de nós visitados em relação ao Dijkstra | **até 66%** |

<!-- TODO: incluir a redução média (não só o máximo) e explicar como o 66% foi calculado. -->

A distância entre coordenadas usa a fórmula de Haversine, que considera a curvatura da Terra.

## Tecnologias

- Python 3
- Pandas (manipulação de dados), Matplotlib (visualização) e `heapq` (fila de prioridade)
- Google Colab e Python Tools for Visual Studio

## Como executar

O código completo, com a análise de dados e os gráficos, pode ser executado no Google Colab:
[Abrir o notebook do projeto](https://colab.research.google.com/drive/14A1cweYDydJcqh8tdiphCxkmyXRosfhp?usp=sharing)

## Autoria

Álefe Tonidandel, na disciplina de Inteligência Artificial da UFOP.
