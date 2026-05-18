Relatório

Aluno: Caio Henrique Alencar Coutinho dos Santos.

Método de remoção para nós com 2 filhos:

Para apagar um nó que tem dois filhos, usei o esquema do sucessor (menor dos maiores).
Justificativa: Em uma árvore binária, tudo que tá na esquerda é menor e tudo que tá na direita é maior. Se a gente tira um nó do meio que tem dois filhos, precisamos colocar outro no lugar para não quebrar a árvore. Para escolher o sucessor, o código vai uma vez para a direita e depois desce tudo para a esquerda até achar o menor valor de lá.
Esse nó serve para ser o novo topo daquela parte da árvore, porque ele é maior que todos da esquerda e menor que todos da direita. O código só copia o valor dele com o “atual.setConteudo()” e deleta o nó que ficou repetido lá embaixo, sem bagunçar o resto dos ponteiros.

Por que usei recursividade na remoção:

Justificativa: Para apagar um nó, a gente precisa avisar o nó pai dele sobre quem vai ficar no lugar (se vai ser um filho ou se vai ficar vazio/null). Se eu usasse um while (de forma iterativa), ia ter que criar uma variável No pai só para ficar guardando quem era o pai da vez, o que ia encher o código de if e else para saber se o nó era o filho da esquerda ou da direita.
Usando recursão, isso é resolvido direto na linha de código:
“atual.setEsquerda(removerRecursivo(atual.getEsquerda(), conteudo));“
Desse jeito, o próprio Java cuida de guardar o caminho na memória. Quando a função acha o nó substituto e volta, ela já vai grudando os ponteiros no lugar certo sem complicação.

