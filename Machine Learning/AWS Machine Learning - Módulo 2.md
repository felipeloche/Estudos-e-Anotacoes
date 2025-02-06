# AWS Machine Learning - Módulo 2

### Introdução
- O que é Machine Learning?
- Problemas de negócios resolvidos com ML
- Processo de ML
- Visão geral das ferramentas de ML
- Desafios de ML

##### Seção 1 - O que é ML?

- Um subdominio de IA, tendo Deep Learning como seu próprio subdominio.
Inteligência Artificial(Machine Learning(Deep Learning))
- ML é o estudo de algoritmos e modelos estatisticos para executar uma tarefa usando inferência em vez de instruções.
Dados -> Modelo -> Previsão.
- **Linha do Tempo**:
Computação Tradicional ->
Computação em nuvem e a lei de Moore ->
Machine Learning moderno.

- **Resumo**:
**IA**: Máquinas que executam tarefas humanas
**ML**: Modelos de treinamento para fazer previsões
**Deep Learning**: Redes Neurais
Avanços tecnológicos e econômicos tornaram machine learning mais acessível para indivíduos e organizações.


##### Seção 2 - Problemas de negócios resolvidos com ML
- **Casos de Uso**
    - Spam x E-mail normal
    - Itens recomendados
    - Fraude

**Tipos de Machine Learning**
- **Aprendizagem supervisionada (Classificação e Regressão):**
  - Reconhecimento de imagens
  - Previsão do tempo
  - Previsão de crescimento populacional
  - Visão computacional

- **Aprendizagem não supervisionada (Agrupamento em clusters e Redução de dimensionalidade):**
  - Recomendação de produtos
  - Segmentação de clientes
  - Descoberta de estrutura de dados

- **Processamento de linguagem natural**
  - Usado em chatbots e Alexa

- **Aprendizagem por reforço**
  - Conhece o resultado mas não o caminho.
  - Tentativa e Erro geram aprimoramento
  - IA de apoio, robótica, carros autoguiados

**Use ML quando tiver:**
  - Grandes conjuntos de dados, grande número de variáveis
  - Falta de procedimentos claros para obter a solução
  - Experiência existente em machine learning
  - Infraestrutura já implementada para oferecer suporte a ML
  - Suporte de gerenciamento para ML


##### Seção 3 - Processo de aprendizado de máquina

Problema de negócios > Formulação do problema > Coletar e rotular dados > Avaliar dados

Em ML as colunas representam recursos e as linhas representam instancias

Engenharia de Caracteristicas > Selecionar e treinar o modelo > Avaliar Modelo > Ajustar Modelo > Atende os objetivos do negócio?

Através dos dados rotulados, 80% irá ser usado para desenvolver o modelo treinado, enquanto os 20 finais serao usados posteriormente como dados de teste para que o modelo treinado possa prever

**Resultados do Treinamento**
- Sobreajuste
- Subajuste
- Balanceada

**Processo iterativo em 3 passos**
- Processamento de dados
- Treinamento
- Avaliação

##### Seção 4 - Visão geral das ferramentas de aprendizagem automática

- JupyterNotebook
- Pandas
- Matplotlib
- Seaborn
- NumPy
- scikit-learn
- Amazon SageMaker
  - Ground Truth
  - Notebook
  - Treinamento
  - Inferência
  - AWS Marketplace

##### Seção 5 - Desafios de ML
- Dados
  - Qualidade ruim
  - Insuficiente
  - Sobreajuste subajuste
- Negócios
  - Complexidade na formulaçao de perguntas
  - Explicação de modelos para a empresa
  - Custo dos sistemas de criação
- Usuários
  - Falta de especialização em ciência de dados
  - Custo da equipe do cientistas de dados
  - Falta de suporte
- Tecnologia
  - Problema com privacidade de dados
  - Integração com outros sitemas

Uso de modelos e serviços existentes simplificam ML.
- YOLO (You Only Look Once)

#### RESUMO
- ML é um subconjunto da IA
- O pipeline de ML  descreve os diferentes estágios para o desenvolvimento de uma aplicação ML
- Amazon Machine Learning tem 3 camadas principais: Serviços Gerenciados, Serviços de ML e Estruturas de ML
- O desenvolvimento de ML se difere do desenvolvimento tradicional.

***Fixação de Conhecimento***
1. ML é o estudo científico de algoritmos e modelos estatísticos para executar tarefas usando inferência em vez de instruções
2. Em um sistema de aprendizagem por reforço, o modelo interage com seu ambiente e aprende a realizar ações que maximizam as recompensas
3. Diferentemente da classificação binária, que lida com apenas duas classes (por exemplo, spam/não spam), a classificação multiclasse trabalha com múltiplos rótulos possíveis.
4. Os sistemas de ML que respondem à alterações no ambiente são sistemas de aprendizagem por reforço.
5. Durante o estágio de preparação de dados, você garante que todos os seus dados sejam de um tipo semelhante para que tenha uma única visualização coesa dos dados
6. Você pode converter os dados no estágio de preparação de dados
7. O sobreajuste ocorre quando o modulo funciona bem com os dados de treinamento, mas não com os dados de avaliação. 
O modelo está memorizando os dados de treinamento e não generalizando para novos dados.
8. pandas e scikit-learn são bibliotecas Python que você pode usar para trabalhar em problemas de ML
9. Amazon SageMaker é um serviço que você pode usar para implantar soluções de ML, hospedar Jupyter notebooks é também hospedar o JupyterLab
10. Antes de decidir desenvolver uma solução de ML, você deve ter um grande conjunto de dados com um grande número de variáveis.
