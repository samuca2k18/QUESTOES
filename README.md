
## Questão 1: Soma de Números Naturais

Este programa realiza a soma de todos os números naturais de 1 até um valor específico definido na variável `variable` (neste caso, 13).

```python
# Inicializa a variável 'variable' com o valor 13, que representa o número de iterações
variable = 13

# Inicializa a variável 'soma' com 0, que irá acumular a soma dos números
soma = 0

# Inicializa a variável 'k' com 0, que servirá como contador no loop
k = 0

# Inicia um loop que continuará enquanto 'k' for menor que 'variable'
while k < variable:
    # Incrementa 'k' em 1 a cada iteração
    k += 1
    
    # Adiciona o valor atual de 'k' à variável 'soma'
    soma += k

# Após o loop, imprime o valor total da soma
print(soma)

```
**Explicação**:
- A variável `soma` armazena o valor acumulado da soma de 1 até `variable`.
- Em cada iteração do loop `while`, `k` é incrementado em 1 e seu valor é adicionado a `soma`.


## Questão 2: Verificar Pertinência à Sequência de Fibonacci

O programa verifica se um número informado pertence à sequência de Fibonacci.

```python
def pertence_fibonacci(n):
    # Inicializa os dois primeiros números da sequência de Fibonacci
    a = 0 
    b = 1
    
    # O loop continuará enquanto 'b' for menor que 'n'
    while b < n:
        # Atualiza 'a' e 'b': 'a' recebe o valor de 'b', e 'b' recebe a soma dos dois números anteriores
        a, b = b, a + b
        
    # Após o loop, verifica se 'b' é igual a 'n' ou se 'n' é 0
    if b == n or n == 0:
        return f"O número {n} pertence à sequência de Fibonacci."
    else:
        return f"O número {n} não pertence à sequência de Fibonacci."

# Solicita ao usuário que informe um número
numero = int(input("Informe um número: "))

# Chama a função e armazena o resultado
resultado = pertence_fibonacci(numero)

# Imprime o resultado
print(resultado)
```

**Explicação**:
- O código utiliza um loop para gerar a sequência de Fibonacci até que o valor seja maior ou igual a `n`.
- Caso `n` seja encontrado na sequência, o programa informa que ele pertence à sequência de Fibonacci.

## Questão 3: Análise de Faturamento Diário

O programa lê um arquivo JSON com o faturamento diário e calcula:
- O menor valor de faturamento ocorrido em um dia do mês.
- O maior valor de faturamento ocorrido em um dia do mês.
- O número de dias em que o faturamento foi superior à média mensal.

```python
import json

def calcular_faturamento(filename):
    with open(filename, 'r') as file:
        dados = json.load(file)["faturamento_diario"]

    # Filtrar valores válidos
    faturamento_valido = [f for f in dados if f > 0]

    # Calcular menor, maior e média
    menor_faturamento = min(faturamento_valido)
    maior_faturamento = max(faturamento_valido)
    media_mensal = sum(faturamento_valido) / len(faturamento_valido)

    # Contar dias acima da média
    dias_above_media = sum(1 for f in faturamento_valido if f > media_mensal)

    # Resultados
    print(f"Menor faturamento: {menor_faturamento}")
    print(f"Maior faturamento: {maior_faturamento}")
    print(f"Dias acima da média: {dias_above_media}")

# Exemplo de execução
calcular_faturamento("faturamento.json")
```

**Exemplo de JSON**:
```json
{
    "faturamento_diario": [0, 1500, 0, 1800, 0, 0, 0, 2100, 0, 1600, 2500, 0, 1700, 0, 0, 0, 1800, 2000, 2100, 0, 1900, 0, 0, 2200, 2100, 1800, 0, 0, 1750, 2200, 0]
}
```

## Questão 4: Percentual de Faturamento por Estado

O programa calcula o percentual de faturamento de cada estado em relação ao faturamento total.

```python
# Dicionário para armazenar o faturamento mensal por estado (em reais)
faturamento_por_estado = {
    "SP": 67836.43,
    "RJ": 36678.66,
    "MG": 29229.88,
    "ES": 27165.48,
    "Outros": 19849.53
}

# Calcula o faturamento total somando os valores de todos os estados
faturamento_total = sum(faturamento_por_estado.values())

# Exibe o faturamento total de forma formatada
print(f"O faturamento total da distribuidora foi de R$ {faturamento_total:.2f}.\n")

# Calcula e exibe o percentual de participação de cada estado no faturamento total
print("Aqui está o percentual de participação de cada estado no faturamento total:")
for estado, valor in faturamento_por_estado.items():
    percentual = (valor / faturamento_total) * 100
    print(f"- {estado}: {percentual:.2f}% do total")
```

**Explicação**:
- O programa calcula o faturamento total e, para cada estado, calcula o percentual de participação no faturamento total.

## Questão 5: Inversão de uma String

O programa inverte os caracteres de uma string informada pelo usuário sem usar funções prontas.

```python
# Solicita ao usuário uma string para inverter
string = input("Informe uma string para inverter: ")

# Variável para armazenar a string invertida
string_invertida = ""

# Posição inicial do índice para o último caractere da string
indice = len(string) - 1

# Enquanto o índice for maior ou igual a zero
while indice >= 0:
    # Adiciona o caractere atual à string invertida
    string_invertida += string[indice]
    
    # Move o índice para o caractere anterior
    indice -= 1

# Exibe a string invertida
print("String invertida:", string_invertida)
```

**Explicação**:
- O loop `while` começa do último caractere e percorre a string até o primeiro caractere, adicionando cada um a uma nova string chamada `string_invertida`.
  
---
