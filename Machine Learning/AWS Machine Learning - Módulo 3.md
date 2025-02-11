# AWS Machine Learning - Módulo 3
 
**Formulação do Problema e Coleta de Dados**
- Definição clara do problema
- Coleta e proteção de dados
- Obtenção de dados apropriados para ML

**Ambiente e Preparação dos Dados**
- Configuração do Jupyter Notebook no SageMaker
- Avaliação inicial dos dados
- Pré-processamento e engenharia de features
- Uso de ferramentas open source para análise

**Desenvolvimento do Modelo**
- Treinamento no Amazon SageMaker
- Implementação de validação cruzada
- Ajuste de hiperparâmetros

**Implantação e Avaliação**
- Hospedagem do modelo
- Execução de inferências
- Avaliação da precisão
- Otimização contínua do modelo

## Seção 1 - Formulando problemas de aprendizado de máquina
**Perguntas a serem feitas:**  
*Business*
- Qual o problema a ser resolvido? qual objetivo quero alcançar?
- Como essa tarefa é executada atualmente?
- Como a solução será usada?
- Existe algo pronto que posso usar de base?
- Quem são os especialistas responsáveis?

*Machine Learning*
- É um problema de ML?
- É supervisionado ou não?
- O que se busca prever?
- Possuo acesso aos dados?
- Qual a solução mais simples? Como seria solucionado manualmente?

## Seção 2 - Coleta e proteção de dados  
**Quais dados eu preciso?**  
- Quantos dados eu tenho e onde eles estão?
- Tenho acesso aos dados?
- Qual soluçao posso usar para centralizar os dados?

**Fontes de dados**  
*Dados Privados*  
- Os clientes que criam

*Dados Comerciais*  
- AWS Data Exchange, AWS Marketplace e outros provedores externos

*Dados Open Source*  
- Kaggle
- OMS
- EUA Census Bureau
- UCI Machine Learning Repository

**Observações**  
- São uma grande quantidade de dados, usados em casos que a resposta ou previsão já é conhecida  
- Recurso e Destino / Feature and Target

**Ferramentas para armazenar dados na AWS**
- Amazon S3
	- Armazenamento de objetos (arquivos) altamente escalável e durável na nuvem. Ideal para dados não estruturados.
- Amazon FSx
	- Sistema de arquivos gerenciado compatível com Windows e Linux. Bom para cargas de trabalho empresariais.
- Amazon EFS
	- Sistema de arquivos elástico para Linux, compartilhável entre múltiplas instâncias EC2.
- Amazon RDS
	- Serviço de banco de dados relacional gerenciado. Suporta MySQL, PostgreSQL, Oracle, SQL Server.
- Amazon Redshift
	- Data warehouse para análise de dados em larga escala, otimizado para consultas analíticas complexas.
- Amazon Timestreamn
	- Banco de dados de séries temporais gerenciado, projetado para IoT e aplicações que geram dados em sequência temporal.

### Seção 2A - ETL
**ETL com AWS Glue**
- Pode unir diferentes dados e emitir um único endpoint
- É possível criar uma função pelo AWS Lambda para, sempre que for criado algo, extrair os dados do S3 para o Glue.

**ETL COM PYTHON *exemplos***
- Importações e variáveis
```python
import boto3, requests, zipfile, os, io
url = 'http://url.com/somezipfile.zip'
folder='./extracts'`
```
- Fazer download e extrair
```python
r = requests.get(url, stream=True)
thezip = zipfile.ZiplFile(io.BytesIO(r.content))
thezip.extractall(folder)
```
- Fazer upload para o Amazon S3
```python
s3 = boto3.client('s3')
bucket = 'bucketname'
with os.scandir(folder) as dir:
	for f in dir:
		if f.is_file():
			s3.upload_file(
				Filename=os.path.join(folder, f.name),
				Key=f.name, Bucket=bucket)
```

### Seção 2B - Protegendo dados

**AWS Identity and Access (IAM)**
- Políticas para controle de acesso
```python
"Statement": [
    {
	"Sid": "Stmt1583974365198",
	"Action": ["s3:GetObject"], 				#GetObject limita o acesso a somente leitura
	"Effect": "Allow", 			    		#Allow permite a ação
	"Resource": "arn:aws:s3:::awsmachinelearningrepo/*", 	#Somente para este bucket
	"Principal": {"AWS": ["DataReaderRole"]}, 		#Apenas por essa função do IAM
    }
]
```
**Criptografia**
- A AWS fornece recursos de criptografia como o S3 e RDS

**Auditoria**
- AWS CloudTrail monitora a atividade do usuário e o uso da API

#@ Laboratório 3.1
### [Amazon SageMaker - Criação e importação de dados](https://github.com/felipeloche/Estudos-e-Anotacoes/blob/main/Laboratorio%201%20-%20Criacao%20e%20Importacao%20de%20Dados.md)

## Seção 3 - Avaliando os dados
- Formatar dados
- Examinar tipos de dados
- Executar estatísticas descritivas
- Visualizar dados  

Antes de executar estatísticas em seus dados, você deve garantir que eles estejam no formato correto para análise.  
Exemplo:  

```json
"Customer:ABC,DateOfTransation:10/5,Vendor:Store1,ChargeAmount:10.99,WasThisFraud:No..."
```

|   Customer  |  DateTran.  |   Vendor    | ChargeAmt.  |  WasFraud?  |
|-------------|-------------|-------------|-------------|-------------|
|    ABC      |   10/5      | Store1      |   10.99     |      No     |  

**Pandas**
- Reformata dados em representação tabular (DataFrame)
- Converte formatos comuns como CSV, JSON e outros
```python
import panda as pd
url = "https://somewhere.com/winequality-red.csv"
df_wine = pd.read_csv(url, ';')
```
**Nomes de índice e coluna**
```python
df_wine.columns #refere-se ao nome das colunas 
dw_wine.index #refere-se aos rótulos das linhas
```
**Esquema DataFrame**
```python
df_wine.dtypes #mostra os tipos de dados de cada coluna 
dw_wine.info() #fornece um resumo mais completo e datalhado do DataFrame
```
