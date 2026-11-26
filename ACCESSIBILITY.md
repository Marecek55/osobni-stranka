# Zpráva o přístupnosti

Příklady řádků nahraďte vlastními výsledky. Zapište alespoň tři skutečné nálezy
a u každého hash commitu, který ho opravil (najdete ho v `git log --oneline`).

## Výsledky nástrojů

| Nástroj | Před opravami | Po opravách |
| --- | --- | --- |
| Lighthouse (Accessibility) | 100/100 | 100/100 |
| WAVE (Errors a Contrast Errors) | 0 chyb | 0 chyb |
| Test klávesnicí | Funguje | Funguje |

## Nalezené problémy a jejich opravy

| Problém | Jak jsem ho našel | Oprava (commit) | Kritérium WCAG |
| --- | --- | --- | --- |
| Malá výška odkazů | DevTools | `fe9e788` | 2.5.8 |
| Přepisování barvy fokusu | Kontrola CSS | `0563628` | 2.4.7 |
| Nedokoalý popis obrázku | Kontrola alt textu | `2964a24` | 1.1.1 |

## Test media rules

| Nastavení | Co jsem při emulaci viděl | V pořádku |
| --- | --- | --- |
| prefers-color-scheme: dark | Tmavé pozadí a světlý text. | Ano |
| prefers-contrast: more | Velmi viditelné rámečky a větší kontrast. | Ano |
| prefers-reduced-motion: reduce | Animace a přechody jsou vypnuté. | Ano |
| prefers-reduced-transparency: reduce | Karty nejsou průhledné. | Ano |
| forced-colors: active | Viditelné rámečky a fokus. | Ano |
| dark + more | Černé pozadí a bílý text. | Ano |

## Kritéria WCAG 2.2 úrovně A a AA

Specifikace: https://www.w3.org/TR/WCAG22/ (kritérium najdete podle čísla).
Úrovně A a AA mají dohromady 55 kritérií (31 úrovně A a 24 úrovně AA). Kritérium
4.1.1 Parsing bylo ve verzi 2.2 odstraněno, proto v tabulce není.

U každého kritéria nahraďte TODO. Ve sloupci Stav ponechte jedno ze tří slov:

- **Splněno**: do posledního sloupce napište, kde a jak (například „všechny obrázky mají alt“).
- **Nevztahuje se**: do posledního sloupce napište, proč (například „na stránce není video“).
- **Nesplněno**: kritérium opravte a stav změňte. V odevzdané verzi nesmí zůstat žádné
  Nesplněno ani TODO.

Kritéria označená „nové“ přibyla ve verzi 2.2.

### 1 Perceivable (vnímatelnost)

| Kritérium | Název | Úroveň | Stav | Kde a jak / proč ne |
| --- | --- | --- | --- | --- |
| 1.1.1 | Non-text Content | A | Splněno | Všechny obrázky mají alt. |
| 1.2.1 | Audio-only and Video-only (Prerecorded) | A | Nevztahuje se | Na stránce není zvuk ani video. |
| 1.2.2 | Captions (Prerecorded) | A | Nevztahuje se | Na stránce není video. |
| 1.2.3 | Audio Description or Media Alternative (Prerecorded) | A | Nevztahuje se | Na stránce není video. |
| 1.2.4 | Captions (Live) | AA | Nevztahuje se | Na stránce není živé vysílání. |
| 1.2.5 | Audio Description (Prerecorded) | AA | Nevztahuje se | Na stránce není video. |
| 1.3.1 | Info and Relationships | A | Splněno | Správné nadpisy, seznam a tabulka. |
| 1.3.2 | Meaningful Sequence | A | Splněno | Správné pořadí obsahu. |
| 1.3.3 | Sensory Characteristics | A | Nevztahuje se | Na stránce nejsou takové pokyny. |
| 1.3.4 | Orientation | AA | Splněno | Funguje na výšku i na šířku. |
| 1.3.5 | Identify Input Purpose | AA | Nevztahuje se | Na stránce nejsou formuláře. |
| 1.4.1 | Use of Color | A | Splněno | Odkazy jsou podtržené. |
| 1.4.2 | Audio Control | A | Nevztahuje se | Na stránce není zvuk. |
| 1.4.3 | Contrast (Minimum) | AA | Splněno | WAVE nenašel chyby. |
| 1.4.4 | Resize Text | AA | Splněno | Při 200 % se nic neztratilo. |
| 1.4.5 | Images of Text | AA | Splněno | Text je napsaný v HTML. |
| 1.4.10 | Reflow | AA | Splněno | Při 400 % se nic neztratilo. |
| 1.4.11 | Non-text Contrast | AA | Splněno | Rámeček fokusu je dobře vidět. |
| 1.4.12 | Text Spacing | AA | Splněno | Po změně rozestupů se text nepřekrývá. |
| 1.4.13 | Content on Hover or Focus | AA | Nevztahuje se | Při najetí se nezobrazuje další obsah. |

### 2 Operable (ovladatelnost)

| Kritérium | Název | Úroveň | Stav | Kde a jak / proč ne |
| --- | --- | --- | --- | --- |
| 2.1.1 | Keyboard | A | Splněno | Ovládání klávesnicí funguje. |
| 2.1.2 | No Keyboard Trap | A | Splněno | Nikde se nezasekává. |
| 2.1.4 | Character Key Shortcuts | A | Nevztahuje se | Nejsou vlastní klávesové zkratky. |
| 2.2.1 | Timing Adjustable | A | Nevztahuje se | Není časový limit. |
| 2.2.2 | Pause, Stop, Hide | A | Nevztahuje se | Animace trvá jen 0,5 sekundy. |
| 2.3.1 | Three Flashes or Below Threshold | A | Splněno | Nic nebliká. |
| 2.4.1 | Bypass Blocks | A | Splněno | Funguje odkaz Přejít na obsah. |
| 2.4.2 | Page Titled | A | Splněno | Stránka má titulek. |
| 2.4.3 | Focus Order | A | Splněno | Tab prochází odkazy ve správném pořadí. |
| 2.4.4 | Link Purpose (In Context) | A | Splněno | Odkazy mají jasné názvy. |
| 2.4.5 | Multiple Ways | AA | Nevztahuje se | Web má pouze jednu stránku. |
| 2.4.6 | Headings and Labels | AA | Splněno | Nadpisy odpovídají obsahu. |
| 2.4.7 | Focus Visible | AA | Splněno | Při stisknutí Tab je vidět rámeček. |
| 2.4.11 | Focus Not Obscured (Minimum) (nové) | AA | Splněno | Vybraný odkaz není zakrytý. |
| 2.5.1 | Pointer Gestures | A | Nevztahuje se | Nejsou použita gesta. |
| 2.5.2 | Pointer Cancellation | A | Splněno | Odkazy fungují běžným kliknutím. |
| 2.5.3 | Label in Name | A | Splněno | Názvy odkazů odpovídají textu. |
| 2.5.4 | Motion Actuation | A | Nevztahuje se | Stránka se neovládá pohybem zařízení. |
| 2.5.7 | Dragging Movements (nové) | AA | Nevztahuje se | Není použito přetahování. |
| 2.5.8 | Target Size (Minimum) (nové) | AA | Splněno | Odkazy mají dostatečnou velikost. |
### 3 Understandable (srozumitelnost)

| Kritérium | Název | Úroveň | Stav | Kde a jak / proč ne |
| --- | --- | --- | --- | --- |
| 3.1.1 | Language of Page | A | Splněno | Je nastaven. |
| 3.1.2 | Language of Parts | AA | Nevztahuje se | Cizí názvy jsou pouze názvy her. |
| 3.2.1 | On Focus | A | Splněno | Při zaostření se nic samo nemění. |
| 3.2.2 | On Input | A | Nevztahuje se | Na stránce nejsou formuláře. |
| 3.2.3 | Consistent Navigation | AA | Nevztahuje se | Web má pouze jednu stránku. |
| 3.2.4 | Consistent Identification | AA | Nevztahuje se | Nejsou opakované ovládací prvky na více stránkách. |
| 3.2.6 | Consistent Help (nové) | A | Nevztahuje se | Web má pouze jednu stránku. |
| 3.3.1 | Error Identification | A | Nevztahuje se | Na stránce nejsou formuláře. |
| 3.3.2 | Labels or Instructions | A | Nevztahuje se | Nejsou vstupní pole. |
| 3.3.3 | Error Suggestion | AA | Nevztahuje se | Na stránce nejsou formuláře. |
| 3.3.4 | Error Prevention (Legal, Financial, Data) | AA | Nevztahuje se | Na stránce se neodesílají údaje. |
| 3.3.7 | Redundant Entry (nové) | A | Nevztahuje se | Nezadávají se žádné údaje. |
| 3.3.8 | Accessible Authentication (Minimum) (nové) | AA | Nevztahuje se | Na stránce není přihlašování. |

### 4 Robust (robustnost)

| Kritérium | Název | Úroveň | Stav | Kde a jak / proč ne |
| --- | --- | --- | --- | --- |
| 4.1.2 | Name, Role, Value | A | Splněno | Byly použity správné HTML prvky. |
| 4.1.3 | Status Messages | AA | Nevztahuje se | Na stránce nejsou stavové zprávy. |
