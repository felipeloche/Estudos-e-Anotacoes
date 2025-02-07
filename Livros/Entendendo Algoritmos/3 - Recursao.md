# Capítulo 3 - Recursão

**Função Regressiva**
```python
def regressiva(i):
    print (i)
    regressiva(i-1)
```
- Ao escrever uma função recursiva, deve informar quando ela deve parar
- Toda função recursiva tem duas partes:
- Caso-recursivo: Quando a função chama a si mesma
- Caso-base: Quando a função não chama a si mesma novamente, evitando um loop infinito
```python
def regressiva(i):
    print (i)
    if i <=1: Caso-base
        return
    else: Caso-recursivo
        regressiva(i-1)
  ```     
**Pilha de chamada (call stack)**
```python
def sauda(nome):
    print("Olá, " + nome + "!")
    sauda2(nome)
    print("preparando para dizer tchau...")
    tchau()
#Essa função te cumprimenta e chama outras 2 funções
def sauda2(nome):
    print("Como vai "+nome+"?")
    
def tchau():
    print("ok, tchau!")
```

**Exercicios**
**3.1** - Suponha que eu forneça uma pilha de chamada como esta:  
 Sauda 2: [Nome: "Maggie"]  
 Sauda: [Nome: "Maggie"]  
Quais informações você pode retirar baseando-se apenas nesta pilha de chamada?  
**R.:** A função Sauda é chamada primeiro com o nome Maggie para posteriormente a Sauda 2 ser chamada;  
 A atual função chamada é Sauda 2, após a execução da mesma, voltará para a Sauda.

**Função recursiva para calcular fatorial**
```python
def fat(x):
    if x == 1:
        return 1
    else:
        return x * fat(x-1)
```
**3.2** - Suponha que você acidentalmente escreva uma função recursiva que fique executando infinitamente.  
Como você viu, seu computador aloca memória na pilha para cada chamada de função.  
O que acontece com a pilha quando a função recursiva fica executando infinitamente?  
**R.:** A pilha cresce eternamente. Quando o programa fica sem espaço, ele é finalizado com erro de overflow da pilha

#### Recapitulando:
- Recursão é quando uma função chama a si mesma
- Toda função recursiva tem dois casos: o caso-base e o caso recursivo
- Uma pilha tem duas operações: push e pop
- Todas as chamadas de função vão para a pilha de chamada
- A pilha de chamada pode ficar muito grande e ocupar muita memória