# Aprendendo-R
Iniciando meus estudos na análise de dados com o R
#Criando o primeiro Script
#Atribuindo um texto à uma variável, você pode atribuir com o sinal de = ou <-
mensagem = "Hello word!"
#Imprimindo o valor da variável
print(mensagem)
#O R executa linha por linha, então se quiser executar mais de uma linha tem que selecionar elas

#Caso você tenha dúvida de que se trata determinada função, basta colocar uma interrogação na frente dela e na aba Help aqui do lado vai aparecer a documentação dela
?print #Imprime o argumento
?head #Imprime as 6 primeiras linhas de um vetor ou data.frame(falaremos mais na frente o que são)
?str #Fornece informações sobre o tipo de dado, suas dimensões e o conteúdo das variáveis
?getwd #Acessa a pasta onde o R está coletando ou salvando os arquivos
?mean #Função genérica de média aritmética
?sd #Usada para calcular o desvio padrão de um conjunto de dados NUMÉRICOS
?sum #Usada para calcular a somda de dados NUMÉRICOS
?seq #Usada para criar sequências numéricas de acordo com os dados fornecidos.

#Instalando pacotes
#GGPLOT2 - Pacote usado para criar gráficos e visualização de dados de forma flexível e altamente personalizável, seguindo a Gramática dos Gráficos.
install.packages("ggplot2")
#Carregando o pacote ggplot2
library(ggplot2) # Deu erro, perguntar para o professor na terça

#Vetores - Armazena um conjunto de vetores ordenados, chamados de elementos, esses elementos devem ser do mesmo tipo.
#Criando um vetor
?c() #O c vem de COMBINAR, ou seja, ela cria e combina elementos em um único obejto
cidade = c("Brasília",
           "São Paulo",
           "Rio de Janeiro",
           "Porto Alegre")
cidade
#OBS: Lembre-se sempre de executar o código para depois imprimir os resultados

temperatura = c(32,22,35,17)
temperatura

região = c(1,2,2,3)
região

#Acessando elementos
cidade[1]
#Acessa o elemento correspondente aquela posição
#Acessando um intervalo de elementos
temperatura [1:3]
#Diz-se, imprima do primeiro elemento até o terceiro elemento desse vetor
#Copiando um vetor
cidade2 = cidade
cidade2
#Excluindo o segundo elemento da consulta
temperatura[-2]
#Alterando um vetor
cidade2[3] = "Belo Horizonte"
cidade2
#Entre colchetes fica a posição do vetor que se quer alterar
#Adicionando um novo elemento
cidade2[5] = "Curitiba"
cidade2
#Deletando o vetor
cidade2 = NULL
cidade2

#Fatores - armazena variáveis categóricas(nominal ou ordinal) - qualitativos
?factor
UF = factor(c("DF","SP","RJ","RS"))
UF

grau.instrucao = factor(c("Nível Médio",
                          "Superior",
                          "Nível Médio",
                          "Fundamental"),
                        levels = c("Fundamental",
                                   "Nível Médio",
                                   "Superior"),
                        ordered = TRUE)
grau.instrucao
#levels define a ordem de importância

#Listas
?list() #São estruturas de dados que podem contem elementos de diferentes tipos(diferente dos vetores)
pessoa = list(sexo ="M", cidade = "Brasília", idade = "20")
pessoa
#Acessando o primeiro elemento da lista
pessoa[1]
#Acessando o valor do primeiro elemento da lista
pessoa[[1]]
#Editando a lista
pessoa[["idade"]] = NULL
pessoa
#Criando novamente a lista
pessoa = list (sexo = "M", cidaede = "Brasília", idade = "20")
pessoa
#Listas de listas
cidade = list(cidade = cidade,
              temperatura = temperatura,
              região = região)
cidade

#Criando um data.frame com vetores
#Data.frame organiza elementos semelhantes a uma planilha
df = data.frame(cidade, temperatura)
df
df2 = data.frame(cidade)
df2
#Filtrando valores do dataframe
#Recuperando o valor da linha 1, coluna 2
df[1,2]
#Recuperando todas as linhas da primeira coluna
df[,1]
#Recuperando a primeira linha de todas as colunas
df[1,]
#Selecionando as 3 primeiras linhas da primeira e ultima coluna
df2[c(1:3),c(1:3)]
#Verificando o nome das colunas
names(df)
#Verificando o numero de linhasXcolunas
dim(df)
#Verificando os tipos de dados
str(df)
#Acessar uma coluna do dataframe
df$cidade
df['cidade']

#Matrizes
?matrix()
#Cria matrizes, que são estruturas bidimensionais(ou seja, com linhas e colunas)
#Criando uma matriz
m = matrix(seq(1:25),
           ncol = 5,
           byrow = TRUE,
           dimnames = list(c(seq(1:5)),
                           c('A','B','C','D','E'))
           )
m
m2 = matrix(seq(1:9),nrow = 3)
m2
#Filtrando matriz
m[c(1:2),c("B", "C")]
