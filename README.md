<link rel="stylesheet" type="text/css" href="style.css"></link>
<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script type="text/javascript" async
  src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.7/MathJax.js?config=TeX-MML-AM_CHTML">
</script>

<script>
    function carregarImagem(input, id) {
        var reader = new FileReader();
        reader.onload = function (e) {
            var img = document.createElement("img");
            img.src = e.target.result;
            document.getElementById(id).appendChild(img);
        };
        reader.readAsDataURL(input.files[0]);
    }
</script>

<figure markdown=1>

![logo](https://upload.wikimedia.org/wikipedia/commons/f/fd/Logo_CEFET-MG.png)

<figcaption>CEFET-MG — Centro Federal de Educação Tecnológica de Minas Gerais</figcaption>
</figure>

DEPARTAMENTO DE COMPUTAÇÃO DE DIVINÓPOLIS — DECOM-DV

Laboratório de Eletrônica

Turma: 2024/1

Prof. M. Sc. Diego Ascânio Santos

<label for="alunos">Alunos: </label>
<input type="text" id="alunos" name="alunos" size="80" >

<label for="data">Data: </label>
<input type="date" id="data" name="data">

# Aula Prática 02 — Regulador de Tensão com Diodo Zener

## Conceitos Teóricos

### Diodo Zener

O diodo zener é um componente eletrônico similar a um diodo semicondutor normal, mas projetado para funcionar de maneira diferente: em operação intencional na região de ruptura para permitir o fluxo contrário de corrente (MALVINO; BATES, 2016)

Diferente de um diodo comum, que só conduz corrente em uma direção, o diodo zener conduz corrente na direção normal (polarização direta) e também na direção reversa, desde que a tensão aplicada ultrapasse um valor específico, chamado de tensão de ruptura (breakdown voltage).

É justamente essa característica que torna o diodo zener útil. Ele é muito utilizado para regular tensão em circuitos eletrônicos. Quando a tensão de entrada ultrapassa a tensão de ruptura do diodo zener, ele conduz corrente na direção reversa, dissipando o excesso de tensão e mantendo a tensão de saída praticamente constante, o que o torna apto para os seguintes usos:

-   **Regulador de Tensão**: Como explicado, o diodo zener é usado para manter a tensão de saída de um circuito estabilizada, evitando variações.
-   **Circuitos Clipadores**: Nesses circuitos, o diodo zener limita a amplitude do sinal elétrico, "cortando" a parte do sinal que excede a tensão de ruptura.

## Atividade Experimental

### Materiais e Equipamentos

-   Retificador de onda completa de \\(48V (V\_{AC})\\) com filtro capactivo de \\(1000 \mu F\\) construído na Aula 01;
-   Um Diodo Zener com tensão de ruptura de \\(9 V\\);
-   Um resistor \\(R\\) de \\(1 k\Omega\\);
-   Um resistor \\(R\_{L}\\) de \\(3.3 k\Omega\\);
-   Simulador [Falstad](https://www.falstad.com/circuit/circuitjs.html) e seus instrumentos de medidas virtuais tais quais: voltímetro, amperímetro, dentre outros;

### Regulador de Tensão com Diodo Zener

1. Carregue no Falstad um circuito retificador de tensão de onda completa com filtro capacitivo na saída. A tensão de entrada \\(V\_{AC}\\) do circuito deve ser de \\(48 V\\) e o filtro capacitivo deve ser de \\(1000 \mu F\\).
2. Monte o circuito apresentado na Figura 1.
    <figure markdown=1>
        ![](./img/zener.png)
        <figcaption>Aplicação Básica do diodo Zener. Fonte: (BENÍTEZ, 2022)</figcaption>
    </figure>
3. Meça a tensão contínula na carga \\(R\_{L}\\) e no resistor \\(R\\);
4. Cálcule a corrente na carga, em \\(R\\) e no diodo Zener à partir das tensões medidas;
5. Calcule a potência dissipada pelo diodo Zener;
6. Repita o experimento, utilizando \\(R\_{L} = 1k\Omega\\). Compare os resultados obtidos.
    \\[ R_{L_{min}} = \frac{RV_{Z}}{(V_{i} - V_{Z})} \\]
7. Preencha as tabelas abaixo para cada valor de \\(R\_{L}\\) utilizado.

#### Tabela para \\(R\_{L} = 3.3 k\Omega\\)

|                   | Valor Medido           | Valor Calculado        | Unidade |
| ----------------- | ---------------------- | ---------------------- | ------- |
| \\(V\_{Z}\\)      | <input type="number"/> | <input type="number"/> | V       |
| \\(V\_{R\_{L}}\\) | <input type="number"/> | <input type="number"/> | V       |
| \\(V\_{R}\\)      | <input type="number"/> | <input type="number"/> | V       |
| \\(I\_{R\_{L}}\\) | <input type="number"/> | <input type="number"/> | mA      |
| \\(I\_{R}\\)      | <input type="number"/> | <input type="number"/> | mA      |
| \\(P\_{Z}\\)      | <input type="number"/> | <input type="number"/> | mW      |

#### Tabela para \\(R\_{L} = 1 k\Omega\\)

|                   | Valor Medido           | Valor Calculado        | Unidade |
| ----------------- | ---------------------- | ---------------------- | ------- |
| \\(V\_{Z}\\)      | <input type="number"/> | <input type="number"/> | V       |
| \\(V\_{R\_{L}}\\) | <input type="number"/> | <input type="number"/> | V       |
| \\(V\_{R}\\)      | <input type="number"/> | <input type="number"/> | V       |
| \\(I\_{R\_{L}}\\) | <input type="number"/> | <input type="number"/> | mA      |
| \\(I\_{R}\\)      | <input type="number"/> | <input type="number"/> | mA      |
| \\(P\_{Z}\\)      | <input type="number"/> | <input type="number"/> | mW      |

#### Tabela para \\(R\_{L} = 500 \Omega\\)

|                   | Valor Medido           | Valor Calculado        | Unidade |
| ----------------- | ---------------------- | ---------------------- | ------- |
| \\(V\_{Z}\\)      | <input type="number"/> | <input type="number"/> | V       |
| \\(V\_{R\_{L}}\\) | <input type="number"/> | <input type="number"/> | V       |
| \\(V\_{R}\\)      | <input type="number"/> | <input type="number"/> | V       |
| \\(I\_{R\_{L}}\\) | <input type="number"/> | <input type="number"/> | mA      |
| \\(I\_{R}\\)      | <input type="number"/> | <input type="number"/> | mA      |
| \\(P\_{Z}\\)      | <input type="number"/> | <input type="number"/> | mW      |

## Formulários

- Corrente do Zener sem carga \\(R_{L}\\):
    \\[ I_{Z} = \frac{V_{i} - V_{Z}}{R} \\]
- Corrente do Zener com carga:
    - Corrente do resistor \\(R\\):
        \\[ I_{R} = \frac{V_{i} - V_{Z}}{R} \\]
    - Corrente do resistor \\(R_{L}\\):
        \\[ I_{R_{L}} = \frac{V_{Z}}{R_{L}} \\]
    - Corrente do Zener:
        \\[ I_{Z} = I_{R} - I_{R_{L}} \\]
- Tensão de Zener sem carga \\(R_{L}\\):
    \\[ V_{Z} = V_{i} - I_{Z}R \\]
- Tensão de Zener com carga:
    \\[ V_{Z} = V_{R_{L}} = R_{L} \times I_{L} \\]
- Excedente da tensão de zener com carga:
    \\[ V_{E_{Z}} = {\frac{R_{L}}{R_{S} + R_{L}} \times V_{i}} \\]
- Potência dissipada pelo Zener:
    \\[ P_{Z} = V_{Z} \times I_{Z} \\]

## Referências

-   MALVINO, A. P.; BATES, D. J. Eletrônica-Vol. 1: 8ª Edição. [s.l.] McGraw Hill Brasil, 2016.
-   BENÍTEZ, C. M. V. Eletrônica Geral 1 – Práticas de Laboratório. UTFPR, 2022.
