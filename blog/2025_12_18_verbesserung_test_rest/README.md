---
author: Jakub Möslinger
date: '2025-12-18'
---

# Arbeit mit REST

## Musterlösung

``` python
import requests

isbn = input("ISBN: ")

url = f'https://apr.rasser.eu/api/v2/books/{isbn}'

response = requests.get(url)

if response.status_code == 200:

data = response.json()

print(data)
book = data['book']
print(f'{book['title']} ({book['isbn']})')

print('Autoren:')

num = 1

for author in book['authors']:
print(f'{num}. {author}')
num = num + 1

else:
error = response.json()
print("Fehler: {error['message']}")

```
## Erklärung (KI generiert)

### Zweck des Programms

Das Programm:

- fragt den/die Nutzer:in nach einer ISBN
- ruft über eine Web-API Informationen zu einem Buch ab
- gibt Titel, ISBN und Autoren aus
- zeigt eine Fehlermeldung, falls etwas schiefgeht


### Importiert das Modul requests

Damit kann man HTTP-Anfragen (z.B GET) an Webserver senden

```python
import requests
```

### URL aufbauen

Baut die URL für die API-ANfrage. Die eingegebene ISBN wird in die URL eingefügt

```python
url = f'https://apr.rasser.eu/api/v2/books/{isbn}'
```

### Abrfage senden

Sendet eine GET-Anfrage an die API. Die Antwort des Servers wird in response gespeichert

```python
response = requests.get(url)
```

und Status code ermitteln/überprüfen:
```python
if response.status_code == 200:
```

### Umwandlung der Daten

Wandelt die Antwort (JSON-Format) in ein Python-Dictionary um

```python
data = response.json()
```

### Ausgabe

Titel und ISBN ausgeben:

```python
print(f"{book['title']} ({book['isbn']})")
```

### Ausgabe der Autoren

Zähler für die Nummerierung der Autoren:
```python
num = 1 
```

Schleife über alle Autoren des Buches:
```python
for author in book['authors']:
```

Gibt jeden Autor nummeriert aus und erhöht den Zähler nach jedem Durchlauf

```python
print(f'{num}. {author}')
num = num + 1 
```

### Fehlermeldung

Im Fehlerfall('else') wird die NAchrihct der REST- Schnittstelle ausgeben

```python
error = response.json()
print(f"Fehler: {error['message']}")
```