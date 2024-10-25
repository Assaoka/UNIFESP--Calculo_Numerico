# Aula 2: 10/10/2024
## Grupo:
- Thomas Pires Correia
- Miguel Gustavo Santos Rangel
- Lucas Molinari
- Lucas Castelani Gouveia
- João Victor Assaoka Ribeiro 

## Função:

~~~python
def f(x):
    return x**5-3*x**3-5*x+4

def df(x):
    return 5*x**4-9*x**2-5

def newton(f,df,x0,tol=1e-6):
    x = x0
    i = 0
    while abs(f(x))>tol:
        i += 1
        x = x-f(x)/df(x)
    return x, i

print(newton(f,df,1))
~~~

## Resultado:
~~~
x0 = 0.6553181593147065
Iterações = 3
~~~