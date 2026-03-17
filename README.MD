O Guia Turístico Preguiçoso: Otimização de Rotas com Heurística Híbrida 🚶‍♂️⛰️

Este projeto apresenta uma aplicação de Inteligência Artificial voltada para a mobilidade urbana em cenários de relevo acidentado, utilizando como estudo de caso a cidade histórica de Ouro Preto - MG.

📖 Sobre o Projeto
Diferente dos sistemas de GPS tradicionais que focam apenas em distância ou tempo, o Guia Turístico Preguiçoso utiliza o algoritmo A* (A-Star) modificado para considerar o esforço físico necessário para vencer ladeiras. A aplicação compara o desempenho do algoritmo de Dijkstra contra o A* utilizando uma Heurística Híbrida inovadora.

🛠️ A "Mágica": Heurística Híbrida
O diferencial deste trabalho é a fórmula matemática da heurística (h(n)), que pondera dois fatores principais:
* Preguiça (j): Distância Haversine em linha reta até o destino.
* Esforço (i): Custo do desnível positivo (subida) acumulado.
* Fator Alpha (alpha): Parâmetro de ajuste que define o perfil do usuário, variando de um "Atleta" (alpha = 0) a um "Morrofóbico" (alpha = 1).

📊 Resultados Obtidos
A IA foi testada em 210 rotas reais simuladas em Ouro Preto:
* Divergência de Rota: Em 40,5% dos casos, a IA decidiu caminhar um trajeto mais longo no plano para evitar a exaustão de uma subida íngreme.
* Eficiência: O algoritmo A* foi significativamente mais eficiente que o Dijkstra, reduzindo em até 66% o número de nós visitados.
* Precisão Geográfica: Implementação da Fórmula de Haversine para cálculos precisos considerando a curvatura da Terra.

🚀 Tecnologias Utilizadas
* Python 3.
* Bibliotecas: Pandas (manipulação de dados), Matplotlib (visualização) e Heapq (fila de prioridade).
* Ambiente: Google Colab / Python Tools for Visual Studio.

🔗 Execução
O código completo com a análise de dados e gráficos pode ser visualizado e executado diretamente via Google Colab:
Acesse o Notebook do Projeto: https://colab.research.google.com/drive/14A1cweYDydJcqh8tdiphCxkmyXRosfhp?usp=sharing

Desenvolvido por Álefe Tonidandel na disciplina de Inteligencia Artificial da UFOP.
