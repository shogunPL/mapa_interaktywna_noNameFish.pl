# NNF MAP — aktualizacje

Aktualna wersja bazowa: **1.0.0**.

Automatyczny updater programu korzysta z **GitHub Releases** tego repozytorium.

Dla wersji `X.Y.Z` release powinien mieć tag `vX.Y.Z` i dwa assety:

- `NNF_MAP_Setup_vX.Y.Z_x64.exe`
- `NNF_MAP_Setup_vX.Y.Z_x64.exe.sha256`

Program porównuje wersję z najnowszym GitHub Release, pobiera instalator i przed uruchomieniem weryfikuje jego SHA-256.

Repozytorium jest prywatne, dlatego klient potrzebuje osobnego fine-grained PAT ograniczonego do tego repozytorium i minimalnego uprawnienia **Contents: Read**. Token nie powinien być umieszczany w kodzie, instalatorze ani publicznych plikach.

W źródłach programu znajduje się workflow `.github/workflows/release.yml`, który po wypchnięciu taga `vX.Y.Z` może automatycznie zbudować instalator i utworzyć release.
