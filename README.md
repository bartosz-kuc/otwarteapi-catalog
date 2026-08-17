# otwarteapi-catalog

Publiczne dane katalogu stojące za [otwarteAPI.pl](https://otwarteapi.pl) —
katalogu publicznych API rządowych z całego świata (Polska, Unia Europejska
i kraje z 6 kontynentów — 32 jurysdykcje), opisanych tak by mogły być
odkrywane i wywoływane przez agentów AI oraz ludzi.

## Co to jest

`ai-catalog.json` w formacie **ARD (Agent Resource Directory)** — jeden
maszynowo czytelny plik opisujący każde API: nazwę, opis, endpoint,
wymagany klucz/autoryzację, jurysdykcję (kod kraju, `EU` lub `INT`), tagi i
przykładowe zapytania. Ten sam plik serwuje sama strona pod
[otwarteapi.pl/.well-known/ai-catalog.json](https://otwarteapi.pl/.well-known/ai-catalog.json).

## Kto to prowadzi

Bartosz Kuć (ten sam autor co [skanfirmy.pl](https://skanfirmy.pl)),
prywatny projekt non-profit. Kontakt: firma@bartosza.pl. Więcej na
[otwarteapi.pl/o-projekcie](https://otwarteapi.pl/o-projekcie).

## To jest lustro, nie źródło prawdy

To repozytorium to **kopia** stanu produkcyjnego, aktualizowana ręcznie.
Zaakceptowane PR-y i issue trafiają najpierw tutaj do przeglądu, a
dopiero potem są ręcznie przenoszone do prywatnego repo, które faktycznie
zasila stronę produkcyjną — nie ma automatycznej synchronizacji w żadną
stronę.

## Jak zgłosić nowe API lub poprawkę

1. **Nowe API**: otwórz issue albo PR dodający wpis do `entries[]` w
   `ai-catalog.json`. Wymagane pola: `identifier` (URN, np.
   `urn:air:otwarteapi.pl:api:twoj-slug`), `displayName`, `description`,
   `url` (dokumentacja techniczna), `type`, `jurisdiction` (`PL`/`EU`/kod
   kraju), `tags`, `metadata.auth` (`brak` jeśli bez klucza), oraz
   `representativeQueries` (2-3 przykładowe pytania, po jednym w
   naturalnym języku). API musi być **publiczne, oficjalne** (rządowe,
   samorządowe lub międzynarodowej instytucji publicznej) i mieć żywą,
   działającą dokumentację.
2. **Poprawka istniejącego wpisu** (zmieniony endpoint, nieaktualny opis,
   błędna jurysdykcja): PR edytujący konkretny wpis, z krótkim
   uzasadnieniem w opisie PR.
3. Każdy PR jest ręcznie recenzowany pod kątem poprawności i tego, czy
   API faktycznie działa (żywy `curl`/test), zanim trafi do wersji
   produkcyjnej.

## Licencja

MIT — patrz [LICENSE](LICENSE). Same dane API pozostają własnością i na
licencji swoich pierwotnych źródeł (rządów/instytucji UE); ten plik tylko
je katalogizuje i linkuje do oficjalnej dokumentacji.
