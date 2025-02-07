# Livro Entendo Algoritmos
# Capítulo 1 - Introdução a Algoritmos

**Pesquisa Binária**
```python
def pesquisa_binaria (lista, item):
    baixo=0
    alto=len(lista)-1
    
    while baixo <= alto:
        meio = (baixo+alto) // 2
        chute = lista[meio]
        if chute == item:
            return meio
        if chute > item:
            alto = meio -1
        else:
            baixo = meio+1
    return None

minha_lista = [1,3,5,7,9]

print(pesquisa_binaria(minha_lista, 9))
print(pesquisa_binaria(minha_lista, -1))
```

- **Exercicios**

**1.1** Suponha que você tenha uma lista com 128 nomes e esteja fazendo uma pesquisa binária.  
Qual seria o número máximo de etapas que você levaria para encontrar o nome desejado?  
**R.: log²(128) = 7**

**1.2** Suponha que você duplique o tamanho da lista.  
Qual seria o número máximo de etapas agora?  
**R.: log²(256) = 8**

Forneça o tempo de execução para cada um dos casos a seguir em termos da notação Big O  
**1.3** Você tem um nome e deseja encontrar o número de telefone para esse nome em uma agenda telefônica  
**R.: O log(n)**

**1.4** Você tem um número de telefone e deseja encontrar o dono dele em uma agenda telefônica (Dica: Deve procurar pela agenda inteira)  
**R.: O(n)**

**1.5** Você quer ler os números de cada pessoa da agenda telefônica  
**R.: O(n)**

**1.6** Você quer ler os números apenas dos nomes que começam com A.  
(Isso é complicado! Este algoritmo envolve conceitos que são abordados mais profundamente no capítulo 4)  
**R.: O(n)**  
Mesmo que seja para apenas 1 dos 26 caracteres. No capítulo 4 será explicado sobre constantes na notação Big O

#### Recapitulando:
- A pesquisa binária é muito mais rápida do que a pesquisa simples
- O(log n) é mais rápido do que O(n), e O(log n) fica ainda mais rápido conforme os elementos da lista aumentam
- A rapidez de um algoritmo não é medida em segundos
- O tempo de execução de um algoritmo é medido por meio de seu crescimento
- O tempo de execução dos algoritmos é expresso na notação Big O
