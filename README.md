# Construção de um Corretor Ortográfico em Python

## Introdução
Este projeto foi desenvolvido como parte do curso de Processamento de Linguagem Natural (NLP) na Alura. O objetivo principal é construir um corretor ortográfico simples em Python usando técnicas de processamento de texto e probabilidades.

## Bibliotecas Utilizadas
- Pandas
- NLTK (Natural Language Toolkit)

## 1. Dados de Treinamento
### 1.1 Leitura do Corpus
O corpus utilizado consiste em artigos da Alura e foi lido a partir de um arquivo de texto.

```python
file_path = "/caminho/para/o/arquivo/artigos.txt"
with open(file_path, "r") as file:
    corpus = file.read()
```

### 1.2 Limpeza dos Dados
O texto do corpus foi tokenizado e filtrado para criar uma lista de palavras limpas.
```python
lista_palavras = lista_palavras(tokenize(corpus))
frequencia_palavras_corpus = nltk.FreqDist(lista_palavras)
total_palavras = len(lista_palavras)
vocabulario = set(lista_palavras)
```

## 2. Funções de Correção
### 2.1 Corrigindo Erros por Inserção
```python
corretor_por_insercao('lgica')
# return ['lógica']
```

### 2.2 Corrigindo Erros por Alteração
```python
corretor_por_alterancia('lígica')
# return ['lógica']
```
### 2.3 Corrigindo Erros por Deleção de Caracteres
```python
corretor_deleta_caracter_extra('lóigica')
# return ['lógica']
```
### 2.4 Corrigindo Erros por Inversão de Caracteres
```python
corretor_inverte_caracteres('lgóica')
# return 'lógica'
```

### 2.5 Corrigindo Erros por Deleção de Dois Caracteres Extras Seguidos
```python
corretor_deleta_dois_caracteres_extras_seguidos('dosss')
# return ['dos']
```

## 3. Dados para Teste
Os dados de teste consistem em pares de palavras corretas e palavras com erros simulados.
```python
test_path = "/caminho/para/o/arquivo/palavras.txt"
with open(test_path, "r") as f:
    lista_palavras_teste = [tuple(linha.split()) for linha in f]
```

### 3.1 Função de Avaliação do Corretor
```python
avaliador(lista_palavras_teste, vocabulario)
# 79.57% de 186 palavras corrigidas corretamente.
# 6.99% de 186 palavras desconhecidas.
```
Este corretor ortográfico simples demonstra a aplicação de técnicas de processamento de linguagem natural para lidar com erros ortográficos em palavras. A avaliação com dados de teste fornece insights sobre a eficácia do corretor em diferentes cenários.

