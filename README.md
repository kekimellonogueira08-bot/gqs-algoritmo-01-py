# Analisador de Palíndromos

Este projeto analisa frases e verifica se elas são **palíndromos**, ou seja, se permanecem iguais quando lidas de trás para frente. Para isso, o programa remove caracteres especiais, converte o texto para letras minúsculas e compara a frase com sua versão invertida.

##  Instalação

O projeto utiliza **Python 3**.

Verifique se o Python está instalado:

```bash
python --version
```

Caso o comando não funcione, tente:

```bash
python3 --version
```

Não são necessárias bibliotecas externas, pois o programa utiliza apenas o módulo `re`, que já faz parte da biblioteca padrão do Python.

## Como executar

Clone o repositório e entre na pasta do projeto:

```bash
git clone https://github.com/SEU-USUARIO/gqs-algoritmo-01-py.git
cd gqs-algoritmo-01-py
```

Execute o programa com:

```bash
python DesafioLogica.py
```

Ou:

```bash
python3 DesafioLogica.py
```

## Exemplo de entrada e saída

O programa utiliza duas frases definidas no próprio código:

```python
texto1 = "A sacada da casa de cadasa"
texto2 = "Socorram-me, subi no ônibus em Marrocos"
```

Ao executar, a saída esperada é:

```text
Teste 1: False
Teste 2: True
```

## Lógica do algoritmo

A função `analisar()` primeiro verifica se a entrada é `None`. Em seguida, utiliza uma expressão regular para remover caracteres que não sejam letras ou números e converte o texto para letras minúsculas.

Depois, a string é invertida utilizando `[::-1]`. Por fim, o programa compara a string original tratada com a string invertida: se forem iguais, retorna `True`; caso contrário, retorna `False`.

### Fluxo resumido

1. Recebe uma frase.
2. Remove caracteres especiais e espaços.
3. Converte para letras minúsculas.
4. Inverte a frase.
5. Compara as duas versões.
6. Retorna `True` ou `False`.

## Autor

**Kaio Moreira - 32510906**

**Erick Mello - 326211590**

**Icaro Ferreira - 325111358**

Projeto desenvolvido como atividade acadêmica da disciplina de **Garantia da Qualidade de Software**, sob orientação do professor **Daniel Paiva**.
