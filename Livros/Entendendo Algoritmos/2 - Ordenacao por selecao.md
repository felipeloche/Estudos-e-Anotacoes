# Capítulo 2 - Ordenação por seleção

**Exercicios**
**2.1** Suponha que você esteja criando um aplicativo para acompanhar suas finanças  
1 - Compras | 2 - Cinema | 3 - Mensalidade  
Todos os dias você anotará tudo o que gastou e onde gastou.  
No final do mês, você deverá revisar os seus gastos e resumir o quanto gastou.  
Logo, você terá um monte de inserções e poucas leituras.  
Você deverá usar um array ou lista para implementar este aplicativo?  
**R.:** Lista Encadeada, pois haverá mais inserção do que leitura.  

**2.2** Suponha que você esteja criando um aplicativo para anotar os pedidos dos clientes em um restaurante.  
Seu aplicativo precisa de uma lista de pedidos. Os garçons adicionam os pedidos a essa lista e os chefes retiram os pedidos da lista.  
Funciona como uma fila. Os garçons colocam os pedidos no final da fila e os chefes retiram os pedidos do começo dela para cozinhá-los.  
Você usaria um array ou uma lista encadeada para implementar essa lista?   
*(Dica: listas encadeadas são boas para inserções/eliminações e arrays são bons para acesso aleatório. O que fazer neste caso?)*  
**R.:** Lista Encadeada. Há muitas inserções e não há necessidade de percorrer a lista pois sempre será removido o index da mesma.

**2.3** Vamos analisar um experimento. Imagine que o Facebook guarda uma lista de usuários.  
Quando alguém tenta acessar o Facebook, uma busca é feita pelo nome de usuário. Se o nome da pessoa está na lista, ela pode continuar o acesso.  
As pessoas acessam o Facebook com muita frequência, então existem muitas buscas nessa lista.  
Presuma que o Facebook usa a pesquisa binária para procurar um nome na lista.  
A pesquisa binária requer acesso aleatório - você precisa ser capaz de acessar o meio da lista de nomes instantaneamente.  
Sabendo disso, você implementaria essa lista como um array ou uma lista encadeada?  
**R.:** Array, pois fornece acesso aleatorio, podendo ir para o meio sem precisar percorrer desde o início.

**2.4** As pessoas se inscrevem no Facebook com muita frequência também. Suponha que você decida usar um array para armazenar a lista de usuários.  
Quais as desvantagens de um array em relação as inserções? Em particular, imagine que você está usando a pesquisa binária para buscar os logins.  
O que acontece quando você adiciona novos usuários em um array?  
**R.:** Inserções em arrays são lentas e necessitam já estar ordenadas. Ou seja, a cada inserçao precisaria ordenar em seguida.

**2.5** Na verdade, o Facebook não usa nem arrays nem listas encadeadas para armazenar informações. Vamos considerar uma estrutura de dados híbrida: um array de listas encadeadas.  
Você tem um array com 26 slots. Cada slot aponta para uma lista encadeada.  
Por exemplo, o primeiro slot do array aponta para uma lista encadeada que contém os usuários que começam com a letra A.  
O segundo slot aponta para a lista encadeada que contém os usuários que começam com a letra B, e assim por diante.  
Suponha que o Adit B se inscreva no Facebook e você queira adicioná-lo à lista.  
Você vai ao slot 1 do array, a seguir para a lista encadeada do slot 1, e adiciona Adit B no final.  
Agora, suponha que você queira procurar o Zakhir H. Você vai ao slot 26, que aponta para a lista encadeada de todos os nomes começados em Z.  
Então, procura pela lista até encontrar o Zakhir H.  
Compare esta estrutura híbrida com arrays e listas encadeadas. É mais lento ou mais rápido fazer inserções e eliminações nesse caso?  
Você não precisa responder dando o tempo de execução Big(O), apenas diga se a nova estrutura de dados é mais rápida ou mais lenta do que os arrays e as listas encadeadas. 
**R.:** Mais lenta para buscar que Arrays porém mais rápida ou igual à listas encadeadas em tudo. 

**Ordenação por seleção**
```python
def buscaMenor(arr):
    menor = arr[0]      #menor = Armazena o menor valor
    menor_indice = 0    #menor_indice = Armazena o índice de menor valor
    for i in range(1, len(arr)):
        if arr[i] < menor:
            menor = arr[i]
            menor_indice = i
    return menor_indice
```
```python
def ordenacaoporSelecao(arr):       #ordenaporSelecao = Ordenações em um array
    novoArr = []
    for i in range(len(arr)):
        menor = buscaMenor(arr)     #menor = Encontra o menor elemento do array e adiciona ao novo array
        novoArr.append(arr.pop(menor))
    return novoArr

print(ordenacaoporSelecao([5,3,6,2,10]))
```
#### Recapitulando:
- A memória do seu computador é como um conjunto gigante de gavetas
- Quando se quer armazenar múltiplos elementos, usa-se um array ou uma lista
- No array, todos os elementos são armazenados um ao lado do outro
- Na lista, os elementos estão espalhados e um elemento armazena o endereço do próximo elemento
- Arrays permitem leituras rápidas
- Listas encadeadas permitem rápidas inserções e eliminações
- Todos os elementos de um array devem ser do mesmo tipo (todos ints, doubles e assim por diante)