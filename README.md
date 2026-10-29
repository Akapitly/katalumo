# Katalumo — wersja webowa

Zawartość tego folderu to cała strona katalumo.com. Żadnej kompilacji, żadnych zależności.

| Plik | Co to |
|---|---|
| `index.html` | gra (jeden plik, dźwięki i muzyka wszyte) |
| `firebase-config.js` | konfiguracja tablicy wyników; `null` = tablica wyłączona |
| `privacy.html` | strona prywatności (PL/EN), link w tablicy wyników |
| `icon.svg`, `icon-*.png` | ikona karty/urządzenia |
| `og.png` | obrazek podglądu przy wysyłaniu linku |
| `manifest.webmanifest` | pozwala „dodać do ekranu głównego" na telefonie |

## Aktualizacja gry

Nowa wersja = podmiana samego `index.html` (zbudowanego z artifactu bez przycisków testowych). Reszta plików zostaje.

## Publikacja — GitHub → Vercel → domena

1. **GitHub**: nowe repozytorium `katalumo` (publiczne lub prywatne, bez README) → „uploading an existing file" → przeciągnij wszystkie pliki z tego folderu → Commit.
2. **Vercel** (vercel.com, to samo konto co aplikacja Tokio): „Add New → Project" → wybierz repo `katalumo` → Framework: **Other**, nic nie zmieniaj → Deploy. Po minucie gra działa pod `katalumo.vercel.app`.
3. **Domena**: w projekcie Vercel → Settings → Domains → wpisz `katalumo.com` → Add. Vercel pokaże rekordy DNS do ustawienia u rejestratora domeny (zwykle rekord **A** na adres Vercela dla `katalumo.com` i **CNAME** dla `www`). Wpisz dokładnie te wartości, które pokaże Vercel. Propagacja: od kilku minut do kilku godzin; Vercel sam wystawia certyfikat HTTPS.
4. **Firebase → Authentication → Settings → Authorized domains**: dodaj `katalumo.com` i `katalumo.vercel.app` (bez tego logowanie Google nie zadziała).

## itch.io

Zip z tego folderu (bez README) → itch.io → „Create new project" → Kind of project: **HTML** → Upload → zaznacz „This file will be played in the browser" → Embed options: **Click to launch in fullscreen**, **Mobile friendly** włączone. Na itch gra działa w ramce: tablica wyników jest do odczytu, a publikowanie wyniku odsyła na katalumo.com.
