---
layout: post
author: igor
---
# Fundamentos práticos à computação quântica: Bloch sphere.

Esta é (provavelmente) uma longa lista de posts em relação à computação quântica.
Como você pode ter ouvido falar, Computação Quântica é uma abordagem promissora para resolver certos problemas, que são difíceis mesmo para os supercomputadores mais rápidos.
Processadores quânticos rudimentares já foram usados ​​para simular as propriedades de pequenas moléculas e resolver problemas otimização, e esses dispositivos agora são acessíveis para programação na nuvem.

Os tipos de operações e algoritmos são um pouco diferentes daqueles usados ​​em computadores clássicos, aproveitando as características da mecânica quântica como superposição e emaranhamento˙

Computadores quânticos utilizam propriedades únicas de partículas subatômicas em conjunção com as teorias de ciência da computação para processar e armazenar informações. 

Representação de informação digital convencional usa uma sequência de bits. Cada bit é basicamente a carga de um elétron. Se o elétron é carregado, o bit assume o valor 1; alternativamente o bit assume o valor 0 se o eletron não é carregado. Então, um bit pode ter o estado 0 ou 1.

Em sistemas de computação quântica como em sistemas clássicos, dois estados de sistemas distintos são necessários para representar um único dado. Por exemplo, considere um eletron de um átomo de hidrogênio que mostra o seu estado fundamental na Figura 1 seu estado excitado na Figura 2.

![](img/Fig.1.png)
![](img/Fig.2.png)


Se fosse em um sistema clássico, pode-se considerar que o estado de excitação represente um `|1⟩` e o estado fundamental represente `|0⟩`. Em geral, o elétron é um sistema quântico, que pode existir numa superposição linear de um estado fundamental e excitado. Isto é, este estado fundamental (0) com probabilidade e amplitude α e um estado de excitação (1) com probabilidade e amplitude β. Estes dois estados de sistema quântico são referidos como um quibit, e seu estado atual ψ pode ser qualquer combinação linear, ou conhecida como superposição, destes dois estados básicos. Veja a Figura 5.

![](img/Fig.5.png)

O estado de um _quibit_ pode ser visualizado como uma esfera imaginária e intuitiva na Figura 3 conhecida como _Bloch_ _sphere_. A seta da esfera representa o qubit. Os polos norte e sul representam o estado básico `|1⟩` e `|0⟩` , respectivamente; os outros pontos são superposições de `|0⟩` e `|1⟩`. Enquanto o bit em seu estado clássico pode ser polo norte e polo sul do equador, um qubit pode ser qualquer ponto da esfera.

![](img/Fig.3.png)

O interessante da Bloch sphere é que nos permite visualizar o qubit em coordenadas esféricas, por exemplo, o ângulo polar θ e φ. A representação Bloch sphere de um qubit é

![](img/Fig.4.png)

Note: Há quem argumente que, desde que o bit clássico é representado via voltagens, tal representação contém também coordenadas axis em dois polos.

Quando um quibt é mensurado, como a gente já discutiu antes, colapsa em um dos dois polos, que é a direção que a seta no Bloch o representa. Se a seta é próximo ao polo norte, existe uma alta probabilidade de colapsar naquele polo, similarmente quando a seta é para sul.

Para criar uma operação de um único qubit, siga os passos a seguir:

1 - Instale o Qiskit, uma ferramenta desenvolvida pela IBM Research, a Quantum Information Science Kit.
2 - Vamos usar o IBM Q pela Cloud.
3 - Importe o código QASM a seguir.

`include "qelib1.inc";`

`qreg q[1];`

`creg c[1];`

`x q[0];`

`measure q[0] -> c[0];`


Para entender matematicamente, leia o guia completo.

![](img/Fig.6.png)
![](img/Fig.7.png)

O código utiliza um X gate, que é conhecido como "bit-flip", uma vez que muda de 0 pra 1 e vice-versa.

Se começar no estado `|0⟩` do polo norte, o X gate rotaciona para o sul da esfera `|1⟩`.

Na representação da Bloch sphere, um qubit pode não só ser o sul o norte da esfera, mas tambem um estado que une os dois estados. Em outras palavras, um qubit pode existir em múltiplos estamos simultaneamente. Isso é basicamente a essência do princípio da superposição que acontece com as ondas naturais de partículas subatômicas.

A única propriedade que faz a computação quântica ser tão especial, é que o qubit, diferente dos bits clássicos, podem sobrepor o estado 0 e 1.

Um estado quântico de superposição pode ser escrito como uma combinação linear de `|1⟩` e `|0⟩`, sendo
`|φ⟩ = α|0⟩+β|1⟩` .

