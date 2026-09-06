# MZ — Veškeré stavební práce (Děčín)

Klientský web pro dvoučlennou řemeslnou partu z Děčína.
Zakázka razdvaweb s pevnou cenou a termínem **jeden týden od dodání podkladů**.

## Co to je

Statický web. Dvě stránky, žádný framework, žádný build step.

```
index.html                    hlavní stránka
zasady-osobnich-udaju.html    GDPR
fonts.css + fonts/            self-hosted Archivo + IBM Plex Sans (latin, latin-ext)
img/                          fotky z realizací
robots.txt
```

Nasazení: GitHub → Vercel, preset "Other", prázdný build command.

## Pravidla, která neporušuj

**Žádné závislosti.** Ani npm, ani build nástroj, ani framework. Když se zdá, že
je něco potřeba, není — je to statická stránka pro řemeslníka.

**Žádné externí requesty.** Ani fonty, ani analytika, ani ikony z CDN, ani
mapy. Web schválně nenačítá nic z cizí domény, aby nepotřeboval cookie lištu.
To je vlastnost, ne opomenutí, a je to tak popsané v zásadách zpracování údajů.
Cokoliv přidaného zvenčí tenhle slib ruší.

**CSS zůstává inline v `<style>` v každé stránce.** Nerozděluj do souborů.

**Formulář zatím nikam neposílá.** Napojení řeším až po schválení vzhledu.
Až na to dojde: serverless endpoint na Vercelu + Resend. Ne dřív.

**Souhlas není právní titul pro poptávkový formulář.** Zpracování stojí na
čl. 6 odst. 1 písm. b) GDPR. Nepřidávej zaškrtávátko „souhlasím se
zpracováním osobních údajů".

## Čeká na klienta

Bez těchto věcí se nespouští a neběží týdenní termín:

- [ ] 12–20 fotek z realizací + 2 portréty → `img/`
- [ ] Jména obou, kdo dělá co
- [ ] Přesný název, IČO, adresa, plátcovství DPH
- [ ] Skutečné ceny „od" (v ceníku jsou teď vzorové!)
- [ ] Elektro: mají odbornou způsobilost dle vyhl. 250/2021? Podle toho
      se upraví formulace v sekci služeb a v FAQ.
- [ ] Doba uchování poptávek + jména zpracovatelů do zásad
- [ ] Vyřešená doména (držitelem je klient, registrátor Media4Web/Webnode —
      převod přes AuthInfo, u .cz zdarma a bez čekací lhůty)

Místa k doplnění jsou v kódu označená a v zásadách žlutě podbarvená. Nemaž je,
dokud nedorazí skutečné údaje — slouží jako kontrolní seznam při předání.

## Rozsah

Fixní cena. Obsahové změny jsou v ceně, změny funkčnosti nebo designu jsou
nový projekt. Když návrh vede k rozšíření rozsahu, řekni to nahlas dřív,
než to začneš dělat.

Šablonu pro další klienty vytáhnu až z hotové zakázky, ne během ní.

## Styl

- Vykání. Zákazník je majitel bytu, ne kamarád.
- Krátké věty, žádné korporátní vycpávky.
- Hlavní konverzní akce je telefon. Nesmí zmizet z dohledu na žádném rozlišení.
- Barvy a typografie jsou v CSS proměnných nahoře v `<style>`. Nepřidávej
  nové barvy mimo tuhle sadu.
