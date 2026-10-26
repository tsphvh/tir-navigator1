# TIR Navigator PWA — prototyp iPhone

## Uruchomienie bez Maca

1. Załóż konto GitHub (github.com) na iPhonie.
2. Utwórz publiczne repozytorium np. `tir-navigator` i prześlij do niego pliki z tego archiwum (pliki muszą być w katalogu głównym).
3. W GitHub: **Settings → Pages → Build and deployment → Deploy from a branch → main / (root) → Save**.
4. Po publikacji otwórz adres `https://TWOJ_LOGIN.github.io/tir-navigator/` w Safari na iPhonie.
5. W Safari wybierz **Udostępnij → Dodaj do ekranu początkowego**.
6. Załóż konto HERE developer i utwórz klucz API z uprawnieniami do Geocoding & Search oraz Routing v8. Wklej klucz w aplikacji. Nie umieszczaj klucza w repozytorium.
7. W Safari zezwól na lokalizację, naciśnij „Moja lokalizacja”, wpisz cel i wybierz „Wyznacz trasę TIR”.

## Ważne ograniczenia

- Mapa Leaflet + OpenStreetMap i zapytania HERE wymagają internetu. Service worker buforuje tylko lokalne pliki aplikacji (nie mapy ani trasy).
- Klucz HERE jest podawany w przeglądarce; jest widoczny w żądaniach sieciowych. Do produkcji potrzebny backend-proxy, limity i zabezpieczenia klucza.
- Darmowy limit i warunki HERE zależą od konta; wymagane są właściwe uprawnienia i ewentualne ustawienia CORS.
- To demonstrator wyświetlania trasy, nie pełna nawigacja turn-by-turn; nie ma prowadzenia głosowego, automatycznego reroutingu, korków ani gwarantowanych ograniczeń w całej Europie.
- Profil: 4 m wysokości, 2,55 m szerokości, 16,5 m długości, 40 000 kg masy całkowitej. Naciski osi, towary niebezpieczne i specyficzne przepisy krajowe nie są w tej wersji modelowane.
- Nie polegaj na prototypie przy podejmowaniu decyzji o przejeździe ciężarówką. Zawsze sprawdzaj aktualne oznakowanie i legalność trasy.

## Struktura

- `index.html` — interfejs i mapa Leaflet
- `app.js` — GPS, geokodowanie HERE, routing truck, rysowanie trasy
- `sw.js` — cache podstawowych plików aplikacji
- `manifest.webmanifest` i `icon.svg` — instalacja PWA

## Uwaga techniczna

W razie błędów API sprawdź konfigurację i aktualne parametry HERE Routing API v8. Testów z prawdziwym kluczem HERE nie przeprowadzono.
