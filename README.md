# dtrepat_PAC4

## Introducció
Projecte corresponent a la PAC4 de l'assignatura de 22.403 - Programació per a la ciència de dades de la UOC.

Concretament, el projecte tracta i analitza dades sobre l'Orbea Monegros, una prova de ciclisme de muntanya (BTT) no competitiva que es realitza a Sariñena (Osca).


## Instal·lació i posada en funcionament
Passos per instal·lar el projecte:

1. Clona el repositori a la teva màquina local (en cas que l'hagis descarregat, saltat aquest pas). Per descomprimir-lo usa la comanda unzip i el nom del fitxer al terminal (si bé hi ha moltes altres formes).

```bash
git clone https://github.com/trepi93/dtrepat_PAC4
```


2. Navega fins al directori on s'ha descarregat o descomprimit el projecte 
```bash
cd dtrepat_PAC4
```


3. Instal·la les dependències necessaries (es recomana crear un virtual enviroment per fer-ho). També ho pots fer seguint els passos especificats a [setup.py](#setuppy)

(Opcional) Passos per crear un virtual enviroment 

a. Si s'executa amb linux
```bash
virtualenv venv
source venv/bin/activate
```

b. Si s'executa amb Windows
```bash
python3 -m venv venv
venv\Scripts\activate
```
En qualsevol cas, instal·la les dependències fent:
```bash
python3 -m pip install -r requirements.txt
```

Un cop fet això, ja tindràs el projecte instal·lat. En cas de que fallés la instal·lació dels paquets, assegura't de tenir la versió de python actualitzada (o almenys superior a la 3.9) i, si ho estàs executant en Windows, tenir tots els compiladors instal·lats. En cas contrari, actualitza la versió de python i instal·la o configura els compil·ladors (usant, per exemple Microsoft Visual Studio Build Tools).


## Estructura del Projecte

El codi del projecte consta de la següent estructura:


- **`src/`**: Conté el codi font del projecte, dividit en diversos mòduls.
  - **`exercise_1.py/`**: Codi corresponent a l'exercici 1. Importació del dataset
  - **`exercise_2.py/`**: Codi corresponent a l'exercici 2. Neteja del dataset
  - **`exercise_3.py/`**: Codi corresponent a l'exercici 3. Histograma
  - **`exercise_4.py/`**: Codi corresponent a l'exercici 4. Clubs Ciclistes
  - **`exercise_5.py/`**: Codi corresponent a l'exercici 5. Unió Ciclista Sant Cugat (UCSC)
  - **`main.py/`**: Codi que executa tots els mòduls i mostra la solució

- **`tests/`**: Conté les suits de testos del projecte
  - **`test_ex1.py/`**: Tests corresponents a l'exercici 1
  - **`test_ex2.py/`**: Tests corresponents a l'exercici 2
  - **`test_ex3.py/`**: Tests corresponents a l'exercici 3
  - **`test_ex4.py/`**: Tests corresponents a l'exercici 4
  - **`test_ex5.py/`**: Tests corresponents a l'exercici 5
  - **`test_main.py/`**: Tests corresponents al fitxer main

- **`data/`**: Conté les dades usades en el projete i en els tests
- **`img/`**: Conté l'histograma generat durant l'anàlisi
- **`license.txt`**: Conté la llicència del projecte
- **`README.md`**: Es aquest document, i explica com instal·lar i executar el projecte i els seus tests
- **`requirements.txt`**: Conté les dependències necessàries del projecte.
- **`setup.py`**: Fitxer de configuració i distribució del paquet dtrepat_PAC4


## Com executar-lo
A fi d'executar el projecte, un cop instal·lat, al terminal, posar la següent comanda

```bash
python3 -m src.main
```

Aquesta comanda, per defecte executarà tots els exercicis del projecte, de l'1 al 5. En cas que es desitgi executar menys exericis, es pot usar el parametre opcional --exercise, tot indicant el número d'exercici fins el qual es vol executar. En aquest cas, executarà d'1 fins a n, essent n el número indicat.

```bash
python3 -m src.main --exercise n
```

Així, per exemple si executem la següent comanda, obtindrem els exercisi de l'1 al 3 (inclòs)

```bash
python3 -m src.main --exercise 3
```

## Tests
D'altra banda, també s'han previst una sèrie de suit de testos. Per tal d'executar-los usarem el mòdul coverage. Concretament, executarem la següent comanda:

```bash
coverage run --source=. -m unittest discover -s tests
```

I, per veure el grau de cobertura dels tests usarem:

```bash
coverage report
```

Actualment, aquesta comanda retorna la següent taula:

```
Name                 Stmts   Miss  Cover
----------------------------------------
src/__init__.py          0      0   100%
src/exercise_1.py       20      0   100%
src/exercise_2.py       21      0   100%
src/exercise_3.py       50      3    94%
src/exercise_4.py       23      0   100%
src/exercise_5.py       21      0   100%
src/main.py             29      4    86%
tests/__init__.py        0      0   100%
tests/test_ex1.py       45      1    98%
tests/test_ex2.py       61      1    98%
tests/test_ex3.py       59      1    98%
tests/test_ex4.py       70      1    99%
tests/test_ex5.py       59      1    98%
tests/test_main.py      27      1    96%
----------------------------------------
TOTAL                  485     13    97%
```

## Estil de codi
Tanmateix, també hem previst l'opció de veure el compliment dels estàndards d'estil PEP8 pels nostres fitxers. Per fer-ho cal executar la següent comanda per veure el resultat d'estil del codi font

```bash
pylint src/*.py
```
o la següent per veure el resultat d'estil dels tests

```bash
pylint tests/*.py
```

## setup.py
Hem creat un fitxer setup.py que permet empaquetar i distribuir ràpidament el nostre paquet. Per fer-ho, un cop descarregat el nostre paquet, des del directori (i entorn virtual) si s'escau, el podem instal·lar usant la següent comanda:

```bash
pip install -e .
```

Un cop instal·lat tot ja podrem executar el nostre paquet tal com hem explicat en el punt *Com executar-lo*.
A més, també hem previst que amb una sola comanda puguem veure totes les solucions de l'exercici (en aquest cas, no està previst poder fer una execució sel·lectiva, és a dir fins a un exercici concret). Es fa executant la comanda:

```bash
dtrepat_pac4
```

## Llicència

Projecte llicenciat sota una MIT License. Veure license.txt per més informació.
