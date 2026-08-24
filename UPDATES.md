# NNF MAP — automatyczne aktualizacje

Repozytorium aktualizacji jest **publiczne**. Użytkownik programu nie potrzebuje żadnego tokenu GitHub ani konfiguracji dostępu.

Aktualna wersja bazowa: **1.0.0**.

Program sprawdza najnowszy **GitHub Release** przy uruchomieniu, co 30 minut podczas pracy oraz po ręcznym kliknięciu `Sprawdź update`.

Dla wersji `X.Y.Z` release powinien mieć tag `vX.Y.Z`.

Preferowane pliki aktualizacji:

- `NNF_MAP_Patch_vX.Y.Z_x64.exe`
- `NNF_MAP_Patch_vX.Y.Z_x64.exe.sha256`

Updater obsługuje również zgodny fallback:

- `NNF_MAP_Setup_vX.Y.Z_x64.exe`
- `NNF_MAP_Setup_vX.Y.Z_x64.exe.sha256`

Program porównuje wersję z najnowszym GitHub Release, pobiera patch z publicznego assetu, weryfikuje SHA-256 i uruchamia Inno Setup w trybie aktualizacji. Dane użytkownika z `Dokumenty\NNF MAP` pozostają bez zmian.

Workflow `.github/workflows/release.yml` po tagu `vX.Y.Z` może automatycznie zbudować i opublikować patch.
