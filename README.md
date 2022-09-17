## Questão 1.

Faça um programa que peça ao usuário um número e imprima todos os números de um até o
número que o usuário informar.


```python
num = input("Digite um número: ")
i = 0
while i < int(num):
    i += 1
    print(i)
```

    Digite um número: 5
    1
    2
    3
    4
    5
    

## Questão 2.


Crie um programa que leia um valor qualquer e apresente uma mensagem dizendo em qual
dos seguintes intervalos ([0,25], (25,50], (50,75], (75,100]) este valor se encontra. Caso o valor não
esteja em nenhum destes intervalos, deverá ser impressa a mensagem “Fora de intervalo”. Veja
alguns exemplo abaixo:


```python
num = input('Digite um número: ')
num = int(num)
if num >= 0 and num <= 25:
    print ('Número no intervalo [0, 25]')
elif num > 25 and num <= 50:
    print ('Número no intervalo (25, 50]')
elif num > 50 and num <= 75:
    print ('Número no intervalo (50, 75]')
elif num > 75 and num <= 100:
    print ('Número no intervalo (75, 100]')
else:
    print ('Fora do intervalo')
```

    Digite um número: 101
    Fora do intervalo
    

## Questão 3.

Crie uma função que recebe o valor do raio de um círculo como parâmetro e retorna o valor da
área desse círculo. Lembrando que a área de círculo é dada pela equação: A = ℼ r^2


```python
import math
raio = int(input('Digite o valor do raio: '))

def area(r):
    return math.pi*(r**2)

print(area(raio))
```

    Digite o valor do raio: 5
    78.53981633974483
    

## Questão 4.

Faça um programa que peça 2 números inteiros e um número real, calcule e mostre: <br>
a) o produto entre o dobro do primeiro e a metade do segundo.<br>
b) a soma entre o triplo do primeiro e o terceiro.<br>
c) o terceiro elevado ao cubo.


```python
num1 = int(input('Digite o primeiro número: '))
num2 = int(input('Digite o segundo número: '))

res_a = (num1*2)*(num2/2)
res_b = (num1*3)+res_a
res_c = res_a**3

print('a) ',res_a)
print('b) ',res_b)
print('c) ',res_c)
```

    Digite o primeiro número: 10
    Digite o segundo número: 5
    a)  50.0
    b)  80.0
    c)  125000.0
    

## Questão 5.

Vamos fazer um programa para verificar quem é o assassino de um crime. Para descobrir o
assassino, a polícia faz um pequeno questionário com 5 perguntas onde a resposta só pode ser
sim ou não:
1. Mora perto da vítima?
2. Já trabalhou com a vítima?
3. Telefonou para a vítima?
4. Esteve no local do crime?
5. Devia para a vítima?<br>
Cada resposta sim dá um ponto para o suspeito. A polícia considera que os suspeitos com 5
pontos são os assassinos, com 4 a 3 pontos são cúmplices e 2 pontos são apenas suspeitos,
necessitando de outras investigações. Valores abaixo de 2 são liberados.
No seu programa, você deve fazer essas perguntas e, de acordo com as respostas do usuário,
você vai informar como a polícia o considera.


```python
cont = 0
resp1 = input('Mora perto da vítima? (S/N)')
if resp1 == 'S':
    cont += 1
resp2 = input('Já trabalhou com a vítima? (S/N)')
if resp2 == 'S':
    cont += 1
resp3 = input('Telefonou para a vítima? (S/N)')
if resp3 == 'S':
    cont += 1
resp4 = input('Esteve no local do crime? (S/N)')
if resp4 == 'S':
    cont += 1
resp5 = input('Devia para a vítima? (S/N)')
if resp5 == 'S':
    cont += 1
if cont == 5:
    print('Assassino')
elif cont >=3:
    print('Cúmplice')
elif cont == 2:
    print('Suspeito')
else:
    print('Liberado')
```

    Mora perto da vítima? (S/N)S
    MJá trabalhou com a vítima? (S/N)S
    MTelefonou para a vítima? (S/N)S
    Esteve no local do crime? (S/N)N
    Devia para a vítima? (S/N)N
    Cúmplice
    

## Questão 6.

Faça uma função que recebe uma lista de números e retorna a soma dos elementos dessa lista.


```python
def somatorio(lista):
    resultado = 0
    for i in lista:
        resultado = resultado + i
    return resultado

lista1 = [1,2,3]
print(somatorio(lista1))
```

    6
    

## Questão 7.

Faça um programa que leia as coordenadas de 2 (dois) pontos em um plano cartesiano 2D: a
coordenada x do primeiro ponto (x_1), a coordenada y do primeiro ponto (y_1), a coordenada x do
segundo ponto (x_2) e a coordenada y do segundo ponto (y_2). Em seguida, calcule a distância
euclidiana entre os pontos, utilizando a equação abaixo:<br>
𝑑 = (𝑥2 − 𝑥1)² + (𝑦2 − 𝑦1)²


```python
import math
x_1 = int(input('Informe o valor X do primeiro ponto: '))
y_1 = int(input('Informe o valor Y do primeiro ponto: '))
x_2 = int(input('Informe o valor X do segundo ponto: '))
y_2 = int(input('Informe o valor Y do segundo ponto: '))

calculo = math.sqrt((x_2-x_1)**2 + (y_2 - y_1)**2)
print(calculo)
```

    Informe o valor X do primeiro ponto: 4
    Informe o valor Y do primeiro ponto: 5
    Informe o valor X do segundo ponto: 1
    Informe o valor Y do segundo ponto: 1
    5.0
    

## Questão 8.

Calcule a soma de mil termos dos inversos dos fatoriais: 1/(1!) + 1/(2!) + 1/(3!) + 1/(4!) + ...
Dica: Use três variáveis:<br>
● um contador;<br>
● uma variável para soma;<br>
● e uma variável para os termos.<br>
Lembre-se de que 4! = 4 * *3 ** 2 * *1, que também é igual a 4 ** 3!.


```python
def somaFatoral():
    cont = 1
    while cont<1000:
        fat = cont**cont-1
        soma = 0
        if fat >0:
            inv = (1/fat)
            soma += inv
        cont += 1
        print(soma)
        
somaFatoral()
```

    0
    0.3333333333333333
    0.038461538461538464
    0.00392156862745098
    0.0003201024327784891
    2.143392991104919e-05
    1.2142671533449418e-06
    5.960464832810452e-08
    2.5811747983756604e-09
    1.0000000001e-10
    3.5049389948262095e-12
    1.1215665478462766e-13
    3.30169095523013e-15
    8.999274529781282e-17
    2.2836582605211673e-18
    5.421010862427522e-20
    1.2088386483023967e-21
    2.5415280553343456e-23
    5.054539349823847e-25
    9.5367431640625e-27
    1.7115705711410192e-28
    2.9288762467783086e-30
    4.7891646873397845e-32
    7.497736938283039e-34
    1.125899906842624e-35
    1.6243998950493898e-37
    2.255165233728459e-39
    3.016998695670444e-41
    3.894556968221558e-43
    4.8569357496188614e-45
    5.858514256996622e-47
    6.842277657836021e-49
    7.74533103173279e-51
    8.505832390100495e-53
    9.070233087627995e-55
    9.399612981435465e-57
    9.474061716781832e-59
    9.294442148136176e-61
    8.881377417591287e-63
    8.271806125530276e-65
    7.513838815703818e-67
    6.660852295672145e-69
    5.765757997627869e-71
    4.8762081342728105e-73
    4.031223528186754e-75
    3.259415621309696e-77
    2.5786991494945365e-79
    1.997195624728005e-81
    1.514928299964208e-83
    1.125899906842624e-85
    8.20202368384674e-88
    5.859035521275021e-90
    4.1056215205875246e-92
    2.8231696044364787e-94
    1.9056892223256258e-96
    1.2631952608473332e-98
    8.224949245144168e-101
    5.262309330901178e-103
    3.3092632248669374e-105
    2.0460911503225015e-107
    1.2441709715105564e-109
    7.442438440580729e-112
    4.380718879473942e-114
    2.5379418373156492e-116
    1.447544148867368e-118
    8.130181747984103e-121
    4.4976765403707425e-123
    2.451285724169995e-125
    1.3164753725684313e-127
    6.9684662181414696e-130
    3.6362793608495705e-132
    1.8709417094431164e-134
    9.493606161186191e-137
    4.751740771231285e-139
    2.3464172654755274e-141
    1.14331785713817e-143
    5.498119333482511e-146
    2.6098827092251135e-148
    1.223093865803144e-150
    5.659799424266695e-153
    2.5865058846772766e-155
    1.1675193968140756e-157
    5.206169850380846e-160
    2.2937177257339797e-162
    9.985994310600166e-165
    4.2966818078071464e-167
    1.8273638205108228e-169
    7.682894167466848e-172
    3.1936653662150523e-174
    1.3127261917780333e-176
    5.336214747839264e-179
    2.145457343509629e-181
    8.532686401775732e-184
    3.357235151026822e-186
    1.3069455596004046e-188
    5.0345612429349713e-191
    1.919295195600795e-193
    7.241767577341104e-196
    2.704679036164736e-198
    1e-200
    3.660507052763557e-203
    1.3267297885212e-205
    4.761741940137756e-208
    1.6925157271935753e-210
    5.958316895981572e-213
    2.0776781950104952e-215
    7.176881701264339e-218
    2.456034185275946e-220
    8.327444069448656e-223
    2.797722480846625e-225
    9.314281402666905e-228
    3.073133741196434e-230
    1.0049301736319853e-232
    3.257218911414821e-235
    1.0465219923356034e-237
    3.3332911532893065e-240
    1.0525777264660519e-242
    3.295513824922103e-245
    1.0230847102474698e-247
    3.1495642648994274e-250
    9.615462793078597e-253
    2.911391821527658e-255
    8.743217716155216e-258
    2.604420108771751e-260
    7.695704335233296e-263
    2.2558556970938454e-265
    6.560356474884124e-268
    1.8928834978668395e-270
    5.419102572533187e-273
    1.5394450804785577e-275
    4.3397056055711123e-278
    1.2140626006675278e-280
    3.3707904232526567e-283
    9.28874454179649e-286
    2.5406290125218414e-288
    6.897766069675449e-291
    1.8590124554587783e-293
    4.973774330571541e-296
    1.321121513175355e-298
    3.483974800022623e-301
    9.122316069810117e-304
    2.371674573639231e-306
    6.12275162858911e-309
    1.569643906054e-311
    3.996130625e-314
    1.0103761e-316
    2.5372e-319
    6.3e-322
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    0.0
    

## Questão 9.

Crie (manualmente ou sorteando os números) uma lista de 10 números e imprima:
1. uma lista com os 4 primeiros números;
2. uma lista com os 5 últimos números;
3. uma lista contendo apenas os elementos das posições pares;
4. uma lista contendo apenas os elementos das posições ímpares;
5. a lista inversa da lista sorteada (isto é, uma lista que começa com o último elemento da lista sorteada e termina com o primeiro);
6. uma lista inversa dos 5 primeiros números;
7. uma lista inversa dos 5 últimos números.


```python
lista = [1,2,3,4,5,6,7,8,9,10]
print(lista[:4])
print(lista[5:10])
print(lista[1::2])
print(lista[::2])
print(lista[::-1])
print(lista[:4:-1])
print(lista[4::-1])
```

    [1, 2, 3, 4]
    [6, 7, 8, 9, 10]
    [2, 4, 6, 8, 10]
    [1, 3, 5, 7, 9]
    [10, 9, 8, 7, 6, 5, 4, 3, 2, 1]
    [10, 9, 8, 7, 6]
    [5, 4, 3, 2, 1]
    

## Questão 10.

Na música, uma nota tem um tom (sua frequência, resultando em quão grave ou agudo é o som) e uma duração (por quanto tempo a nota soa). Neste problema, estamos interessados apenas na duração das notas.<br>
Marcos está dando os primeiros passos para ser um compositor de jingles. Ele está tendo alguns problemas, mas ao menos ele está criando melodias agradáveis e ritmos atrativos. Um jingle é dividido em uma sequência de compassos, e um compasso é formado de uma série de notas.<br>
A duração de uma nota é indicada pela sua forma. Neste problema, iremos utilizar letras maiúsculas para indicar a duração de uma nota. A seguinte tabela lista todas as notas disponíveis:<br>

![image.png](attachment:image.png)

A duração de um compasso é a soma da duração de suas notas. Nos jingles de Marcos, cada compasso tem a mesma duração. Como Marcos é apenas um iniciante, seu famoso professor Johann Sebastian III o ensinou que a duração de um compasso deve ser sempre 1.<br>
Por exemplo, Marcos escreveu uma composição contendo cinco compassos, dentre os quais quatro possuem a duração correta e um está errado. No exemplo abaixo, cada compasso é delimitado com barras e cada nota é representada como na tabela acima.
![image.png](attachment:image.png)

Marcos gosta de computadores assim como de música. Ele quer que você escreva um programa que determine, para cada uma de suas composições, quantos compassos possuem a duração correta e quais são os compassos com duração incorreta.
![image.png](attachment:image.png)


```python
comp = input('Digite sua composição: ')
#Notes
notasDic = {'W':1, 'H':1/2, 'Q':1/4, 'E':1/8, 'S':1/16, 'T':1/32, 'X':1/64}

compasso = comp.split('/')

#clean last and first items because it stores blanks in the list
compasso.pop()
del compasso[0]

count=0
erros = ''
corretos = 0
listaRes = []

for nota in compasso:
    res = 0
    for n in nota:
        res = res + notasDic[n]
    listaRes.append(res)
    if res != 1:
        erros = erros + f'{nota} '
    else:
        corretos = corretos + 1
    
print(f'Quantidade de corretos: {corretos}.\nIncorretos: {erros}')
```

    Digite sua composição: /HH/QQQQ/XXXTXTEQH/W/HW/
    Quantidade de corretos: 4.
    Incorretos: HW 
    


```python
/HH/QQQQ/XXXTXTEQH/W/HW/
/W/W/SQHES/
/WE/TEX/THES/
```
