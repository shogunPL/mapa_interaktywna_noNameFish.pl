# mapa_interaktywna_noNameFish.pl

To repozytorium jest używane także jako źródło automatycznych aktualizacji programu RF4 Map Overlay.

## Publikowanie nowej wersji

1. Zmień numer w pliku `VERSION`, np. z `1.0.0` na `1.0.1`.
2. Uruchom `build_release.bat` w katalogu projektu.
3. Skrypt utworzy w folderze `release` dwa pliki:
   - `RF4MapOverlay_Update.zip`
   - `RF4MapOverlay_Update.zip.sha256`
4. Na GitHubie utwórz nowy Release z tagiem zgodnym z wersją, np. `v1.0.1`.
5. Do Release wrzuć oba pliki dokładnie pod tymi nazwami i opublikuj Release.

Program sprawdza najnowszy opublikowany Release pod adresem API tego repozytorium. Jeśli numer wersji jest wyższy od wersji zainstalowanej, użytkownik dostaje pytanie o pobranie i instalację aktualizacji.

Updater sprawdza SHA-256 pobranej paczki przed instalacją i nie nadpisuje katalogów danych użytkownika `zapisy` ani `Mapy_RF4`.
