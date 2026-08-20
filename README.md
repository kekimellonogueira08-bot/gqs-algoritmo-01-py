# Desafio de Lógica — Análise de Palíndromos

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Status](https://img.shields.io/badge/Status-Concluído-brightgreen)
![License](https://img.shields.io/badge/License-MIT-green)

## Sobre o projeto

Este projeto foi desenvolvido como parte da atividade **Missão README**, da disciplina de **Garantia da Qualidade de Software**.

O objetivo da atividade é realizar uma análise do código-fonte existente, compreender seu funcionamento e documentá-lo de forma clara por meio deste arquivo `README.md`.

O programa desenvolvido em Python analisa uma entrada de texto e verifica se ela é um **palíndromo**.

Um palíndromo é uma palavra, frase ou sequência que permanece igual quando lida de trás para frente, considerando neste projeto apenas letras e números e ignorando diferenças entre letras maiúsculas e minúsculas.

---

## Linguagem utilizada

O projeto foi desenvolvido utilizando:

* **Python**
* Biblioteca padrão `re` para utilização de expressões regulares.

O arquivo principal do projeto é:

```text
DesafioLogica.py
```

---

## Objetivo do programa

O objetivo principal da função `analisar(entrada)` é verificar se uma determinada entrada de texto é um palíndromo.

Para realizar essa verificação, o programa:

1. Verifica se a entrada é `None`.
2. Remove caracteres que não sejam letras ou números.
3. Converte todas as letras para minúsculas.
4. Inverte a sequência de caracteres.
5. Compara o texto original tratado com o texto invertido.
6. Retorna `True` caso sejam iguais ou `False` caso sejam diferentes.

---

# Análise do código

## 1. Importação da biblioteca `re`

```python
import re
```

A biblioteca `re` é utilizada para trabalhar com **expressões regulares (Regex)**.

Neste projeto, ela é utilizada através da função `re.sub()` para remover caracteres que não sejam letras ou números da entrada.

---

## 2. Função `analisar(entrada)`

```python
def analisar(entrada):
```

A função `analisar()` é responsável por realizar toda a lógica de verificação do palíndromo.

Ela recebe um parâmetro chamado `entrada`, que representa o texto que será analisado.

Por exemplo:

```python
analisar("ovo")
```

Nesse caso, a entrada recebida pela função será:

```text
ovo
```

---

## 3. Verificação de entrada nula

```python
if entrada is None:
    return False
```

Primeiramente, o programa verifica se a variável `entrada` possui o valor `None`.

Caso isso aconteça, a função encerra sua execução e retorna:

```text
False
```

Isso evita que o restante do processamento seja realizado sobre uma entrada que não possui valor.

---

## 4. Limpeza da entrada

O código utiliza:

```python
limpa = re.sub(r'[^a-zA-Z0-9]', '', entrada).lower()
```

Essa é uma das partes mais importantes do programa.

A função `re.sub()` é utilizada para substituir determinados caracteres encontrados no texto.

A expressão regular utilizada é:

```text
[^a-zA-Z0-9]
```

Ela representa qualquer caractere que **não seja**:

* uma letra minúscula entre `a` e `z`;
* uma letra maiúscula entre `A` e `Z`;
* um número entre `0` e `9`.

O segundo argumento de `re.sub()` é:

```python
''
```

Como esse valor é uma string vazia, os caracteres encontrados são removidos.

### Exemplo

A entrada:

```text
Socorram-me, subi no ônibus em Marrocos
```

possui espaços, hífen e vírgula.

Após a limpeza, o resultado fica:

```text
Socorrammesubinonibusemmarrocos
```

Depois disso, o método:

```python
.lower()
```

transforma todas as letras em minúsculas:

```text
socorrammesubinonibusemmarrocos
```

Dessa forma, o programa consegue fazer a comparação sem considerar diferenças entre letras maiúsculas e minúsculas.

---

## 5. Inversão da string

Depois da limpeza, o programa executa:

```python
invertida = limpa[::-1]
```

O trecho:

```text
[::-1]
```

é uma técnica de **slicing (fatiamento)** do Python utilizada para percorrer a string de trás para frente.

Por exemplo:

```python
texto = "abc"
invertida = texto[::-1]
```

O resultado será:

```text
cba
```

No projeto, essa técnica é utilizada para criar uma versão invertida do texto que será comparada com a versão original tratada.

---

## 6. Comparação dos resultados

A última instrução da função é:

```python
return limpa == invertida
```

Nesse momento, o programa compara:

```text
texto tratado
```

com:

```text
texto tratado invertido
```

Se os dois forem iguais, o programa retorna:

```text
True
```

Caso sejam diferentes, retorna:

```text
False
```

Portanto, essa comparação é responsável por determinar se a entrada é ou não um palíndromo.

---

# Execução principal do programa

O código utiliza a seguinte estrutura:

```python
if __name__ == "__main__":
```

No Python, essa estrutura verifica se o arquivo está sendo executado diretamente.

Quando isso acontece, o programa executa os testes definidos abaixo dela.

É importante destacar que, diferentemente de linguagens como Java, este projeto não possui um método chamado `main()`. No Python, o bloco `if __name__ == "__main__":` desempenha o papel de definir o trecho executado quando o arquivo é iniciado diretamente.

---

# Testes realizados

O programa possui dois testes definidos no código.

## Teste 1

Entrada utilizada:

```text
A sacada da casa de cadasa
```

Depois da limpeza e conversão para letras minúsculas:

```text
asacadadacasadecadasa
```

A versão invertida é:

```text
asadacedasacadadacasa
```

Os dois valores são diferentes.

### Resultado

```text
Teste 1: False
```

### Análise

O resultado `False` indica que a sequência de caracteres obtida após o tratamento da entrada não é igual à sua versão invertida. Portanto, essa frase não é considerada um palíndromo pelo algoritmo.

---

## Teste 2

Entrada utilizada:

```text
Socorram-me, subi no ônibus em Marrocos
```

Após a remoção dos caracteres especiais, espaços e conversão para letras minúsculas:

```text
socorrammesubinonibusemmarrocos
```

Quando essa sequência é invertida, o resultado permanece exatamente igual:

```text
socorrammesubinonibusemmarrocos
```

### Resultado

```text
Teste 2: True
```

### Análise

O resultado `True` indica que a sequência tratada é igual à sua versão invertida. Dessa forma, a entrada é reconhecida pelo algoritmo como um palíndromo.

---

# Resumo dos testes

| Teste | Entrada                                   | Resultado |
| ----- | ----------------------------------------- | --------- |
| 1     | `A sacada da casa de cadasa`              | `False`   |
| 2     | `Socorram-me, subi no ônibus em Marrocos` | `True`    |

---

# 🔬 Fluxo de funcionamento

O funcionamento do algoritmo pode ser resumido da seguinte forma:

```text
Entrada
   ↓
Verifica se é None
   ↓
Remove caracteres que não são letras ou números
   ↓
Converte para letras minúsculas
   ↓
Inverte a sequência
   ↓
Compara a sequência original com a invertida
   ↓
True ou False
```

---

# Métodos e recursos utilizados

| Recurso                     | Função no programa                                         |
| --------------------------- | ---------------------------------------------------------- |
| `re.sub()`                  | Remove caracteres que não sejam letras ou números          |
| `.lower()`                  | Converte o texto para letras minúsculas                    |
| `[::-1]`                    | Inverte a sequência de caracteres                          |
| `==`                        | Compara o texto tratado com o texto invertido              |
| `analisar()`                | Concentra a lógica de verificação                          |
| `if __name__ == "__main__"` | Executa os testes quando o arquivo é executado diretamente |

---

# Observação sobre o enunciado

O enunciado da atividade menciona conceitos como `replaceAll`, `StringBuilder` e método `main`, normalmente associados a uma implementação em Java.

Entretanto, o código analisado neste repositório está implementado em **Python**.

Por isso, nesta documentação foram analisados os recursos que realmente estão presentes no código, como:

* `re.sub()`;
* expressões regulares;
* `.lower()`;
* slicing `[::-1]`;
* função `analisar()`;
* estrutura `if __name__ == "__main__":`.

Essa abordagem mantém a documentação fiel ao código-fonte analisado.

---

# Como executar

## 1. Instalar o Python

É necessário possuir o Python instalado no computador.

## 2. Baixar ou clonar o repositório

O repositório pode ser clonado utilizando:

```bash
git clone https://github.com/kekimellonogueira08-bot/gqs-algoritmo-01-py.git
```

Depois, entre na pasta:

```bash
cd gqs-algoritmo-01-py
```

## 3. Executar o programa

Execute:

```bash
python DesafioLogica.py
```

Em alguns sistemas, pode ser necessário utilizar:

```bash
python3 DesafioLogica.py
```

A saída esperada é:

```text
Teste 1: False
Teste 2: True
```

---

# Estrutura do projeto

```text
gqs-algoritmo-01-py/
│
├── DesafioLogica.py
├── README.md
├── LICENSE
└── .gitignore
```

---

# Sobre o autor

**Erick Mello Nogueira**

Atividade desenvolvida para a disciplina de **Garantia da Qualidade de Software**.

O repositório foi realizado a partir de um fork do projeto original, com o objetivo de analisar o código-fonte, executar os testes e produzir uma documentação técnica utilizando Markdown.

---

# Conclusão

A análise permitiu compreender o funcionamento do algoritmo responsável por identificar palíndromos.

O programa realiza o tratamento da entrada utilizando expressão regular, remove caracteres que não sejam letras ou números, converte o texto para letras minúsculas, inverte a sequência utilizando slicing e, por fim, compara a sequência original com sua versão invertida.

Através dos testes fornecidos no código, foi possível verificar dois comportamentos diferentes: o primeiro teste retorna `False`, enquanto o segundo retorna `True`.

Dessa forma, o README documenta o funcionamento do algoritmo, sua execução, os recursos utilizados e os resultados obtidos nos testes.
