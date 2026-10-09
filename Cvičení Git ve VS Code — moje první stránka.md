# Cvičení: Git ve VS Code — moje první stránka

Oct 9, 2026 · @Deck

## Zadání

Vytvoříte jednoduchou webovou stránku a celou dobu u ní budete pracovat s Gitem — výhradně z panelu **Source Control** ve VS Code. Žádné příkazy psát nemusíte.

Na konci cvičení budete mít repozitář s nejméně čtyřmi commity, jednou vytvořenou a sloučenou větví a jednou vrácenou změnou.

Na práci počítejte zhruba 35 minut. Pracujte samostatně, u každého kroku je uvedené, co máte vidět na obrazovce — podle toho poznáte, že jste nic nepřeskočili.

## Krok 1 — Založení repozitáře

1. Vytvořte si na ploše složku `moje-stranka`.
2. Otevřete ji ve VS Code: **File → Open Folder**, vyberte složku.
3. Vlevo klikněte na ikonu **Source Control** (třetí shora, větvička).
4. Klikněte na tlačítko **Initialize Repository**.

**Co máte vidět:** tlačítko Initialize Repository zmizelo a místo něj je prázdný panel s polem na zprávu commitu. Vlevo dole je u názvu větve napsáno `main`.

> Tip: pokud ve složce nic nevidíte, zkontrolujte, že jste otevřeli opravdu složku a ne jen soubor.

## Krok 2 — První commit

1. V Exploreru vytvořte nový soubor `index.html` (ikona listu s plusem).
2. Napište do něj `!` a stiskněte **Enter** — VS Code doplní kostru stránky.
3. Do `<title>` napište své jméno, do `<body>` přidejte `<h1>` s nadpisem.
4. Uložte (**Ctrl + S**).
5. Přepněte se do Source Control. U souboru `index.html` je písmeno **U** (untracked — Git ho ještě nezná).
6. Najeďte na soubor a klikněte na **+** (Stage Changes). Soubor se přesune do sekce *Staged Changes*.
7. Do pole nahoře napište zprávu `první verze stránky` a klikněte na **Commit**.

**Co máte vidět:** seznam změn je prázdný a dole v pruhu je napsáno `main*`. Zpráva commitu je ta vaše, ne „update" nebo prázdná.

> Pozor: zpráva commitu musí dávat smysl i za měsíc. „aaa", „změny" nebo „oprava" se nepočítají.

## Krok 3 — Dva soubory, jeden commit navíc

1. Vytvořte soubor `styles.css` a dejte do něj libovolné pravidlo, třeba `body { background: #f0f0f0; }`.
2. V `index.html` přidejte do `<head>` řádek `<link rel="stylesheet" href="styles.css">`.
3. Uložte oba soubory a podívejte se do Source Control.

Všimněte si písmen vpravo u souborů:

| Písmeno | Význam |
| --- | --- |
| `U` | untracked — soubor je nový, Git ho zatím nesleduje |
| `M` | modified — soubor Git zná a od posledního commitu se změnil |
| `D` | deleted — soubor byl smazán |

4. Klikněte na `index.html`. Otevře se porovnání: vlevo verze z posledního commitu, vpravo vaše současná. Zelené řádky přibyly.
5. Stagujte **oba** soubory a commitněte se zprávou `přidán soubor se styly`.

**Co máte vidět:** v porovnání jste našli přesně ten jeden řádek s `<link>`, který jste přidali.

## Krok 4 — Zkazit to a vrátit zpět

Tohle je ta část, kvůli které se Git používá.

1. V `index.html` smažte celý obsah `<body>`. Uložte.
2. Podívejte se na soubor v Source Control — má `M`. Klikněte na něj a v porovnání uvidíte červeně všechno, co jste smazali.
3. Najeďte na soubor a klikněte na ikonu **↺ (Discard Changes)**. Potvrďte.
4. Vraťte se do souboru.

**Co máte vidět:** obsah je zpátky přesně tak, jak byl v posledním commitu. Seznam změn je prázdný.

**Zamyslete se:** kdyby stejnou věc udělal někdo bez Gitu, jak by svou stránku dostal zpět?

> Discard Changes je nevratné — zahodí práci, která nikdy nebyla v commitu. Proto se commituje často.

## Krok 5 — Větev, sloučení, úklid

Zkusíte barevnou variantu stránky, aniž byste sáhli na funkční verzi.

1. Klikněte vlevo dole na `main`. Nahoře vyberte **Create new branch** a pojmenujte ji `barvy`.
2. Ověřte, že vlevo dole je teď `barvy` — jste na nové větvi.
3. V `styles.css` změňte barvu pozadí a přidejte barvu písma. Uložte, stagujte, commitněte se zprávou `tmavé barevné schéma`.
4. Přepněte se zpět na `main` (vlevo dole → výběr větve). **Podívejte se na `styles.css`** — vaše změny tam nejsou.
5. Zpátky do Source Control: menu **… → Branch → Merge Branch**, vyberte `barvy`.
6. Zkontrolujte `styles.css` — změny jsou tam.
7. Uklidit: **… → Branch → Delete Branch** a vyberte `barvy`.

**Co máte vidět:** vlevo dole je `main`, větev `barvy` už v seznamu není, ale její commit je v historii pořád.

**Zamyslete se:** proč se větev smazala až po merge a ne před ním?

## Bonus — Na GitHub

Pro ty, kdo jsou hotovi dřív. Potřebujete účet na GitHubu.

1. V Source Control klikněte na **Publish Branch**.
2. VS Code se zeptá na přihlášení k GitHubu — povolte to v prohlížeči.
3. Vyberte **Publish to private repository**.
4. Udělejte ještě jednu drobnou změnu, commitněte ji a klikněte na **Sync Changes**.
5. Otevřete si repozitář na githubu.com a najděte svůj poslední commit i se zprávou.

**Co máte vidět:** stejné commity, které máte lokálně, jsou vidět i na webu.

## Kontrolní otázky

Odpovězte vlastními slovy, dvě věty na otázku stačí.

1. Co znamená písmeno `M` u souboru a čím se liší od `U`?
2. K čemu slouží krok „stage", když stejně hned potom commituju?
3. Proč se změny z větve `barvy` neukázaly hned po přepnutí na `main`?
4. Co by se stalo, kdybyste v kroku 4 dali Discard Changes a žádný commit předtím neudělali?
5. Funguje commit bez internetu? A co push?

## Hotovo, když

- [ ] Repozitář má nejméně **4 commity**, každý se srozumitelnou zprávou
- [ ] Jeden commit vznikl na větvi `barvy` a je sloučený do `main`
- [ ] Větev `barvy` je smazaná
- [ ] Stránka se v prohlížeči zobrazí a má pozadí ze souboru `styles.css`
- [ ] Umíte ukázat porovnání libovolných dvou verzí `index.html`

Ukažte vyučujícímu historii commitů a odpovědi na kontrolní otázky.
