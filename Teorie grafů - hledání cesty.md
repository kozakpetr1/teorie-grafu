Algoritmy pro hledání cest v grafech mohou být různé podle toho, zda se jedná o **neorientované** nebo **orientované grafy**, a podle toho, zda hledáme **nejkratší cestu**, **všechny cesty**, nebo jen zda existuje **jakákoli cesta** mezi dvěma vrcholy. Níže najdeš přehled nejběžnějších algoritmů:

---

### **1. Hledání cesty v grafu: DFS (Depth-First Search)**

Používá se pro nalezení cesty (ne nutně nejkratší) v grafech. Funguje tak, že prozkoumává co nejhlouběji graf, než se vrátí zpět.

#### Pseudokód:

```plaintext
Funkce DFS(vrchol_u, vrchol_cíl):
    Pokud vrchol_u == vrchol_cíl:
        Vrať TRUE (cesta existuje)
    
    Označ vrchol_u jako navštívený
    
    Pro každý soused_s vrcholu vrchol_u:
        Pokud soused_s není navštívený:
            Pokud DFS(soused_s, vrchol_cíl) vrátí TRUE:
                Vrať TRUE
    
    Vrať FALSE (žádná cesta nenalezena)
```

---

### **2. Hledání nejkratší cesty: BFS (Breadth-First Search)**

Pro grafy s nenegativními váhami hledá BFS nejkratší cestu. Funguje šířkově a objevuje vrcholy po vrstvách.

#### Pseudokód:

```plaintext
Funkce BFS(vrchol_start, vrchol_cíl):
    Vytvoř frontu a přidej do ní vrchol_start
    Označ vrchol_start jako navštívený
    Zaznamenávej vzdálenosti od startu
    
    Zatímco fronta není prázdná:
        vrchol_u = odeber z fronty
        Pokud vrchol_u == vrchol_cíl:
            Vrať vzdálenost[vrchol_u]
        
        Pro každý soused_s vrcholu vrchol_u:
            Pokud soused_s není navštívený:
                Označ soused_s jako navštívený
                Ulož vzdálenost[soused_s] = vzdálenost[vrchol_u] + 1
                Přidej soused_s do fronty
    
    Vrať -1 (pokud cesta neexistuje)
```

---

### **3. Hledání nejkratší cesty s váhami: Dijkstra**

Používá se pro grafy s neorientovanými/ orientovanými hranami, které mají váhy (nemohou být záporné).

#### Pseudokód:

```plaintext
Funkce Dijkstra(graf, vrchol_start):
    Inicializuj vzdálenosti všech vrcholů na nekonečno
    Vzdálenost[vrchol_start] = 0
    Vytvoř prioritní frontu a vlož (vrchol_start, 0)
    
    Zatímco fronta není prázdná:
        vrchol_u = odeber vrchol s nejnižší vzdáleností
        
        Pro každého souseda_s vrcholu vrchol_u:
            váha_hrany = váha(vrchol_u, soused_s)
            nová_vzdálenost = vzdálenost[vrchol_u] + váha_hrany
            
            Pokud nová_vzdálenost < vzdálenost[soused_s]:
                vzdálenost[soused_s] = nová_vzdálenost
                Přidej (soused_s, nová_vzdálenost) do fronty
    
    Vrať vzdálenosti
```

---

### **4. Algoritmus Floyd-Warshall (pro všechny dvojice vrcholů)**

Používá se pro hledání nejkratších vzdáleností mezi všemi dvojicemi vrcholů v grafu (i s váhami, mohou být i záporné, ale nesmí tvořit záporné cykly).

#### Pseudokód:

```plaintext
Funkce FloydWarshall(graf):
    Inicializuj matici vzdáleností (d[i][j] = ∞, pokud i != j, jinak 0)
    Pro každou hranu (u, v) nastav d[u][v] = váha(u, v)
    
    Pro každý prostředník k (od 1 do N):
        Pro každý vrchol i:
            Pro každý vrchol j:
                d[i][j] = min(d[i][j], d[i][k] + d[k][j])
    
    Vrať matici vzdáleností
```

---

### **5. Algoritmus A***

Optimalizovaný algoritmus pro hledání nejkratší cesty, který využívá heuristiku.

#### Využití:

- Grafy s váhami
- Grafy, kde je znám odhad vzdálenosti z vrcholu k cíli (heuristická funkce).

---

### **6. Bellman-Fordův algoritmus**

Bellman-Ford je algoritmus pro hledání **nejkratší cesty** z jednoho vrcholu do všech ostatních vrcholů v grafu. Na rozdíl od Dijkstrova algoritmu zvládne i **grafy se zápornými váhami hran**. Pokud však graf obsahuje **záporné cykly**, algoritmus dokáže detekovat jejich přítomnost, ale nezvládne vrátit korektní výsledky.

#### Princip:

Algoritmus postupně relaxuje (upravuje) všechny hrany grafu. Relaxace hrany kontroluje, zda by cesta přes tuto hranu poskytla kratší cestu k danému vrcholu. Tento proces se opakuje V−1V-1 krát (kde VV je počet vrcholů v grafu). Pokud po těchto iteracích lze stále provést další relaxaci, graf obsahuje záporný cyklus.

---

#### Pseudokód:

```plaintext
Funkce BellmanFord(graf, vrchol_start):
    Inicializuj vzdálenosti všech vrcholů na nekonečno
    Vzdálenost[vrchol_start] = 0
    
    Pro i = 1 až V-1:  (iterace)
        Pro každou hranu (u, v) v grafu:
            Pokud vzdálenost[u] + váha(u, v) < vzdálenost[v]:
                vzdálenost[v] = vzdálenost[u] + váha(u, v)
    
    Pro každou hranu (u, v) v grafu:
        Pokud vzdálenost[u] + váha(u, v) < vzdálenost[v]:
            Vrať "Graf obsahuje záporný cyklus"
    
    Vrať vzdálenosti (nebo nalezené nejkratší cesty)
```

---

#### Popis kroků:

1. **Inicializace**: Nastaví vzdálenost počátečního vrcholu na 0 a všech ostatních vrcholů na nekonečno.
2. **Relaxace hran**: Opakovaně upravuje vzdálenosti do ostatních vrcholů na základě hmotností hran.
3. **Detekce záporného cyklu**: Po V−1V-1 iteracích provede kontrolu, zda je možné ještě zlepšit vzdálenosti. Pokud ano, existuje záporný cyklus.

---

#### Složitost:

- **Časová složitost**: O(V⋅E)O(V \cdot E), kde VV je počet vrcholů a EE počet hran.
- **Prostorová složitost**: O(V)O(V) pro uchovávání vzdáleností.

---

#### Využití:

- Grafy s **negativními váhami** (např. při výpočtech zisků a ztrát).
- Detekce **záporných cyklů** v grafu.

Pokud chceš, můžu ti napsat implementaci Bellman-Ford algoritmu třeba v Pythonu! 😊