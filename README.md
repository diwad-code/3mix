# 3mix

`3mix` jest repozytorium porządkującym trzy powiązane projekty użytkownika:

- `SpaceshipGame` — gra o poszukiwaniu życia w kosmosie.
- `github-and-vscode-vibecoding-config` — konfiguracja środowiska pracy, VS Code, GitHub i składników potrzebnych do pracy na Windows.
- `bmad-module-game-dev-studio` — moduł/proces do projektowania architektury, mechanik i fabuły gry.

To repo ma pomóc kolejnemu agentowi AI zrozumieć, co się stało, jakie są możliwe kierunki uporządkowania projektu i jakie decyzje trzeba podjąć przed dalszymi zmianami.

## Najważniejsze dokumenty

- [`docs/ai-agent-handoff.md`](docs/ai-agent-handoff.md) — główny dokument startowy dla kolejnego agenta AI.
- [`docs/repo-map.md`](docs/repo-map.md) — mapa katalogów i obecnego stanu repo.
- [`docs/recovery-options.md`](docs/recovery-options.md) — neutralna lista możliwych sposobów uporządkowania projektu.
- [`docs/next-agent-checklist.md`](docs/next-agent-checklist.md) — checklista pierwszych działań dla kolejnego agenta.

## Aktualny stan w skrócie

W katalogu głównym znajdują się trzy wpisy wyglądające jak osobne projekty. W historii Gita są zapisane jako `gitlink`/submodule, ale w repo nie ma pliku `.gitmodules`. To oznacza, że obecnie nie da się jednoznacznie odtworzyć adresów źródłowych tych modułów tylko z tego repozytorium.

Ten stan nie musi oznaczać utraty pracy, ale wymaga decyzji: czy `3mix` ma być hubem dokumentacyjnym, monorepo, repo z submodule, czy czymś innym.
