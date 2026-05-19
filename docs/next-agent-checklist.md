# Checklista dla kolejnego agenta AI

## 1. Zacznij od rozpoznania

- [ ] Przeczytaj `README.md`.
- [ ] Przeczytaj `docs/ai-agent-handoff.md`.
- [ ] Przeczytaj `docs/repo-map.md`.
- [ ] Przeczytaj `docs/recovery-options.md`.
- [ ] Sprawdź `git status`.
- [ ] Sprawdź `git ls-tree HEAD`.
- [ ] Nie zakładaj, że submodule są poprawnie skonfigurowane.

## 2. Ustal z użytkownikiem brakujące informacje

- [ ] Zapytaj, czy trzy projekty istnieją jako osobne repozytoria.
- [ ] Jeśli tak, poproś o URL-e repozytoriów.
- [ ] Zapytaj, czy użytkownik chce jedno repo, kilka repo, czy repo-hub.
- [ ] Zapytaj, czy historia commitów podprojektów ma zostać zachowana.
- [ ] Zapytaj, czy priorytetem jest prostota, porządek techniczny, czy praca z agentami AI.

## 3. Nie rób zmian strukturalnych przed decyzją

- [ ] Nie usuwaj katalogów projektów.
- [ ] Nie twórz `.gitmodules` z wymyślonymi URL-ami.
- [ ] Nie zamieniaj submodule na zwykłe katalogi bez zgody.
- [ ] Nie przenoś kodu między projektami bez planu.
- [ ] Nie przepisuj historii Gita.

## 4. Po decyzji użytkownika przygotuj plan

- [ ] Opisz wybraną opcję własnymi słowami.
- [ ] Wypisz małe kroki po kolei.
- [ ] Oddziel działania bezpieczne od ryzykownych.
- [ ] Wskaż, które pliki zostaną zmienione.
- [ ] Poproś o potwierdzenie, jeśli zmiana dotyczy struktury repo.

## 5. Po zmianach

- [ ] Zaktualizuj README.
- [ ] Zaktualizuj dokumentację w `docs/`.
- [ ] Sprawdź `git status`.
- [ ] Jeśli zmieniono konfigurację repo, sprawdź odpowiednie komendy Gita.
- [ ] Zostaw jasny opis dla następnego agenta.
