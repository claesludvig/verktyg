# CLAUDE.md

OBS: repot är publikt. Skriv inga personuppgifter, länkar eller fil-ID:n här.

Repot har flera fristående delprojekt. Varje delprojekt har en README och, där arbetet
pågår över flera sessioner, en `ARBETSLAGE.md` med överlämning. Läs den först.

- `bostadsarkiv/` – sökbar källbas om bostadsbyggandet och bostadsfinansieringen 1939–2026
  (riksdagstryck, utredningar, remissvar) för Ludvigs kapitel om kreditpolitiken efter kriget.
  Överlämning: `bostadsarkiv/ARBETSLAGE.md`.
- `valjare/` – väljardatabasen. Överlämning: `valjare/ARBETSLAGE.md`.
- `byggfastighet/`, `marknadspuls/`, `vinstforvantningar/`, `seb-research-digest/`,
  `ing-think-digest/`, `omxs30-yfinance/`, `svensk-politik-digest/`, `veckoanalys/` – automatiska
  datainsamlingar (GitHub Actions) som de schemalagda rutinerna triggar och läser från `main`.

Allt ligger på `main`. Repot flyttades hit från ett äldre repo i november 2026, utan historik.

Skriv på svenska i kod, kommentarer och texter, som i resten av repot.

## Ludvigs skrivstil

- Använd aldrig kolon eller tankestreck (– eller —) i text som skrivs i Ludvigs namn, till exempel
  prognostexter, krönikor och artiklar. Skriv om meningen med punkt, komma eller bisats i stället.

## Att göra-listor – var de finns

| Område | Källa | Hur Claude hittar den |
|--------|-------|-----------------------|
| **Jobb** | Microsoft To Do, exporteras automatiskt via Power Automate som CSV till OneDrive: `Claude/todo-export.csv` | Microsoft 365-kopplingen saknar To Do-behörighet, så läs filen i stället: `sharepoint_search` (query `*`, fileType `csv`), välj `todo-export.csv`, läs med `read_resource` |
| **Privat, studier, bokprojekt** | Google Tasks, exporteras till Google Drive-arket "Google Tasks – export för Claude" | `search_files` på titeln, ladda ner som `text/csv` (`read_file_content` visar bara ett urval av raderna) |

"Jobb" eller "att göra jobbmässigt" betyder alltså To Do-exporten, inte Google Tasks.

### Format på To Do-exporten
Kolumner: `Lista, Uppgift, Status, Viktighet, Forfallodatum, Slutford, Senast_andrad, Anteckningar, Exporterad`
- Status: `notStarted` / `completed`; Viktighet: `normal` / `high`
- Datum är i UTC. Ett förfallodatum som `2026-11-23T23:00:00` betyder **24/11** svensk tid (vintertid: +1 h, sommartid: +2 h).
- Listor (nov 2026): Jobb, Anläggningsprognosen, Media, Struktur för återkommande analys, Tasks (gammal och mest avklarad).
- Kolla kolumnen `Exporterad` så att du vet hur färsk exporten är.
