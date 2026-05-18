Relatório Técnico da Atividade (Pronto para Entrega)
Aluno(a): [Seu Nome]

Estrutura de Dados - Projeto Árvores 2026

1. Método Utilizado para Nós com Dois Filhos (Caso 3)
Para lidar com a remoção de nós que possuem dois filhos, foi adotada a estratégia do Sucessor, também conhecida na literatura como o Menor dos Maiores.

Justificativa Teórica: Em uma Árvore Binária de Busca (BST), a integridade estrutural exige que todos os nós à esquerda de uma raiz sejam menores que ela, e todos à direita sejam maiores. Quando removemos um nó intermediário com dois filhos, precisamos colocar um substituto que mantenha essa lei intacta. Ao escolhermos o Sucessor, o algoritmo faz uma transição para o ramo direito (onde todos os valores são maiores) e busca o elemento mais à esquerda possível desse ramo (o menor valor contido ali).

Impacto Operacional: Esse elemento é matematicamente perfeito para ser a nova raiz daquela subárvore, pois ele é maior que toda a subárvore esquerda existente e, simultaneamente, é menor que todos os elementos restantes da subárvore direita. Após transferir seu conteúdo por meio do método atual.setConteudo(), o algoritmo realiza uma exclusão simples do nó sucessor original da memória, sem a necessidade de rotacionar ou desestruturar o encadeamento dos outros nós da árvore.

2. Justificativa da Escolha pela Abordagem Recursiva
A funcionalidade de remoção foi implementada utilizando a metodologia Recursiva, contrastando com a inserção da classe original que continha uma lógica iterativa.

Navegação Dinâmica com Reencadeamento Automatizado: A remoção em árvores binárias necessita não apenas localizar o nó, mas também atualizar as referências do nó pai apontando para o novo substituto (seja null ou o filho sobrevivente). Em um formato iterativo, seríamos forçados a manter um ponteiro de rastreamento No pai = null durante toda a descida em um laço while. Isso geraria ramificações complexas de código condicional para verificar se o nó modificado era o filho esquerdo ou direito do pai em questão.

Aproveitamento da Pilha de Execução (Call Stack): A recursão simplifica este processo através da atribuição direta no retorno da chamada:

atual.setEsquerda(removerRecursivo(atual.getEsquerda(), conteudo));

Com essa instrução, o próprio compilador Java gerencia o empilhamento. Quando o nó substituto é retornado pela função, a atribuição é resolvida de baixo para cima, religando os ponteiros corretos de forma limpa, estéril de erros e condizente com a natureza matematicamente recursiva da estrutura de dados do tipo Árvore.
