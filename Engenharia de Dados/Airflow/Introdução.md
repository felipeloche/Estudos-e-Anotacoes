# Introdução - Conhecendo o Apache Airflow

### O que é uma dag?
 Abreviação para "Directed Acyclic Graphs", em tradução livre, Grafos Acíclicos Dirigidos
- **Grafo** é uma ferramenta matemática com nós e arestas responsáveis por conectar esses nós.
- **Dirigidos** quer dizer que o fluxo trabalha em apenas uma direção.
- **Acíclico** significa que não entrará em loop de repetição, começando no nó inicial e encerrando no nó final.

A principal ideia do Airflow é dividir um trabalho grande em etapas individuais que chamamos de tarefa(tasks).

![DAG - Fazer uma prova](https://www.alura.com.br/artigos/assets/airflow-entendendo-dags/imagem2.png)

### Principais conceitos no Airflow
##### Webserver
- Oferece a interface de usuário do Airflow

##### Metadata Database
- Possui suporte para uma grande gama de banco de dados
- Nestes BD ficam armazenados informações como as configurações de DAGs e do próprio Airflow
- Qualquer modificação no Webserver são atualizadas no Metadata Database pelo Scheduler

##### Scheduler
- Responsável por garantir que as tasks dentro da DAG sejam executadas no momento certo
- Faz a leitura da DAG, extrai as informações e as coloca no BD
- Determina e ordena as tarefas que serão executadas

##### Executor
- É o mecanismo que trata do modo de execução das tasks
- Airflow permite apenas um executor configurado por vez
- Existem 2 tipos de executores:
###### 1. Executores Locais
- Sequential Executor (padrão)
- Local Executor 
###### 2. Executores Remotos
- Celery Executor
- Kubernetes Executor
- CeleryKubernetesExecutor

##### Operator
- Determina qual ferramenta executará as tasks
- Airflow fornece uma grande variedade de operadores, podendo rodar um em Bash, outro em Python, Docker etc
![DAG - Operators](https://www.alura.com.br/artigos/assets/airflow-entendendo-dags/imagem3.png)

Podemos dizer que a principal função de uma dag é realizar a orquestração dos operadores definidos.

##### DAG Run
- É a execução da DAG
- Quando a DAG é executada, um DAG Run é criado para todas as tasks dessa DAG.

###### Arquitetura do Airflow
![Arquitetura do Airflow](https://www.alura.com.br/artigos/assets/airflow-entendendo-dags/imagem4.png)