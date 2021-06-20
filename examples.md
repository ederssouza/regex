# Exemplos

## Capturando CPF

Dígitos e quantificadores

```bash
# ex 1
29531756015

# ex 2
43987830085
29531756015
61924334020
68403821093

# ex 3 => \d, \., -
439.878.300-85
295.317.560-15
619.243.340-20
684.038.210-93

# ex 4 => [-/]
439.878.300-85
29531756015
619.243.340/20
684.038.210-93

# ex 5 => \d, {4, 6}, ^, $, \b
# você precisa ter todas as possibilidades possíveis para montar uma boa regex
123456
1234
12345689
Texto 4567
6788 texto
Texto 4567 texto

# ex 6 => um pouco mais sobre quantificadores +, {1,}
# não sabe a quantidade máxima de caracteres? use + ou {1,}
# cuidado com o quantificador *, pois ele torna a captura opcional
123456
1234
12345689
```

## Capturando telefones

```bash
# ()
# '(11) 940042584'.match(/\(\d{2}\)\s?(9)?\d{4}-?\d{4}/)
# '(11) 40042584'.match(/\(\d{2}\)\s?(9)?\d{4}-?\d{4}/)
#
# () e |
# exemplo de DDD`s (SP e RJ)
João Carlos, 439.878.300-85,21 de maio de 1993,(21) 3079-9987,Rua do Ouvidor,50,20040-030,Rio de Janeiro
Pedro da Silva, 29531756015,12 de Janeiro de 1986,(11) 940042584,Rua da Pátria,12,06.127-015,São Paulo
Pedro da Costa, 619.243.340/20,12 de janeiro de 1986,(11) 958642584,Rua da Concórdia,4a,05244-011,São Paulo
Lucas Nunes, 684.038.210-93,18 de março de 2000,(31)36321001,Rua da Estação,2004,12345000,Minas Gerais
```

## Capturando nomes

```bash
# ex 1 => # flags, i, \w
lucas nunes

# ex 2
João Carlos, 439.878.300-85,21 de maio de 1993,(21) 3079-9987,Rua do Ouvidor,50,20040-030,Rio de Janeiro
Pedro da Silva, 29531756015,12 de Janeiro de 1986,(11) 940042584,Rua da Pátria,12,06.127-015,São Paulo
Pedro da Costa, 619.243.340/20,12 de janeiro de 1986,(11) 958642584,Rua da Concórdia,4a,05244-011,São Paulo
Lucas Nunes, 684.038.210-93,18 de março de 2000,(31)36321001,Rua da Estação,2004,12345000,Minas Gerais
```

## Validando tags HTML

```html
<!-- (1|2|3), \1 -->
<!-- <h(1|2)>.+?<\/h\1> -->
<!-- <h(\d)>.+?<\/h\1> -->
<h1>Título H1</h1>
<h2>Título H2</h2>
<h3>Título H3</h3>
```

## Se sobrar tempo

- Flags (g, m) (replace CPF)
- Negação de classes
- Evitar captura de grupos
