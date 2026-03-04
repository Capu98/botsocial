# Analytics Setup — BotSocial
<!-- Creato: 2026-03-04 -->

## Google Analytics 4 — Come ottenere il Measurement ID

1. Vai su [analytics.google.com](https://analytics.google.com) e accedi con il tuo account Google
2. Clicca **"Inizia a misurare"** → inserisci nome account (es. "BotSocial")
3. Crea una proprietà → scegli **"Web"** → inserisci URL del sito (es. `capu98.github.io/botsocial`)
4. Ti viene assegnato un **Measurement ID** nel formato `G-XXXXXXXXXX`
5. In `index.html`, sostituisci **entrambe** le occorrenze di `GA_MEASUREMENT_ID` con il tuo ID reale

### Dove cercare nel codice
```
<!-- Google Analytics 4 -->
<script async src="...?id=G-XXXXXXXXXX"></script>  ← sostituire qui
gtag('config', 'G-XXXXXXXXXX');                    ← e qui
```

---

## Event Tracking — Eventi configurati

| Evento | Trigger | Categoria | Label |
|--------|---------|-----------|-------|
| `click_cta_call` | Click su qualsiasi link `call.html` | CTA | — |
| `click_pricing_card` | Click su una card pricing | Pricing | Nome piano (Starter / Pro / Agenzia) |
| `scroll_50pct` | Scroll oltre il 50% della pagina | Engagement | — |

### Come verificare gli eventi in GA4
1. In GA4 → menu sinistro → **"Report" → "Tempo reale"**
2. Apri il sito in un'altra scheda e interagisci (clicca CTA, scorri la pagina)
3. Gli eventi appariranno in tempo reale entro pochi secondi

---

## KPI da monitorare settimanalmente

### Traffico
- **Utenti attivi** (settimana corrente vs settimana precedente)
- **Fonte traffico**: organico / social / diretto / referral
- **Pagine più visitate** — capire dove arrivano e dove si fermano

### Engagement
- **Tasso di rimbalzo** — obiettivo < 60%
- **Tempo medio sulla pagina** — obiettivo > 1:30 min
- **scroll_50pct rate** — % di visitatori che scorrono oltre metà pagina

### Conversioni
- **click_cta_call** — quanti cliccano "Prenota una call"
- **click_pricing_card** — interesse per i piani (quale piano attira di più)
- **Tasso di conversione** = click_cta_call / utenti totali — obiettivo > 3%

---

## Note operative

- Il Measurement ID è pubblico (va nel codice HTML) — non è un segreto
- I dati iniziano ad apparire in GA4 dopo 24-48h dalla prima visita
- Per la reportistica storica usare: GA4 → Libreria → Report → Acquisizione e Coinvolgimento
- Collegare anche Google Search Console per i dati SEO (link in GA4 → Admin → Integrazioni)
