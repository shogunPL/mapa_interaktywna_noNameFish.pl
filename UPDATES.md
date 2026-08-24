# NNF MAP — automatyczne aktualizacje

Repozytorium aktualizacji jest **publiczne**. Użytkownik programu nie potrzebuje żadnego tokenu GitHub ani konfiguracji dostępu.

Aktualna wersja bazowa: **1.0.0**.

Program sprawdza najnowszy **GitHub Release** przy uruchomieniu, co 30 minut podczas pracy oraz po ręcznym kliknięciu `Sprawdź update`.

Dla wersji `X.Y.Z` release powinien mieć tag `vX.Y.Z`.

Build tworzy tylko jeden pakiet EXE. Ten sam instalator służy do czystej instalacji i do aktualizacji istniejącej wersji:

- `NNF_MAP_Setup_vX.Y.Z_x64.exe`
- `NNF_MAP_Setup_vX.Y.Z_x64.exe.sha256`

Nie jest tworzona druga kopia `NNF_MAP_Patch_...`, ponieważ byłaby binarnie tym samym instalatorem. Inno Setup rozpoznaje istniejącą instalację po stałym `AppId` i wykonuje aktualizację na miejscu.

Program porównuje wersję z najnowszym GitHub Release, pobiera instalator z publicznego assetu, weryfikuje SHA-256 i uruchamia Inno Setup w trybie aktualizacji. Dane użytkownika z `Dokumenty\NNF MAP` pozostają bez zmian.

Workflow `.github/workflows/release.yml` po tagu `vX.Y.Z` automatycznie buduje i publikuje ten jeden instalator oraz jego plik SHA-256.
