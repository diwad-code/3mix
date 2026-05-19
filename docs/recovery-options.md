# Opcje uporządkowania projektu

Ten dokument opisuje możliwe kierunki naprawy/organizacji repozytorium `3mix`. Nie wskazuje jednej najlepszej opcji. Wybór zależy od tego, jak użytkownik chce pracować dalej.

## Opcja A — `3mix` jako hub dokumentacyjny

`3mix` zawiera głównie dokumentację, mapę projektu i instrukcje. Trzy projekty pozostają osobnymi repozytoriami poza tym repo.

Możliwe działania:

- zostawić w `3mix` dokumenty wyjaśniające relacje między projektami;
- dodać linki do właściwych repozytoriów;
- usunąć lub naprawić niekompletne wpisy submodule po decyzji użytkownika;
- utrzymywać `3mix` jako panel startowy dla człowieka i agentów AI.

Zalety:

- prosta mentalnie struktura;
- mało ryzyka przypadkowego wymieszania kodu;
- dobre miejsce na instrukcje dla AI.

Ryzyka/pytania:

- trzeba osobno zarządzać trzema repozytoriami;
- trzeba wiedzieć, gdzie są właściwe URL-e projektów.

## Opcja B — poprawne submodule

`3mix` pozostaje repozytorium nadrzędnym, a trzy projekty są poprawnie podpięte jako submodule.

Możliwe działania:

- ustalić URL każdego podrepozytorium;
- odtworzyć plik `.gitmodules`;
- zsynchronizować wpisy submodule z commitami zapisanymi w `3mix`;
- dodać instrukcję klonowania z `--recurse-submodules`.

Zalety:

- każdy projekt zachowuje własną historię;
- repo nadrzędne może wskazywać konkretne wersje trzech projektów;
- dobre dla projektów rozwijanych niezależnie.

Ryzyka/pytania:

- submodule bywają trudniejsze dla początkujących;
- brak `.gitmodules` trzeba naprawić ostrożnie;
- potrzebne są prawdziwe URL-e repozytoriów.

## Opcja C — monorepo

Wszystkie trzy projekty stają się zwykłymi katalogami w jednym repozytorium `3mix`.

Możliwe działania:

- usunąć zależność od submodule;
- przenieść realną zawartość projektów do katalogów;
- uporządkować wspólny README i dokumentację;
- dodać wspólne zasady pracy dla kodu, konfiguracji i projektowania gry.

Zalety:

- wszystko jest w jednym miejscu;
- łatwiejsze dla jednego użytkownika lub jednego agenta AI;
- prostsze klonowanie i edycja.

Ryzyka/pytania:

- można utracić osobne historie projektów, jeśli migracja będzie zrobiona nieostrożnie;
- większe repo może być mniej czytelne;
- trzeba zdecydować, czy historia podprojektów ma być zachowana.

## Opcja D — repo startowe z instrukcjami dla agentów

`3mix` pełni rolę repozytorium startowego dla AI. Nie musi zawierać całego kodu. Zawiera kontekst, decyzje, checklisty, prompt startowy i linki.

Możliwe działania:

- utrzymywać dokumenty w `docs/`;
- dodać gotowy prompt dla kolejnego agenta;
- dodać mapę decyzji;
- dodać procedurę: „najpierw zapytaj użytkownika o X, potem zrób Y”.

Zalety:

- bardzo dobre dla pracy z wieloma agentami/chattami AI;
- małe ryzyko zmian w kodzie;
- pomaga nie gubić kontekstu.

Ryzyka/pytania:

- kod gry nadal musi mieć własne dobrze opisane miejsce;
- bez linków do repozytoriów agent nie odtworzy brakujących projektów.

## Opcja E — struktura mieszana

Część projektu zostaje w `3mix`, a część pozostaje zewnętrzna.

Przykłady:

- `SpaceshipGame` jako osobne repo, a dokumentacja i konfiguracja w `3mix`;
- `SpaceshipGame` i konfiguracja razem, a moduł projektowy osobno;
- `3mix` jako repo z dokumentacją plus tylko jeden aktywny submodule.

Zalety:

- można dopasować strukturę do faktycznego sposobu pracy;
- nie trzeba podejmować jednej dużej decyzji od razu.

Ryzyka/pytania:

- łatwo stworzyć chaos, jeśli nie będzie mapy repo;
- trzeba jasno opisać, co jest źródłem prawdy dla każdego obszaru.

## Decyzje, które trzeba uzyskać od użytkownika

Przed naprawą struktury kolejny agent powinien zapytać:

1. Czy `SpaceshipGame`, `github-and-vscode-vibecoding-config` i `bmad-module-game-dev-studio` istnieją jako osobne repozytoria na GitHubie?
2. Czy użytkownik chce pracować w jednym repo, czy w kilku repo?
3. Czy historia commitów podprojektów jest ważna?
4. Czy `3mix` ma być miejscem kodu, dokumentacji, czy obu?
5. Czy głównym odbiorcą struktury ma być człowiek, agent AI, czy oba naraz?
