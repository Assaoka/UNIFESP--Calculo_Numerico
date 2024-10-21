# Aula 1: 08/10/2024
## Grupo:
- Thomas Pires Correia
- Miguel Gustavo Santos Rangel
- Lucas Molinari
- Lucas Castelani Gouveia
- João Victor Assaoka Ribeiro 

## Atividade 1: Erro de Unidade

`Objetivo:` Calcular a distância geodésica entre sua casa e a Unidade Parque Tecnológico da Unifesp usando de 1 a 6 casas decimais nas coordenadas lat long. Análise a diferença entre os resultados.

~~~python
Casa_Thomas = [-23.205850, -45.896660]
Unifesp = [-23.160230, -45.791520]

def distancia (a, b):
    return ((a[0] - b[0])**2 + (a[1] - b[1])**2)**0.5

def distancias (a, b):
    base = distancia(a, b)
    for i in range(6, 0, -1):
        print(f'{i} Casas Decimais:')
        dt = [round(a[0], i), round(a[1], i)]
        df = [round(b[0], i), round(b[1], i)]
        print(f'''Distância entre {dt} e {df}:''')

        dist = distancia(dt, df)
        erro = abs(dist - base)
        print(f'''Erro Absoluto: {erro}
Erro Relativo: {100*erro/dist}%
''')
~~~

~~~
6 Casas Decimais:
Distância entre [-23.20585, -45.89666] e [-23.16023, -45.79152]:
Erro Absoluto: 0.0
Erro Relativo: 0.0%

5 Casas Decimais:
Distância entre [-23.20585, -45.89666] e [-23.16023, -45.79152]:
Erro Absoluto: 0.0
Erro Relativo: 0.0%

4 Casas Decimais:
Distância entre [-23.2059, -45.8967] e [-23.1602, -45.7915]:
Erro Absoluto: 8.689614297341386e-05
Erro Relativo: 0.07576110936010569%

3 Casas Decimais:
Distância entre [-23.206, -45.897] e [-23.16, -45.792]:
Erro Absoluto: 2.3538150066476637e-05
Erro Relativo: 0.020533270085184813%

2 Casas Decimais:
Distância entre [-23.21, -45.9] e [-23.16, -45.79]:
Erro Absoluto: 0.006219797055721871
Erro Relativo: 5.1475406692271%

1 Casas Decimais:
Distância entre [-23.2, -45.9] e [-23.2, -45.8]:
Erro Absoluto: 0.014610662680222208
Erro Relativo: 14.610662680222001%
~~~

`Erro Absoluto:` 0.02681069355708035

`Erro Relativo:` 23.39284402524147%

## Atividade 2: Bissecção

`Objetivo:` No ano de 1225 Leonard of Pisa estudou a equação `x**3 + 2*x**2 + 10*x - 20 = 0` e obteve x=1.368808107. Ninguém sabe qual método Leonard usou, mas a solução é uma boa aproximação. Encontre uma aproximação usando o método da bissecção em Python.

~~~python
def função (x):
    return x**3 + 2*x**2 + 10*x -20

def bissecção (ini, fim):
    meio = (fim + ini)/2
    while (abs(fim - ini) > 10**(-9) or abs(função(meio)) > 10**(-9)):
        if (função(meio) > 0):
            fim = meio
        else:
            ini = meio
        meio = (fim + ini)/2
        print(meio)

    return meio    

bissecção(1, 2)
~~~

~~~
1.25
1.375
1.3125
1.34375
1.359375
1.3671875
1.37109375
1.369140625
1.3681640625
1.36865234375
1.368896484375
1.3687744140625
1.36883544921875
1.368804931640625
1.3688201904296875
1.3688125610351562
1.3688087463378906
1.3688068389892578
1.3688077926635742
1.3688082695007324
1.3688080310821533
1.3688081502914429
1.368808090686798
1.3688081204891205
1.3688081055879593
1.3688081130385399
1.3688081093132496
1.3688081074506044
1.368808108381927
1.3688081079162657
1.368808107683435
1.3688081077998504
~~~

`Saída Final:` 1.3688081077998504
