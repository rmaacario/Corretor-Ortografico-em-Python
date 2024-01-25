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

### 1.2 Limpeza dos Dados
O texto do corpus foi tokenizado e filtrado para criar uma lista de palavras limpas.
