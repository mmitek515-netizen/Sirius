# Sirius

Repozytorium jest na etapie inicjalizacji. Zakres wskazany w [Issue #1](https://github.com/mmitek515-netizen/Sirius/issues/1) obejmuje panel GUI i integrację oryginalnych agentów Aria, Alex, Astyria i Aurelius. Nie znaleziono kodu źródłowego, backendu, kontraktów API, konfiguracji zależności, testów ani workflow CI. Nie ma podstaw, aby zakładać, czym są źródłowe systemy agentów ani jak się z nimi uwierzytelniać.

## Panel demonstracyjny

`index.html` to samodzielny, responsywny panel statusu — nie aplikacja zintegrowana z agentami. Pokazuje cztery kanały agentów i kanał „Wszyscy”; wszystkie źródła mają jawny stan `not_connected`, a obsługa zadań jest `blocked`. Nie wysyła żądań, nie pokazuje fikcyjnych odpowiedzi lub zadań i nie przechowuje poświadczeń.

Aby wyświetlić panel lokalnie:

```sh
python3 -m http.server 8000
```

Otwórz `http://localhost:8000`. Repozytorium nie zawiera zdefiniowanych komend build, lint ani test.

## Audyt, ryzyka i blokery

- Jedyny zastany plik projektu przed dodaniem panelu to ten README; nie ma znanego stacku, istniejącej aplikacji ani funkcji, którą można bezpiecznie reaktywować.
- Wymagane endpointy i tożsamości oryginalnych agentów, ich kontrakty `capabilities`, uwierzytelnianie, odbiór zdarzeń oraz wspierane operacje nie zostały udostępnione. Integracja API, historia, heartbeat, kolejka i komunikacja dwustronna pozostają zablokowane.
- Nie skonfigurowano uwierzytelnionej GitHub App/tokena ograniczonego do repo ani połączeń MCP, GPT Actions, Codex/OpenAI. Nie należy traktować konfiguracji lub profili jako działających workerów.
- Brak workflow CI i testów. Uruchomienie lokalnego panelu nie potwierdza testu w prywatnym Codespace; Codespace, testy E2E i ich logi nie są dostępne w tym audycie.
- Nie wykonano zakupów, checkoutu ani pobierania płatnych zasobów. Wstępnie odnaleziono [Dastone — Figma Admin & Dashboard Template od Mannat-Themes w ThemeForest](https://themeforest.net/item/dastone-figma-admin-dashboard-template/65079544) oraz [podgląd zrzutów](https://themeforest.net/item/dastone-figma-admin-dashboard-template/screenshots/65079544). Dostępność cyfrowa, cena brutto i waluta, podatki, warunki licencji, użycie w wielu repozytoriach, odnowienie oraz natychmiastowa dostawa nie zostały niezależnie potwierdzone (strona dostawcy była niedostępna z tego środowiska). To nie jest zatwierdzona ani gotowa do zakupu propozycja; zakup pozostaje `awaiting_owner_approval` i wymaga najpierw zweryfikowania wszystkich tych warunków oraz zgodności z wybranym stackiem. Bezpłatną alternatywą jest obecny własny panel bez zewnętrznych zasobów.

## Wymagane decyzje / następny krok

1. Właściciel określa docelowy stack oraz dostarcza lub wskazuje autoryzowane API źródłowych agentów i ich dokumentację, bez umieszczania sekretów w repozytorium.
2. Właściciel udostępnia prywatny Codespace do wymaganych testów E2E i widoków mobilnych.
3. Przed zakupem designu należy przedstawić zweryfikowaną ofertę z pełnym kosztem brutto, licencją i terminem dostawy oraz uzyskać osobną, jednoznaczną zgodę na konkretny produkt i kwotę.
4. Po udostępnieniu tych zależności można wdrożyć backend, połączenia, testy i produkcyjny interfejs. Do tego czasu nie deklarować ukończenia integracji ani odbioru projektu.
