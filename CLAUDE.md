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

**Žádné externí requesty při načtení stránky.** Ani fonty, ani analytika, ani
ikony z CDN, ani mapy. Otevření webu nesmí sáhnout na cizí doménu — díky tomu
nepotřebuje cookie lištu.

Odeslání formuláře je výjimka a je v pořádku: požadavek spouští sám uživatel
kliknutím, nic se neukládá do prohlížeče a souhlas se nevyžaduje. Zpracovatel
ale musí být uvedený v zásadách zpracování — Web3Forms tam je.

**CSS zůstává inline v `<style>` v každé stránce.** Nerozděluj do souborů.

**Formulář odesílá přes Web3Forms** (`api.web3forms.com/submit`), poptávka chodí
na `veskerestavebniprace01@gmail.com`. Zdarma do 250 zpráv měsíčně, bez serveru.
Access key je veřejně v HTML — tak to má být; zneužít se přes něj nedá nic kromě
posílání zpráv na tu jednu adresu, proti čemuž je ve formuláři honeypot (`botcheck`).

Původně byl v plánu Vercel serverless + Resend. Zahozeno kvůli rozpočtu klienta.
Nevracet se k tomu bez důvodu.

Po odeslání se přesměrovává na `dekujeme.html`. Adresa přesměrování je zatím
vercel.app — **po převodu domény přepsat** na ostrou adresu.

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
