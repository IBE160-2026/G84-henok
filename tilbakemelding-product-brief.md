# Tilbakemelding på product brief

| | |
|---|---|
| **Gruppe** | G84 – G84-henok |
| **Product brief** | `product-brief.md` (commit `c5cfa77`) |
| **Tilbakemelding fra** | Faglærer i IBE160 (utarbeidet med KI-støtte) |
| **Dato** | 2026-10-06 |

Vurdert fil: `product-brief.md` i repoets rot, som er den eneste briefen. Det finnes ennå ikke PRD, arkitektur eller epics.

## Samlet vurdering

- **Godt utgangspunkt med justeringer.** Gruppen kan gå videre og innarbeide punktene under.

**Det som er bra:**

1. Briefen er ryddig, følger malen og har en realistisk avgrensning. Suksesskriteriene er funksjonelle og kan sjekkes: opprette, vise, redigere, fullføre og slette, lagring ved omlasting, filtrering og at appen ikke krasjer ved ugyldige data.
2. Dere er tydelige på at KI-forslagene er hjelpemidler, ikke beslutninger, og at «KI-forslagene trenger ikke alltid være perfekte», så lenge brukeren kan overstyre dem. OUT-listen (mobil, deling, kalender, push-varsler) holder v1 liten.

**De viktigste endringene:**

1. Gjør briefen mer til deres egen. Mye av teksten er generell og kunne passet de fleste oppgaveapper. Beskriv en konkret bruker og situasjon (for eksempel hvordan dere selv holder oversikt over innleveringer, jobbvakter og private gjøremål i dag), og hvilke etiketter appen skal bruke (Studier, Jobb, Privat?).
2. Legg til et mål for KI-kvaliteten. Kriteriet «KI kan foreslå etikett, prioritet og et kort sammendrag» er oppfylt så snart KI svarer noe. Lag et testsett, for eksempel 20 oppgavetekster med forventet etikett og prioritet, og sett et mål for hvor mange forslag som skal treffe. Definer også hva som gir «Høy» prioritet.
3. Legg en plan for språkmodellen og for sensor. Briefen sier ikke hvilken KI-tjeneste dere vil bruke, hvordan nøkkelen holdes utenfor koden, eller hva som skjer når KI ikke svarer. Sensor må kunne kjøre appen uten deres nøkkel, for eksempel med en testmodus eller regelbaserte reserveforslag.

## Vanskelighetsgrad og gjennomførbarhet

### Vurdert vanskelighetsgrad

- **Enkel**

**Sammenlignbart med:** 6) To-do-liste med smarte etiketter (enkel). Briefen er i praksis dette forslaget, uten smarte lister eller andre utvidelser.

**Begrunnelse:**

| Faktor | Nivå (lav / middels / høy) | Kommentar |
|---|---|---|
| Domenelogikk – hvor mange og hvor kompliserte regler og beregninger må stemme? | Lav | Status, forfallsdato, filtrering og sortering. |
| Datamodell – antall entiteter og relasjoner mellom dem | Lav | I praksis én entitet (oppgave) med noen felt. |
| Brukere, roller og innlogging | Lav | Én personlig bruker uten innlogging. |
| KI-funksjonalitet i appen, f.eks. kall til språkmodell, prompts i koden og håndtering av usikre svar | Middels | Ett KI-kall som gir tre forslag. Krever strukturert svar og feilhåndtering. |
| Integrasjoner og eksterne tjenester, f.eks. API-er, betaling og e-post | Lav | Bare språkmodell-API. |
| Sanntid, samtidighet eller flere brukere som påvirker hverandre | Lav | Ingen. |
| Filhåndtering, f.eks. opplasting, PDF-lesing og eksport | Lav | Ingen. |
| Sikkerhet og personvern | Lav | Oppgavetekst sendes til en ekstern KI-tjeneste. Si kort i appen hva som sendes. |

**Hva vanskelighetsgraden betyr for dere:**

- _Enkel:_ Et enkelt prosjekt gir stor sjanse for å bli ferdig. Vanskelighetsgraden inngår likevel i vurderingen, så for å nå helt opp må dere vise mer i gjennomføringen. Det betyr særlig et gjennomarbeidet design, grundig testing, en tydelig dokumentert prosess og en README som virker.

### Gjennomførbarhet med BMAD og Claude Code

| Spørsmål | Vurdering (OK / risiko / stor risiko) | Kommentar |
|---|---|---|
| **Tid og omfang** – kan v1 realistisk bli ferdig og stabil i løpet av semesteret, med tid til flere iterasjoner? | OK | Ja, med god margin, også for én person. Risikoen er at det blir for lite å vise. |
| **BMAD-flyten** – er briefen konkret nok til at PRD, arkitektur og stories kan lages uten store hull, og blir det overkommelig mange stories? | OK | Scope og kriterier kan bli krav og stories direkte. Avklar etikettene og prioritetsreglene. |
| **Egnet for Claude Code** – bruker løsningen en vanlig, godt dokumentert teknologistakk som Claude Code håndterer godt, eller krever den nisjeteknologi, spesialmaskinvare eller mye manuell konfigurasjon? | OK | Enkel webapp med CRUD og ett API-kall er svært godt egnet. |
| **Kontroll på KI-ens arbeid** – kan gruppen selv avgjøre om koden gjør det riktige? Krever domenet kunnskap gruppen ikke har, f.eks. avanserte beregninger eller fagregler, så er det vanskelig å kvalitetssikre. | OK | Alt kan kontrolleres ved å bruke appen. Med et testsett kan dere også vurdere KI-forslagene. |
| **Testbarhet** – finnes det tydelige regler og forventede resultater som tester kan skrives mot? | OK | De funksjonelle kriteriene egner seg godt for tester. Legg til testsett og mock-svar for KI-delen. |
| **Kjørbar for sensor** – kan appen kjøres lokalt etter README, uten gruppens nøkler, betalte kontoer eller egen infrastruktur? | Risiko | Ikke beskrevet. KI-delen trenger testmodus eller tydelig nøkkeloppsett. |
| **Avhengigheter og kostnader** – krever løsningen betalte API-er, f.eks. språkmodeller, og finnes det en plan for kostnad, testmodus eller mock-data? | Risiko | Krever språkmodell-API, uten plan for kostnad eller testmodus ennå. |

**Konklusjon om gjennomførbarhet:**

- **Gjennomførbart som beskrevet.**

**Forslag til justering av omfang eller vanskelighetsgrad:**

1. Legg til én eller to utvidelser i v1, slik at det blir nok å vise frem, for eksempel smarte lister («I dag», «Denne uken», «Høy prioritet»), eller at KI-en også foreslår forfallsdato fra tekst som «innen søndag».
2. Når kjerneflyten virker, kan dere vurdere at appen lærer av brukerens korrigeringer, for eksempel ved å bruke tidligere godkjente etiketter som eksempler i prompten.

## Hvorfor product brief er viktig for mappen

Product brief er utgangspunktet for PRD, arkitektur, stories og til slutt koden. Del 1 av mappen vurderes blant annet på om sensor kan følge en sporbar vei fra plan til ferdig app. Den vurderes også på om appen gjør det dere har beskrevet, om den er testet, om den er godt designet, og om den kan kjøres etter README. Et uklart, for stort eller for lite brief gjør alt dette vanskeligere senere. Det er mye enklere å rette nå enn sent i semesteret.

## 1. Gjennomgang av briefens deler

| Del av brief | Status | Kommentar |
|---|---|---|
| Executive Summary – er det klart hva appen er, og hvilket problem den løser? | OK | Klart: en enkel oppgaveapp der KI foreslår etikett, prioritet og sammendrag. |
| The Problem – er problemet konkret, med reelle situasjoner og brukere? | Juster | Forståelig, men generelt. Gi et konkret eksempel fra egen hverdag. |
| The Solution – beskriver løsningen brukeropplevelsen, ikke bare teknologi? | OK | Beskriver hva brukeren gjør, med eksempelet «Levere programmeringsoppgaven innen søndag». |
| What Makes This Different – er vurderingen ærlig og realistisk? | OK | Ærlig: ingen unik modell, men en enkel kombinasjon av oppgavehåndtering og KI. |
| Who This Serves – er primærbrukerne tydelige, og vet vi hva de trenger? | Juster | Studenter er en grei målgruppe, men beskriv en konkret bruker og situasjon. «Andre som ønsker en enkel oppgaveliste» kan godt tas ut. |
| Success Criteria – kan kriteriene faktisk sjekkes eller testes? | Juster | Funksjonelle kriterier er gode. Legg til et målbart kriterium for KI-forslagene. |
| Scope – er det klart hva som er med i første versjon, og hva som ikke er det? | OK | Tydelig In/Out. Vurder én utvidelse for å få mer å vise. |
| Vision – henger visjonen sammen med resten uten å blåse opp omfanget? | OK | Henger sammen og holder fast på enkelheten. |

## 2. Utgangspunkt for del 1 av mappen

Punktene følger kriteriene i sensorveiledningen for del 1. Vektene i parentes viser hvor mye hvert kriterium teller i del 1.

| Kriterium i del 1 | Hva briefen bør legge til rette for | Status | Kommentar |
|---|---|---|---|
| **1. Prosess og KI-styring** (30 %) | Brief som er presis nok til at PRD og stories kan bygges direkte på den, slik at krav kan spores fra brief til kode. | Juster | Briefen er presis nok, men repoet har bare én opplasting. Bruk BMAD videre (PRD, arkitektur, stories), commit jevnlig og lagre promptene. |
| **2. Funksjonalitet og omfang** (20 %) | Realistisk omfang for gruppen og semesteret: en tydelig kjerneflyt som kan bli ferdig og stabil, og nok innhold til å vise reell funksjonalitet. | Juster | Realistisk, men lite. Legg til en eller to utvidelser, se forslagene over. |
| **3. Kvalitetssikring og testing** (15 %) | Suksesskriterier og funksjoner som er konkrete nok til å bli testtilfeller. | Juster | God start. Testsett for KI-forslagene vil styrke dette mye. |
| **4. Design og brukeropplevelse** (10 %) | Tydelige brukere og brukssituasjoner som designet kan bygges rundt, gjerne med de viktigste skjermbildene eller flytene skissert. | Juster | Oversikten er lett å se for seg. Skisser hvordan KI-forslagene vises og godkjennes, og legg vekt på et gjennomarbeidet design siden prosjektet er enkelt. |
| **5. Kodekvalitet og arkitektur** (10 %) | Teknologivalg som er begrunnet og ikke mer komplekse enn appen trenger. | OK | Ingen teknologi er valgt ennå, og det er greit. Hold det enkelt, og kall KI fra serveren, ikke fra nettleseren. |
| **6. README og kjørbarhet** (10 %) | Løsning som andre kan kjøre lokalt uten betalte kontoer, og uten tilgang til gruppens egne tjenester og nøkler. | Juster | Planlegg testmodus eller reserveforslag for KI, slik at sensor kan kjøre appen. |
| **7. Ryddighet i repoet** (5 %) | En plan for hvor hemmeligheter, testdata og dokumentasjon skal ligge. | Juster | Bestem en mappe for planleggingsdokumenter, og hold API-nøkkelen i `.env` utenfor Git. |

## 3. Neste steg for gruppen

1. Beskriv en konkret bruker og situasjon, og bestem etikettene og reglene for prioritet.
2. Lag et testsett med rundt 20 oppgavetekster og forventede forslag, og legg til et målbart KI-kriterium. Velg KI-tjeneste og beskriv testmodus.
3. Velg en eller to utvidelser for v1, og lag deretter PRD med BMAD.

Oppdater product brief i repoet når dere har gjort endringene, slik at historikken viser hvordan planen utviklet seg. Det er en del av prosessen sensor ser etter.
