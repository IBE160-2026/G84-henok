# Product Brief: orgAnIzed – KI-støttet oppgavehåndtering

## Executive Summary

**orgAnIzed** er en enkel webapplikasjon som hjelper en student med å holde oversikt over oppgaver fra studier, jobb og privatliv. Brukeren registrerer en oppgave, og kan be KI foreslå etikett, prioritet og et kort sammendrag. Brukeren vurderer forslagene og kan endre dem før lagring.

Prosjektet tar utgangspunkt i min egen situasjon: Jeg kombinerer studier med fulltidsjobb og familieliv med en nyfødt og et barn i småbarnsalderen. Omsorgsoppgaver, avbrudd og uforutsigbare perioder med ro gjør det krevende å planlegge og gjennomføre studiearbeid. Når jeg får tid til å arbeide, trenger jeg raskt å se hvilke oppgaver som haster og hvor jeg skal fortsette.

Første versjon skal gi en samlet oppgaveoversikt med varig lagring, tydelige frister og enkle smarte lister. Målet er en stabil og oversiktlig applikasjon med dokumentert KI-bruk og testing, innenfor et omfang som kan gjennomføres av én student.

## The Problem

En student med jobb og omsorgsansvar må håndtere flere typer oppgaver samtidig. En studieinnlevering kan nærme seg samtidig som praktiske familieoppgaver må løses og arbeidsrelaterte gjøremål må følges opp. Med en nyfødt og en smårolling kan planlagte arbeidsøkter bli avbrutt eller flyttet. Det øker behovet for å lagre oppgaver raskt og finne tilbake til dem uten å bruke mye tid på organisering.

En konkret brukssituasjon er at studenten har en kort, ledig stund om kvelden og må avgjøre om tiden bør brukes på en innlevering, en jobbrelatert oppgave eller et privat gjøremål. En ustrukturert liste gir ikke nødvendigvis et tydelig svar på hva som haster. Prosjektet skal derfor gjøre kategori, frist og prioritet synlig i samme oversikt.

Dette er et behov hentet fra egen hverdag, ikke et resultat av en gjennomført brukerundersøkelse. Hvilke eksisterende notat- eller kalenderverktøy brukeren benytter, er ikke kartlagt. Appen skal støtte prioritering; den kan ikke fjerne tidsmangel eller forutsi familiens behov.

## The Solution

Brukeren oppretter en oppgave med tittel, valgfri beskrivelse og eventuell forfallsdato. Oppgaven kan lagres og administreres uten KI. Ved å velge «Foreslå med KI» får brukeren forslag til etikett, prioritet og et kort sammendrag. Forslagene vises tydelig som forslag og kan godkjennes eller endres.

Eksempel: Med referansedato 17. oktober og forfallsdato 18. oktober kan «Levere programmeringsoppgaven» få etiketten **Studier** og prioriteten **Høy**. En oppgave om å kjøpe klær til barna uten tidsfrist kan få **Privat** og **Middels**, med mindre teksten tydelig sier at den kan vente.

Oppgavene vises med status, etikett, prioritet og frist. Brukeren kan redigere, fullføre og slette dem, og filtrere og sortere oversikten. De smarte listene **I dag**, **Denne uken** og **Høy prioritet** gjør det lettere å finne aktuelle oppgaver etter et avbrudd.

### Etiketter og prioritet

Første versjon bruker tre etiketter:

- **Studier:** forelesninger, øvinger, innleveringer og eksamensforberedelser.
- **Jobb:** personlige arbeidsrelaterte gjøremål, uten pasientopplysninger eller annen fortrolig informasjon.
- **Privat:** familie, hjem og øvrige personlige gjøremål.

Oppgaver som berører flere områder, får ett forslag til hovedetikett som brukeren kan endre. Ved uklar oppgavetekst skal appen gjøre det enkelt å velge manuelt.

Prioritetsreglene brukes både i KI-instruksjonen og i testingen:

- **Høy:** oppgaven er ufullført og forfalt, har forfallsdato i dag eller i morgen, eller beskrives eksplisitt som noe som må gjøres straks/i dag.
- **Lav:** oppgaven beskrives eksplisitt som valgfri eller noe som kan vente, og ingen regel for Høy gjelder.
- **Middels:** øvrige oppgaver, inkludert oppgaver uten frist eller tydelig hasteangivelse.

Høy har forrang ved motstridende signaler. Datoer vurderes i tidssonen Europe/Oslo. Brukerens manuelle valg overstyrer forslaget og skal ikke senere endres automatisk av KI.

### Smarte lister

- **I dag:** ufullførte oppgaver med frist i dag eller tidligere; forfalte oppgaver merkes tydelig.
- **Denne uken:** ufullførte oppgaver med frist fra mandag til søndag i inneværende uke, samt eldre forfalte oppgaver.
- **Høy prioritet:** alle ufullførte oppgaver med lagret prioritet Høy, også uten frist.

Dette er regelbaserte visninger av eksisterende oppgaver, ikke ekstra KI-kall.

## What Makes This Different

orgAnIzed kombinerer enkel oppgavehåndtering med forslag som reduserer manuell kategorisering. Brukeren får en rask vei fra oppgavetekst til en oversiktlig liste, men beholder kontrollen over alle valg.

Prosjektet bygger ikke på en unik modell eller en ny algoritme. Verdien ligger i en avgrenset og forståelig arbeidsflyt for en travel student: rask registrering, synlige frister, enkle smarte lister og KI-forslag som kan korrigeres. Et gjennomarbeidet grensesnitt og pålitelig oppførsel prioriteres fremfor mange funksjoner.

## Who This Serves

Primærbrukeren er en student som kombinerer studier med jobb og familieansvar. Min egen hverdag med fulltidsjobb, en nyfødt og en smårolling gir et konkret utgangspunkt for designet. Løsningen skal likevel kunne brukes av andre studenter med oppgaver fra flere deler av livet.

Brukeren trenger å kunne legge inn en oppgave raskt, avbryte arbeidet og senere finne tilbake til det som haster. En vellykket brukeropplevelse innebærer tydelig oversikt, få nødvendige steg og at oppgavene blir bevart ved omlasting. Første versjon er for én personlig bruker uten innlogging eller samarbeid.

## Success Criteria

### Funksjonalitet og brukeropplevelse

Første versjon skal oppfylle følgende kriterier:

- Brukeren kan opprette, vise, redigere, fullføre og slette oppgaver.
- Oppgaver og endringer beholdes når siden lastes på nytt.
- Tomme titler og ugyldige datoer håndteres med forståelige meldinger uten at appen krasjer.
- Etikett, prioritet, status og eventuell frist vises tydelig.
- Filtrering etter status, etikett og prioritet, samt sortering etter frist og prioritet, gir riktige resultater.
- De tre smarte listene følger de dokumenterte reglene.
- KI-forslag kan godkjennes eller endres før lagring. Feil i KI-tjenesten hindrer ikke manuell oppgavehåndtering.
- Viktige handlinger kan utføres med tastatur. Skjemafelt har tydelige etiketter, og prioritet formidles med tekst i tillegg til farge.

### Målbar KI-kvalitet

Før KI-funksjonen implementeres, opprettes et fast testsett på **20 syntetiske, norske oppgavetekster**, fordelt på Studier, Jobb og Privat. Hvert tilfelle får referansedato, eventuell forfallsdato, forventet etikett og forventet prioritet. Testsettet skal omfatte ulike prioriteter, forfalte oppgaver, oppgaver uten frist og tydelige grenseeksempler.

Målene for en dokumentert evaluering av den faktiske språkmodellen er:

- Minst **16 av 20** etikettforslag samsvarer med forventet etikett.
- Minst **16 av 20** prioritetsforslag samsvarer med de definerte reglene.
- Minst **18 av 20** sammendrag er på norsk, består av én setning på maksimalt 20 ord, bevarer hovedhandlingen og tilfører ingen nye fakta. Dette vurderes manuelt etter samme kriterier for alle tilfellene.

Forventede svar fastsettes før evaluering. Testene skal ikke inneholde ekte personopplysninger. Modellidentifikator, promptversjon, dato og faktiske resultater lagres. Dersom målene ikke nås, dokumenteres feilene og eventuelle forbedringer; resultatene skal ikke fremstilles som bedre enn de er. Et lite testsett gir prosjektspesifikk dokumentasjon, ikke bevis på generell modellkvalitet.

Automatiserte tester med mock-svar kontrollerer separat at appen håndterer gyldige svar, ugyldige svar, tidsavbrudd og API-feil. Mock-svar eller reserveforslag teller ikke som måling av språkmodellens kvalitet.

## Scope

### In – første versjon

- Personlig oppgavehåndtering uten innlogging: opprette, vise, redigere, fullføre og slette.
- Tittel, valgfri beskrivelse, status, forfallsdato, etikett og prioritet.
- Varig lagring og enkel filtrering og sortering.
- KI-forslag til etikett, prioritet og kort sammendrag, med manuell kontroll.
- Smarte lister: I dag, Denne uken og Høy prioritet.
- Et oversiktlig webgrensesnitt med grunnleggende tilgjengelighet.
- Tydelig informasjon om hvilke opplysninger som sendes til KI-tjenesten.
- Testmodus uten API-nøkkel, feilhåndtering og dokumenterte tester.

### Out – ikke i første versjon

- Egen mobilapplikasjon.
- Innlogging, flere brukere, deling og samarbeid.
- Kalender- og e-postintegrasjoner eller push-varsler.
- Avansert prosjektstyring og automatisk omplanlegging.
- KI som utfører oppgaver på vegne av brukeren.
- Automatisk læring fra tidligere brukerrettelser.
- Automatisk uttrekking og lagring av forfallsdato fra fritekst; brukeren angir datoen manuelt.
- Pasientopplysninger, journaldata eller annen fortrolig arbeidsinformasjon.

Smarte lister er valgt som den avgrensede utvidelsen etter faglærers tilbakemelding. Mer avanserte KI-funksjoner utsettes for å prioritere stabilitet, testing og dokumentasjon.

## Plan for KI-tjeneste, personvern og kjørbarhet

**Planlagt tjeneste:** OpenAI API, med en rimelig tekstmodell som støtter strukturerte svar. Det konkrete modellnavnet fastsettes og dokumenteres i PRD/arkitektur etter en enkel tilgjengelighets- og kostnadssjekk. Modellvalget gjøres konfigurerbart på serveren. Dette er et planlagt teknologivalg, ikke en allerede implementert integrasjon.

KI-kall gjøres fra serveren, aldri direkte fra nettleseren med en hemmelig nøkkel. Nøkkelen ligger i en lokal `.env`-fil som utelates fra Git. Repoet får en `.env.example` med variabelnavn og ufarlige eksempelverdier. Avhengigheter og øvrig teknologistakk velges i arkitekturarbeidet med vekt på enkel lokal oppstart.

Brukeren får beskjed om at oppgavens tittel, beskrivelse, eventuell frist og nødvendig datokontekst sendes til en ekstern KI-tjeneste når forslag etterspørres. Hele oppgavelisten sendes ikke. Appen skal oppfordre til å unngå sensitive opplysninger. API-nøkler og rå oppgavetekster skal ikke skrives til vanlige applikasjonslogger.

Kall skjer bare ved en eksplisitt brukerhandling, ikke ved hvert tastetrykk. Det settes grenser for tekstlengde og svarlengde, og automatisk gjentakelse av kall begrenses. En foreløpig utviklingsramme er **100 NOK i API-forbruk**, som følges opp under utviklingen; dette er et budsjettmål, ikke en garantert kostnad eller automatisk håndhevet grense.

**Testmodus for sensor:** Appen skal kunne startes uten API-nøkkel eller betalt konto. Standard testmodus bruker dokumenterte, regelbaserte reserveforslag og merkes tydelig som «Testmodus – regelbaserte forslag». Den demonstrerer arbeidsflyten, men utgir seg ikke for å være en språkmodell. README forklarer hvordan ekte KI aktiveres med egen nøkkel.

Ved tidsavbrudd, ugyldig svar eller tjenestefeil beholdes brukerens tekst. Appen viser en forståelig melding og lar brukeren fortsette manuelt eller velge tydelig merkede reserveforslag. Svar fra modellen valideres før de vises eller lagres.

## Utviklingsprosess og kvalitetssikring

Briefen brukes videre i BMAD til PRD, UX-beskrivelse, arkitektur, epics og stories. Planleggingsdokumenter samles under `docs/`, med egne områder for KI-økter/prompter, beslutninger og testresultater. Eksakt struktur tilpasses BMAD-oppsettet og beskrives i README.

Arbeidet deles i små, reelle utviklingssteg med beskrivende commits. Prompter, korrigeringer av KI-forslag og begrunnede endringer lagres underveis. Krav kobles til stories og relevante tester, slik at veien fra plan til kode kan følges.

Kvalitetssikringen omfatter automatiserte tester av sentrale regler og feilsituasjoner, manuelle tester av brukerflyten og en separat evaluering av KI-forslagene. README skal inneholde eksakte installasjons-, oppstarts- og testkommandoer. Oppskriften prøves i et rent miljø før levering.

Denne revisjonen er utarbeidet med ChatGPT-støtte på grunnlag av opprinnelig brief, faglærers tilbakemelding datert 6. oktober 2026 og studentens beskrevne livssituasjon. Dokumentet beskriver planlagt arbeid. Ingen implementering, brukertesting eller oppnådde KI-resultater hevdes gjennomført.

## Vision

På lengre sikt kan orgAnIzed bli en personlig oppgaveassistent som bruker tidligere godkjente kategoriseringer som eksempler, foreslår datoer fra tekst og eventuelt integreres med kalender. Slike funksjoner vurderes først etter at første versjon fungerer stabilt og erfaringer viser et reelt behov.

Visjonen er å bevare enkelheten: **orgAnIzed skal gjøre det lettere å finne neste viktige oppgave i en travel hverdag, uten at organiseringen blir en ekstra oppgave.**

## Revisjonsnotat – 17. oktober 2026

- Konkretisert målgruppen med studier, fulltidsjobb og omsorg for en nyfødt og en smårolling.
- Definert etiketter, prioritetsregler og smarte lister.
- Lagt til målbar KI-evaluering på 20 syntetiske oppgaver.
- Planlagt serverbasert KI-integrasjon, nøkkelhåndtering, kostnadskontroll og testmodus.
- Tydeliggjort personvern, feilhåndtering, testing og sporbar utviklingsprosess.
- Neste steg: oppdatere briefen i kursrepoet og bruke den som grunnlag for BMAD-PRD.
