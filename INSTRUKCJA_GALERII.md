# 📸 INSTRUKCJA ZARZĄDZANIA GALERIĄ HAIR ESTETIC

## 📋 Spis treści
1. [Struktura galerii](#struktura-galerii)
2. [Jak dodać nowe zdjęcia](#jak-dodać-nowe-zdjęcia)
3. [Jak usunąć zdjęcia](#jak-usunąć-zdjęcia)
4. [Jak zmienić kolejność zdjęć](#jak-zmienić-kolejność-zdjęć)
5. [Formaty zdjęć](#formaty-zdjęć)
6. [Rozwiązywanie problemów](#rozwiązywanie-problemów)

---

## 📁 Struktura galerii

Galeria znajduje się w dwóch plikach:
- `gallery.html` - wersja polska
- `gallery-en.html` - wersja angielska

⚠️ **WAŻNE**: Każda zmiana musi być wprowadzona w OBU plikach!

---

## ➕ Jak dodać nowe zdjęcia

### Krok 1: Przygotuj zdjęcia
- Potrzebujesz 2 zdjęcia: **PRZED** i **PO**
- Zalecane formaty: JPG, PNG, WebP
- Zalecana rozdzielczość: minimum 800px szerokości
- Zdjęcia powinny mieć podobne proporcje

### Krok 2: Znajdź sekcję z danymi galerii
Otwórz plik `gallery.html` i znajdź linię około 759, która wygląda tak:
```javascript
const galleryData = [
```

### Krok 3: Dodaj nowy wpis
Dodaj nowy obiekt na końcu listy (przed `];`):

```javascript
{
    before: 'https://adres-twojego-zdjecia-przed.jpg',
    after: 'https://adres-twojego-zdjecia-po.jpg',
    format: 'portrait' // Opcje: 'portrait', 'landscape', 'square'
}
```

### Przykład kompletnego wpisu:
```javascript
const galleryData = [
    // Istniejące wpisy...
    {
        before: 'https://www.hair-estetic.com/before1.jpg',
        after: 'https://www.hair-estetic.com/after1.jpg',
        format: 'portrait'
    },
    // Twój nowy wpis:
    {
        before: 'https://www.hair-estetic.com/before2.jpg',
        after: 'https://www.hair-estetic.com/after2.jpg',
        format: 'portrait'
    }
];
```

### Krok 4: Powtórz dla wersji angielskiej
Wykonaj dokładnie te same kroki w pliku `gallery-en.html`

---

## ➖ Jak usunąć zdjęcia

### Metoda 1: Usunięcie konkretnego wpisu
1. Znajdź wpis który chcesz usunąć w sekcji `galleryData`
2. Usuń cały obiekt razem z przecinkiem

**Przed usunięciem:**
```javascript
{
    before: 'https://picsum.photos/400/400?random=3',
    after: 'https://picsum.photos/400/400?random=4',
    format: 'square'
},
{
    before: 'https://picsum.photos/400/500?random=5',  // <- Ten chcemy usunąć
    after: 'https://picsum.photos/400/500?random=6',
    format: 'portrait'
},
```

**Po usunięciu:**
```javascript
{
    before: 'https://picsum.photos/400/400?random=3',
    after: 'https://picsum.photos/400/400?random=4',
    format: 'square'
},
```

### Metoda 2: Wykomentowanie (tymczasowe ukrycie)
Jeśli chcesz tymczasowo ukryć zdjęcie:
```javascript
// {
//     before: 'https://picsum.photos/400/500?random=5',
//     after: 'https://picsum.photos/400/500?random=6',
//     format: 'portrait'
// },
```

---

## 🔄 Jak zmienić kolejność zdjęć

Po prostu przenieś cały obiekt w inne miejsce w tablicy `galleryData`.

**Przykład przeniesienia na początek:**
```javascript
const galleryData = [
    // Przeniesiony wpis na początek:
    {
        before: 'https://www.hair-estetic.com/featured-before.jpg',
        after: 'https://www.hair-estetic.com/featured-after.jpg',
        format: 'landscape'
    },
    // Reszta wpisów...
    {
        before: 'https://www.hair-estetic.com/before1.jpg',
        after: 'https://www.hair-estetic.com/after1.jpg',
        format: 'portrait'
    }
];
```

---

## 🖼️ Formaty zdjęć

Galeria obsługuje 3 formaty wyświetlania:

### `portrait` (pionowy)
- Proporcje: 4:5
- Najlepsze dla: zdjęć włosów w pionie, portretów

### `landscape` (poziomy)
- Proporcje: 16:9
- Zajmuje 2 kolumny na dużych ekranach
- Najlepsze dla: szerokich ujęć, porównań side-by-side

### `square` (kwadratowy)
- Proporcje: 1:1
- Najlepsze dla: zdjęć Instagram, zbliżeń

---

## 🔧 Rozwiązywanie problemów

### Problem: Zdjęcia się nie wyświetlają
**Sprawdź:**
- ✅ Czy URL zdjęcia jest poprawny (sprawdź w przeglądarce)
- ✅ Czy nie brakuje apostrofów `'` wokół adresu
- ✅ Czy jest przecinek po każdym obiekcie (oprócz ostatniego)

### Problem: Galeria się nie ładuje (biały ekran)
**Prawdopodobnie błąd składni JavaScript:**
- ✅ Sprawdź czy wszystkie nawiasy `{}` są zamknięte
- ✅ Sprawdź czy wszystkie apostrofy `'` są w parach
- ✅ Sprawdź przecinki między obiektami
- ✅ Upewnij się, że ostatni wpis NIE MA przecinka

### Problem: Różnice między wersją PL i EN
**Pamiętaj:**
- ⚠️ Zawsze wprowadzaj zmiany w OBU plikach
- ⚠️ Zachowaj tę samą kolejność zdjęć w obu wersjach

---

## 💡 Wskazówki

1. **Testuj lokalnie** - otwórz plik HTML w przeglądarce przed wgraniem na serwer
2. **Rób kopie zapasowe** - przed większymi zmianami skopiuj plik
3. **Używaj narzędzi deweloperskich** - F12 w przeglądarce pokaże błędy
4. **Optymalizuj zdjęcia** - używaj narzędzi do kompresji (np. TinyPNG)
5. **Zachowaj spójność** - używaj podobnych proporcji dla zdjęć PRZED i PO

---

## 📞 Potrzebujesz pomocy?

Jeśli napotkasz problemy:
1. Sprawdź konsolę przeglądarki (F12 → Console)
2. Porównaj swoją składnię z przykładami powyżej
3. Upewnij się, że edytujesz właściwy plik
4. W razie wątpliwości - przywróć kopię zapasową

---

## 🎨 Struktura kodu (dla zaawansowanych)

### Gdzie znajdują się kluczowe elementy:

**Dane galerii:** Linia ~759
```javascript
const galleryData = [...]
```

**Liczba zdjęć na stronę:** Linia ~852
```javascript
const ITEMS_PER_PAGE = 15;
```

**Style CSS:** Linie 16-696
- Kolory: linie 17-24 (zmienne CSS)
- Układ galerii: linie 216-252
- Modal (pełny widok): linie 369-525

**Logika JavaScript:** Linie 757-1194
- Animacja przesuwania: linie 906-997
- Obsługa modala: linie 1038-1087
- Paginacja: linie 855-903

---

*Ostatnia aktualizacja: Październik 2025*