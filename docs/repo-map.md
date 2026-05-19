# Mapa repozytorium

## Katalog główny

Ścieżka lokalna:

```text
/home/runner/work/3mix/3mix
```

Obecne wpisy w katalogu głównym:

```text
SpaceshipGame
bmad-module-game-dev-studio
github-and-vscode-vibecoding-config
```

## Znaczenie katalogów

### `SpaceshipGame`

Planowana rola: właściwy projekt gry o poszukiwaniu życia w kosmosie.

Prawdopodobne obszary odpowiedzialności:

- mechaniki gry;
- eksploracja kosmosu;
- logika statku;
- system odkrywania życia;
- assety, sceny, UI i gameplay.

### `github-and-vscode-vibecoding-config`

Planowana rola: przygotowanie środowiska pracy.

Prawdopodobne obszary odpowiedzialności:

- konfiguracja VS Code;
- ustawienia GitHub/Copilot;
- instrukcje dla Windows;
- instalacja narzędzi;
- standard pracy lokalnej.

### `bmad-module-game-dev-studio`

Planowana rola: projektowanie gry od strony kreatywno-architektonicznej.

Prawdopodobne obszary odpowiedzialności:

- architektura gry;
- mechaniki;
- fabuła;
- struktura zadań projektowych;
- proces pracy z agentami AI.

## Stan techniczny

Wpisy trzech katalogów są zapisane w Git jako `160000 commit`, czyli gitlink/submodule. Brakuje jednak pliku `.gitmodules`.

Efekt:

- repo zna nazwy katalogów i konkretne commity;
- repo nie zna URL-i, z których ma pobrać zawartość;
- `git submodule status` zgłasza błąd;
- kolejny agent nie powinien zgadywać brakujących URL-i.

## Źródła prawdy do ustalenia

Kolejny agent powinien pomóc użytkownikowi ustalić:

- które repo jest głównym miejscem pracy;
- czy gra ma być rozwijana w `SpaceshipGame` jako osobnym repo;
- czy konfiguracja VS Code ma być używana jako osobny moduł;
- czy moduł game-dev-studio ma być narzędziem projektowym, zależnością, czy dokumentacją;
- czy `3mix` ma tylko łączyć projekty, czy także zawierać ich realną treść.
