# Handoff dla kolejnego agenta AI

## Cel dokumentu

Ten dokument jest przygotowany dla kolejnego agenta AI lub nowego chatu AI, który ma wejść do repozytorium `diwad-code/3mix` i pomóc użytkownikowi uporządkować trzy powiązane projekty.

Nie wybieraj automatycznie jednej ścieżki naprawy. Najpierw przedstaw użytkownikowi opcje i poproś o decyzję, jeśli zmiana wpływa na strukturę repozytoriów.

## Kontekst użytkownika

Użytkownik pracuje nad grą `SpaceshipGame`. Cel gry: poszukiwanie życia w kosmosie.

Powstały trzy osobne obszary pracy:

1. `SpaceshipGame`
   - właściwy projekt gry;
   - powinien zawierać kod, assety, sceny, mechaniki i logikę gry.

2. `github-and-vscode-vibecoding-config`
   - środowisko pracy od zera;
   - konfiguracja VS Code, GitHub, narzędzi, instalacji składników Windows i workflow pracy.

3. `bmad-module-game-dev-studio`
   - moduł/proces do projektowania gry;
   - ma pomagać w architekturze, mechanikach, fabule i zadaniach kreatywno-technicznych.

Użytkownik nie wie, jak te trzy części połączyć w spójny system pracy.

## Co wykryto w repo

W katalogu `/home/runner/work/3mix/3mix` znajdują się trzy katalogi:

- `SpaceshipGame`
- `bmad-module-game-dev-studio`
- `github-and-vscode-vibecoding-config`

Z punktu widzenia Gita są zapisane jako wpisy typu `160000 commit`, czyli gitlink/submodule:

- `SpaceshipGame` → commit `6e1c0a8eea546c73500614f5679fce47e7d5a7aa`
- `bmad-module-game-dev-studio` → commit `7de7811511b174725b214083ecb76631cfa82296`
- `github-and-vscode-vibecoding-config` → commit `b54c449f1c7b156f4785314faec7ded93c5e5296`

Jednocześnie w repo nie ma pliku `.gitmodules`. Komenda `git submodule status` kończy się błędem:

```text
fatal: no submodule mapping found in .gitmodules for path 'SpaceshipGame'
```

To oznacza, że repo pamięta konkretne commity podprojektów, ale nie przechowuje informacji, skąd je pobrać.

## Najważniejszy problem

Repozytorium `3mix` wygląda jak próba połączenia trzech repozytoriów przez submodule, ale konfiguracja submodule jest niekompletna.

Brakuje decyzji projektowej:

- czy trzy projekty mają pozostać osobnymi repozytoriami;
- czy `3mix` ma być tylko dokumentacyjnym hubem;
- czy wszystko ma zostać scalone w jedno monorepo;
- czy należy odbudować poprawne submodule;
- czy repo ma zawierać tylko instrukcje dla agentów i człowieka.

## Czego nie robić bez decyzji użytkownika

Nie wykonuj automatycznie tych działań bez potwierdzenia:

- nie usuwaj katalogów `SpaceshipGame`, `bmad-module-game-dev-studio`, `github-and-vscode-vibecoding-config`;
- nie zamieniaj submodule na zwykłe katalogi bez decyzji;
- nie zakładaj, że jedna struktura jest najlepsza;
- nie przepisuj historii Gita;
- nie próbuj odtwarzać zdalnych URL-i submodule na podstawie zgadywania;
- nie przenoś kodu między projektami bez planu migracji.

## Co można zrobić dalej

Kolejny agent powinien:

1. Sprawdzić, czy użytkownik chce zachować trzy osobne repozytoria.
2. Ustalić, czy istnieją zdalne repozytoria dla trzech projektów.
3. Poprosić użytkownika o URL-e brakujących repozytoriów, jeśli mają być submodule.
4. Przedstawić neutralnie opcje z `docs/recovery-options.md`.
5. Po decyzji użytkownika przygotować mały, bezpieczny plan zmian.
6. Dopiero wtedy zmieniać strukturę repo.

## Docelowy rezultat do ustalenia

Po rozmowie z użytkownikiem powinno być jasne:

- gdzie żyje kod gry;
- gdzie żyje konfiguracja środowiska;
- gdzie żyją dokumenty projektowe/fabularne;
- jak nowy agent AI ma rozpocząć pracę;
- jak człowiek ma uruchomić projekt lokalnie;
- czy `3mix` jest hubem, monorepo, czy repo z submodule.
