# Laboratório 1 - Seção 3
# Amazon SageMaker - Criação e importação de dados

## Objetivos 
- Iniciar uma instância de notebook do Amazon SageMaker
- Criar e utilizar um notebook Jupyter
- Executar código nas células do notebook
- Baixar dados externos
- Gerenciar notebooks Jupyter localmente

## Principais Tarefas

### 1. Criando uma Instância de Notebook no SageMaker
1. Acessar o SageMaker através do AWS Management Console
2. Criar instância de notebook chamada "MyNotebook"
3. Selecionar tipo de instância: ml.m4.xlarge
4. Usar identificador de plataforma: notebook-al2-v1 (Amazon Linux 2)
5. Configurar lifecycle configuration com ml-pipeline
6. Aguardar a mudança de status de "Pending" para "InService"

### 2. Trabalhando com JupyterLab
- Navegar pela interface do JupyterLab
- Entender os diferentes tipos de células:
  - Células de código (para executar código)
  - Células Markdown (para texto formatado)
- Usar atalhos básicos do teclado:
  - SHIFT + ENTER (executar célula)
  - M (converter para Markdown)
  - B (adicionar célula abaixo)
  - ESC (sair da célula)

### 3. Projeto de Importação de Dados
- Download e extração de arquivos zip
- Carregamento de dados usando pandas
- Trabalho com arquivos ARFF
- Visualização básica de dados

#### Códigos Utilizados

1. Importação das bibliotecas necessárias:
```python
import warnings, requests, zipfile, io
warnings.simplefilter('ignore')
import pandas as pd
from scipy.io import arff
```

2. Download e extração do arquivo zip:
```python
f_zip = 'http://archive.ics.uci.edu/ml/machine-learning-databases/00212/vertebral_column_data.zip'
r = requests.get(f_zip, stream=True)
Vertebral_zip = zipfile.ZipFile(io.BytesIO(r.content))
Vertebral_zip.extractall()
```

3. Carregamento dos dados do arquivo ARFF:
```python
data = arff.loadarff('column_2C_weka.arff')
df = pd.DataFrame(data[0])
df.head()
```

### 4. Boas Práticas
- Salvar notebooks localmente antes do término do laboratório
- Fazer download do trabalho importante para evitar perda de dados
- Usar tipos apropriados de células para diferentes conteúdos
- Manter uma estrutura organizada do notebook

#### Arquivos Gerados Após Extração
Após a execução do código de extração, serão gerados quatro arquivos:
- column_2C_weka.arff
- column_2C.dat
- column_3C_weka.arff 
- column_3C.dat