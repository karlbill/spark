# Spark
Estudo sobre Spark

## Introdução
O Spark é muito utilizado quando se precisa processar um grande volume de dados com alta performance e eficiência. Nesse momento, o Pandas pode não ser suficiente. Ou seja, o Spark é uma solução de Big Data. O Spark é uma estrutura de processamento paralelo, muito superior ao Hadoop.

Links úteis:
1. [Site Spark](https://spark.apache.org)
2. [Documentação Spark](https://spark.apache.org/documentation.html)
3. [O'Reilly livros](https://www.oreilly.com/beta-search/?q=pyspark&type=book&order_by=relevance)
## Instalação das Ferramentas
1. Instalação do Java: ``` apt-get install openjdk-8-jdk-headless -qq > /dev/null ``` 
2. Instalação do Python
3. Instalação do Apache Spark (versão: 3.1.2) / Hadoop 2.7 no Linux: </br>
``` wget -q https://dlcdn.apache.org/spark/spark-3.3.1/spark-3.3.1-bin-hadoop2.tgz ```
4. Descompactar o arquivo baixado: ``` tar xvf spark-3.3.1-bin-hadoop2.tgz ```
5. Adicionar as linhas abaixo no arquivo **~/.bashrc** : </br>
``` export SPARK_HOME=/[caminho_do_arquivo]/spark ```</br>
``` export PATH=$PATH:$SPARK_HOME/bin:$SPARK_HOME/sbin ```
6. Instalação do findspark: ``` pip install findspark ```
7. No Windows (para remoção de Warnings): instalação do *winutils.exe* -> mova o arquivo para a pasta **spark-3.1.2-bin-hadoop2.7/hadoop/bin**

## Adicionando o Spark a um Notebook do Jupyter
1. Como incluímos o diretório do Spark no PATH do sistema, o findspark não terá problemas em encontrálo:
``` 
import findspark
findspark.init() 
```
> Caso não tivéssemos feito a exportação do caminho do diretório para o PATH do sistema, teríamos que utilizar a lib **os** para configurar a variável de ambiente para esse diretório:
```
import os
os.environ["SPARK_HOME"] = [CAMINHO_DO_DIRETÓRIO_DO_SPARK]
```
Após as configurações acima, podemos importar o SparkSession do pyspark.sql e construir uma sessão do Spark:
```
from pyspark.sql import SparkSession
spark = SparkSession.builder.master('local[*]').appName("Iniciando com Spark").getOrCreate()
```
> O parâmetro local[*] significa que serão usados todos os processadores disponíveis na máquina local.

Conferindo a variável *spark*, temos:

![image](https://user-images.githubusercontent.com/39681960/203611034-7ce2291d-9c89-46dc-a464-1f304eb97741.png)

## Sobre o SparkSession
Link: [Documentação SparkSession](https://spark.apache.org/docs/latest/api/python/reference/pyspark.sql/api/pyspark.sql.SparkSession.html)

Contém 3 Interfaces:
1. Dataset: contém os benefícios do DataFrame e do RDD, disponíveis apenas nas linguagens Java e Scala;
2. DataFrame: registro e armazenamento de tabelas, execução de comandos SQL, leitura de arquivos;
3. Resilient Distributed Dataset (RDD): coleção de elementos particionados nos nós de um Cluster. É a API de nível mais baixo do Spark.

## Trabalhando com o conjunto de dados
Link:
[TSE - Resultado Eleição](https://cdn.tse.jus.br/estatistica/sead/odsele/votacao_candidato_munzona/votacao_candidato_munzona_2022.zip)

1. Feito o download, vamos realizar a descompactação diretamente pelo Notebook:
```

```




















