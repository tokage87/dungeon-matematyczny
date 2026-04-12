# Dungeon Matematyczny — Propozycje Nowych Funkcji

## Analiza Projektu

**Dungeon Matematyczny** to edukacyjna gra dungeon-crawler w HTML/CSS/JS, stworzona dla ucznia klasy 4 (Szymon M.) jako pomoc w przygotowaniach do egzaminu z matematyki.

### Obecne funkcje:
- 3-piętrowy dungeon z rozgałęzioną mapą pokoi (canvas)
- System walki turowej — rozwiązywanie zadań matematycznych jako ataki
- 12+ typów potworów z pixel-artowymi sprite'ami i mechaniką odporności
- 3 poziomy trudności ataków (lekki/mocny/potężny) z różnymi kategoriami matematyki
- Kategorie: obliczenia, brakujące liczby, kolejność działań, działania pisemne, ułamki, geometria, zapis słowny, zadania z treścią, oś liczbowa, dzielenie pisemne, quiz Roblox Studio
- Sklep, questy z NPC, ulepszenia ekwipunku (miecz, zbroja, tarcza, buty)
- Kreator postaci z personalizacją wyglądu
- Proceduralny dźwięk, zapis/wczytywanie przez localStorage, timer i ranking
- Wybór kategorii i tryb ćwiczeń
- Walki z bossami z rotacyjną odpornością

---

## Propozycja 1: System Osiągnięć (Achievement System)

System odznak/trofeów nagradzający za osiągnięcie kamieni milowych:

### Przykładowe osiągnięcia:
| Odznaka | Nazwa | Warunek |
|---------|-------|---------|
| ⭐ | **Bezbłędny** | Oczyść pokój bez żadnego błędu |
| ⚡ | **Speedrunner** | Pokonaj piętro w mniej niż 3 minuty |
| 🧮 | **Matematyk** | Odpowiedz poprawnie na 50 zadań łącznie |
| 💎 | **Kolekcjoner** | W pełni ulepsz cały ekwipunek (4 sloty) |
| 🏆 | **Pogromca Bossów** | Pokonaj wszystkie 3 bossy |
| 🛡️ | **Nieustraszony** | Pokonaj bossa nie tracąc ani jednego serca |
| 🔥 | **Seria Ognia** | Odpowiedz poprawnie 10 razy z rzędu |
| 📚 | **Wszechstronny** | Rozwiąż co najmniej 5 zadań z każdej kategorii |

### Implementacja:
- Odznaki wyświetlane na ekranie tytułowym i w panelu bohatera
- Przechowywane w `localStorage`
- Powiadomienie popup przy zdobyciu nowej odznaki
- Dodaje długoterminową motywację i powtarzalność gry

---

## Propozycja 2: Panel Statystyk (Statistics & Weakness Tracker)

Ekran dostępny z menu głównego / HUD pokazujący postępy w nauce:

### Zawartość:
- **Liczba zadań** — ile prób i ile poprawnych odpowiedzi per kategoria
- **Procent trafień** — np. "Ułamki: 62%", "Obliczenia: 91%"
- **Wykres słupkowy** — wizualizacja wyników per kategoria
- **Rekomendacja** — "Potrzebujesz więcej ćwiczeń z: Ułamki, Zapis słowny"
- **Historia sesji** — wyniki z ostatnich 5 gier

### Implementacja:
- Dane zbierane w `Game.stats` i zapisywane w `localStorage`
- Nowy panel UI z wykresem canvas
- Przycisk "Statystyki" na ekranie tytułowym
- Bezpośrednio przydatne do przygotowań do egzaminu — wskazuje słabe punkty

---

## Propozycja 3: Codzienne Wyzwanie (Daily Challenge)

Specjalny tryb dostępny z ekranu tytułowego:

### Mechanika:
- **Mini-dungeon** (5 pokoi + boss) generowany z seeda opartego na dacie
- Ten sam układ dla wszystkich graczy danego dnia
- **Nagroda bonusowa** za ukończenie (dodatkowe złoto/XP)
- **Licznik serii** — za kolejne dni ukończeń:
  - 3 dni z rzędu → bonus mikstura
  - 7 dni z rzędu → specjalna odznaka
  - 14 dni z rzędu → unikalny element kosmetyczny
- **Lokalny ranking dzienny** — najlepszy czas danego dnia

### Implementacja:
- Seed z daty: `Math.seedrandom(new Date().toDateString())`
- Nowy przycisk "Wyzwanie Dnia" na ekranie tytułowym
- Zapis serii w `localStorage` z datami
- Zachęca do codziennego ćwiczenia — kluczowe przed egzaminem
- Mechanika serii buduje nawyk regularnej nauki
