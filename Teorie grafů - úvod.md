## Základní pojmy teorie grafů:
**Graf** v teorii grafů je **matematický objekt**, který se skládá z **uzlů** (také nazývaných vrcholy) a **hran**. Uzly představují objekty (např. místa, osoby nebo počítače) a hrany znázorňují vztahy nebo spojení mezi těmito objekty (např. silnice, přátelství nebo komunikační kanály).

**Graf:** Skládá se ze dvou množin:

- **Vrcholy (uzly):** Body, které reprezentují objekty v daném problému. Znázorňují se kružnicemi nebo tečkami.
- **Hrany:** Spojení mezi vrcholy. Znázorňují se čárami. Hrany mohou být orientované (se šipkou) nebo neorientované.

<iframe class="quiver-embed" src="https://q.uiver.app/#q=WzAsMyxbMSwwLCJcXGJ1bGxldCBBIl0sWzIsMSwiXFxidWxsZXQgQiJdLFswLDIsIlxcYnVsbGV0IEMiXSxbMiwwXSxbMCwxLCIiLDIseyJzdHlsZSI6eyJoZWFkIjp7Im5hbWUiOiJub25lIn19fV0sWzEsMl1d&embed" width="432" height="432" style="border-radius: 8px; border: none;"></iframe>


**Typy grafů:**

- **Neorientovaný graf:** Hrany nemají směr.
- **Orientovaný graf:** Hrany mají směr (od jednoho vrcholu k druhému).
- **Označený graf:** Hranám jsou přiřazeny hodnoty (váhy).
- **Vážený graf:** Vrcholům i hranám jsou přiřazeny hodnoty (váhy).
- **Úplný graf:** Každý vrchol je spojen s každým jiným vrcholem hranou.
- **Souvislý graf:** Pro každý pár vrcholů existuje cesta.
- **Strom:** Souvislý graf bez cyklů.

**Důležité pojmy:**

- **Stupeň vrcholu:** Počet hran, které z daného vrcholu vycházejí.
- **Cesta:** Posloupnost hran, která spojuje dva vrcholy tak, že žádná hrana se neopakuje.
- **Cyklus:** Cesta, která začíná a končí ve stejném vrcholu.
- **Délka cesty:** Součet vah hran na cestě.
- **Nejkratší cesta:** Cesta s nejmenší délkou mezi dvěma vrcholy.
- **Souvislost:** Schopnost grafu spojovat všechny jeho vrcholy cestami.
- **Stromová struktura:** Graf bez cyklů, ve kterém existuje právě jedna cesta mezi každým párem vrcholů.

**Aplikace teorie grafů:**

- Sociální sítě
- Dopravní systémy
- Počítačové sítě
- Bioinformatika
- Chemie
- Ekonomie
- A mnoho dalších

**Úkol 1:**
Jsou dány graf A a B.
![[grafy.png]]

1. Urči o jaké typy grafů se jedná (orientovaný/neorientovaný, neoznačený/označený/vážený, úplný/neúplný, souvislý/nesouvislý, cyklický/stromový).
2. Vyjádři grafy pomocí tabulek (matice sousednosti).
3. V pythonu vytvoř skript, který bude:
	- obsahovat inicializaci proměnných, ve kterých budou zaznamenány údaje grafů,
	- obsahovat funkci, která zjistí, zda je mezi zdrojovým a cílovým uzlem hrana,
	- obsahovat funkci, která zjistí, jestli je hrana mezi dvěma uzly obousměrná.

**Graf A**
- orientovaný, označený, neúplný, souvislý, cyklický

**Graf B**
- orientovaný, neoznačený, neúplný, souvislý, cyklický

**Graf A - matice sousednosti**

|     |  A  |  B  |  C  |  D  |  E  |  F  |  G  |  H  |  I  |
| :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
|  A  |  0  |  1  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |
|  B  |  1  |  0  |  3  |  2  |  0  |  0  |  0  |  0  |  0  |
|  C  |  0  |  3  |  0  |  0  |  4  |  0  |  0  |  0  |  0  |
|  D  |  0  |  0  |  0  |  0  |  0  |  0  |  2  |  3  |  0  |
|  E  |  0  |  0  |  4  |  0  |  0  |  2  |  0  |  0  |  0  |
|  F  |  0  |  0  |  0  |  0  |  2  |  0  |  0  |  0  |  3  |
|  G  |  0  |  0  |  0  |  2  |  0  |  0  |  1  |  0  |  0  |
|  H  |  2  |  0  |  0  |  3  |  0  |  2  |  2  |  0  |  0  |
|  I  |  0  |  0  |  2  |  0  |  0  |  3  |  0  |  0  |  0  |
**Graf B - matice sousednosti**

|     |  A  |  B  |  C  |  D  |  E  |  F  |  G  |  H  |  I  |
| :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
|  A  |  0  |  1  |  0  |  0  |  0  |  0  |  0  |  0  |  0  |
|  B  |  1  |  0  |  1  |  1  |  0  |  0  |  0  |  0  |  0  |
|  C  |  0  |  1  |  0  |  0  |  1  |  0  |  0  |  0  |  0  |
|  D  |  0  |  0  |  0  |  0  |  0  |  0  |  1  |  1  |  0  |
|  E  |  0  |  0  |  1  |  0  |  0  |  1  |  0  |  0  |  0  |
|  F  |  0  |  0  |  0  |  0  |  1  |  0  |  0  |  0  |  1  |
|  G  |  0  |  0  |  0  |  1  |  0  |  0  |  1  |  0  |  0  |
|  H  |  1  |  0  |  0  |  1  |  0  |  1  |  1  |  0  |  0  |
|  I  |  0  |  0  |  1  |  0  |  0  |  1  |  0  |  0  |  0  |

``` python
graf_a = [
    [0,1,0,0,0,0,0,0,0],
    [1,0,3,2,0,0,0,0,0],
    [0,3,0,0,4,0,0,0,0],
    [0,0,0,0,0,0,2,3,0],
    [0,0,4,0,0,2,0,0,0],
    [0,0,0,0,2,0,0,0,3],
    [0,0,0,2,0,0,1,0,0],
    [2,0,0,3,0,2,2,0,0],
    [0,0,2,0,0,3,0,0,0]
]
  
graf_b = [
    [0,1,0,0,0,0,0,0,0],
    [1,0,1,1,0,0,0,0,0],
    [0,1,0,0,1,0,0,0,0],
    [0,0,0,0,0,0,1,1,0],
    [0,0,1,0,0,1,0,0,0],
    [0,0,0,0,1,0,0,0,1],
    [0,0,0,1,0,0,1,0,0],
    [1,0,0,1,0,1,1,0,0],
    [0,0,1,0,0,1,0,0,0]
]

def je_hrana(graf, zdroj, cil):
    return True if graf[zdroj][cil] else False

def je_obousmerna(graf, uzel1, uzel2):
    return True if je_hrana(graf, uzel1, uzel2) and je_hrana(graf, uzel2, uzel1) else False

print(je_hrana(graf_a, 0, 7))
print(je_hrana(graf_a, 7 , 0))
print(je_obousmerna(graf_a, 0, 7))
```

**Úkol 2**
Je dán graf C.
![[strom.png]]

1. Urči o jaký typ grafu se jedná (orientovaný/neorientovaný, neoznačený/označený/vážený, úplný/neúplný, souvislý/nesouvislý, cyklický/stromový).
2. Vyjádři graf pomocí matice sousednosti.
3. V pythonu vytvoř skript, který bude:
	- obsahovat inicializaci proměnných, ve kterých budou zaznamenány údaje grafu,
	- obsahovat funkci, která zjistí, zda je mezi zdrojovým a cílovým uzlem hrana,
	- osahovat funkci pro traverzování stromu z vybraného uzlu.

``` python
import numpy as np

matice_sousednosti = np.array([
    [0, 1, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],  # A
    [1, 0, 0, 1, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],  # B
    [1, 0, 0, 0, 0, 1, 1, 0, 0, 0, 0, 0, 0, 0, 0],  # C
    [0, 1, 0, 0, 0, 0, 0, 1, 1, 0, 0, 0, 0, 0, 0],  # D
    [0, 1, 0, 0, 0, 0, 0, 0, 0, 1, 1, 0, 0, 0, 0],  # E
    [0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 1, 1, 0, 0],  # F
    [0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1, 1],  # G
    [0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],  # H
    [0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],  # I
    [0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],  # J
    [0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],  # K
    [0, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0],  # L
    [0, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0],  # M
    [0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0],  # N
    [0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0, 0, 0],  # O
])

# Depth-First Search (traverzování do hloubky)
def doHloubky(matice, start, navstiveno=None):
    if navstiveno is None:
        navstiveno = []
    navstiveno.append(start)
    print(start, end=" ")

    for soused, pripojen in enumerate(matice[start]):
        if pripojen and soused not in navstiveno:
            doHloubky(matice, soused, navstiveno)

doHloubky(matice_sousednosti, 0)
```

Ukázka postupu traverzování do hloubky:
![[dfs.png]]