# Strings

## Strings

Strings sind Zeichenfolgen, die jedes Unicodezeichen repräsentieren können

## String-Methoden

- `.lower()`
- `.upper()`

## String-Methoden

- `.startswith(...)`
- `.endswith(".txt")`

## String-Methoden

- `.center(10)`
- `.ljust(10)`
- `.rjust(10)`

## String-Methoden

- `.strip()`
- `.split(' ')`
- `.splitlines()`
- `.join()`

## Raw Strings

Üblicherweise hat das Zeichen `\` eine besondere Bedeutung in Strings - z.B. in den Kombinationen `\n`, `\"` oder `\\`

Benötigen wir die ersten beiden nicht, können wir sogenannte _raw strings_ verwenden:

```py
path = r"C:\documents\foo\bar.txt"
```

## Übung: Faust

Formatierung von Goethes Faust

https://www.gutenberg.org/ebooks/2229

(siehe auch: "Gutenberg Mirror")

## Übung: Faust

Original:

```txt
  Ihr naht euch wieder, schwankende Gestalten,
  Die früh sich einst dem trüben Blick gezeigt.
```

Ziel:

```txt
Ihr naht euch wieder, schwankende Gestalten,               1
Die früh sich einst dem trüben Blick gezeigt.              2
```

## Übung: Faust

Weitere Aufgaben:

- Zeilennummern nur alle 5 Zeilen
- Zeilennummern alle 5 Zeilen, wenn die Zeile Text enthält - ansonsten in der nächsten Zeile