# IT Návody - Šablony pro tisk

Jednotný styl pro tvorbu a tisk návodů.

## Struktura souborů

```
navody/
├── navody-print.css          # Hlavní stylesheet (linkuj do všech návodů)
├── navod-sablona.html        # Prázdná šablona pro nové návody
├── priklad-logicka-hradla-tahak.html  # Ukázkový návod
└── README.md                 # Tento soubor
```

## Rychlý start

1. **Zkopíruj šablonu:**
   
   ```bash
   cp navod-sablona.html muj-novy-navod.html
   ```
1. **Uprav obsah** v HTML editoru
1. **Otevři v prohlížeči** → Ctrl+P → Tisk do PDF nebo tiskárny

## Jak upravit vzhled všech návodů najednou

Všechny barvy, fonty a rozměry jsou v CSS proměnných na začátku `navody-print.css`:

```css
:root {
    --color-primary: #2c3e50;    /* Změň pro jinou hlavní barvu */
    --color-secondary: #3498db;  /* Akcenty */
    --font-size-base: 14px;      /* Velikost textu */
    /* ... */
}
```

## Dostupné CSS třídy

### Sekce a kontejnery

- `.section` - základní ohraničená sekce
- `.step` - krok v návodu
- `.warning` - žluté upozornění (⚠️)
- `.tip` / `.info` - zelený tip (💡)

### Tabulky

- `table` - standardní tabulka
- `table.truth-table` - kompaktní pravdivostní tabulka (centrovaná)

### Seznamy

- `ol.steps` - číslované kroky s velkými čísly v kroužku

### Pomocné

- `.text-center`, `.text-right` - zarovnání
- `.text-muted` - šedý text
- `.no-print` - skryje při tisku

### Rozbalovací sekce

```html
<details>
    <summary>Klikni pro zobrazení</summary>
    <p>Skrytý obsah - při tisku se automaticky rozbalí</p>
</details>
```

## Tisk

### Optimalizace pro tisk

- Všechny `<details>` se při tisku automaticky rozbalí
- Prvky s `.no-print` se skryjí
- Sekce se nerozdělují mezi stránky (`page-break-inside: avoid`)

### Doporučený prohlížeč

**Chrome** má nejspolehlivější tisk. V tiskovém dialogu:

- ☑️ Barvy a obrázky na pozadí
- Okraje: Výchozí nebo Minimální

## Patička a licence

Každý návod má v patičce:

- Jméno autora
- Licenci CC BY-SA 4.0

Při úpravě zachovej odkaz na původního autora.

## GitHub Pages (sdílení online)

1. Nahraj soubory do GitHub repozitáře
1. Settings → Pages → Source: main branch
1. Návody budou dostupné na: `https://TVUJ-NICK.github.io/navody/`

-----

Autor: David | Montessori ZŠ Archa
Licence: CC BY-SA 4.0