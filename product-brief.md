# Product Brief: orgAnIzed – KI-støttet oppgavehåndtering

## Executive Summary

**orgAnIzed** er en enkel webapplikasjon for oppgavehåndtering som bruker kunstig intelligens til å hjelpe brukeren med å organisere oppgaver. Brukeren kan opprette og administrere oppgaver som i en vanlig To-Do-liste, mens KI analyserer oppgaveteksten og foreslår etikett, prioritet og et kort sammendrag.

Mange bruker oppgavelister til å holde oversikt over studier, jobb og private gjøremål. Etter hvert som antallet oppgaver øker, kreves det mer manuelt arbeid for å kategorisere og prioritere dem. orgAnIzed skal redusere dette arbeidet uten å gjøre oppgavehåndteringen mer komplisert.

Målet med første versjon er å lage en enkel og fungerende applikasjon som demonstrerer hvordan grunnleggende CRUD-funksjonalitet kan kombineres med KI på en praktisk måte.

## The Problem

Tradisjonelle To-Do-applikasjoner gjør det enkelt å registrere oppgaver, men organiseringen overlates i stor grad til brukeren. Brukeren må selv velge kategori, vurdere prioritet og holde oversikt over hvilke oppgaver som haster.

Dette kan bli vanskelig når oppgaver fra flere områder samles på samme sted. En student kan for eksempel samtidig ha oppgaver knyttet til studier, jobb og privatliv. Når listen vokser, kan det bli vanskeligere å raskt se hva som bør prioriteres.

Det finnes derfor en mulighet til å bruke KI til å automatisere deler av organiseringen samtidig som brukeren beholder kontrollen.

## The Solution

orgAnIzed skal gi brukeren et enkelt grensesnitt for å opprette og administrere oppgaver.

Når en oppgave opprettes, analyserer KI oppgaveteksten og foreslår en passende **etikett**, **prioritet** og et **kort sammendrag**. En oppgave som «Levere programmeringsoppgaven innen søndag» kan for eksempel få etiketten *Studier* og prioriteten *Høy*.

KI-forslagene skal være hjelpemidler og ikke automatiske beslutninger. Brukeren kan derfor endre forslagene dersom de ikke passer.

Oppgavene samles i en oversikt hvor brukeren kan se status, prioritet, etikett og eventuell frist, samt redigere, fullføre eller slette oppgaver.

## What Makes This Different

orgAnIzed skiller seg fra en vanlig To-Do-liste ved at deler av organiseringen kan gjøres automatisk ved hjelp av KI.

I stedet for at brukeren alltid må kategorisere og prioritere hver oppgave manuelt, kan applikasjonen foreslå dette basert på innholdet i oppgaven.

Prosjektet baserer seg ikke på en unik KI-modell eller algoritme. Forskjellen ligger i å kombinere vanlig oppgavehåndtering med enkel KI-assistanse på en måte som er lett å forstå og bruke.

## Who This Serves

Den primære målgruppen er **studenter som ønsker en enkel måte å organisere oppgaver fra studier, jobb og privatliv på**.

Brukeren skal kunne registrere en oppgave raskt uten å måtte organisere all informasjon manuelt. En vellykket brukeropplevelse betyr at det er enkelt å legge inn oppgaver, forstå hvilke som bør prioriteres og holde oversikt over hva som er fullført.

Løsningen kan også brukes av andre som ønsker en enkel personlig oppgaveliste.

## Success Criteria

Første versjon regnes som vellykket dersom:

- brukeren kan opprette, vise, redigere, fullføre og slette oppgaver
- oppgaver og endringer lagres slik at de ikke forsvinner når siden lastes på nytt
- KI kan foreslå etikett, prioritet og et kort sammendrag basert på oppgaveteksten
- brukeren kan endre KI-forslagene manuelt
- oppgaver kan filtreres eller sorteres etter minst status, etikett eller prioritet
- applikasjonen håndterer ugyldige eller manglende data uten å krasje

KI-forslagene trenger ikke alltid være perfekte. Et viktig kriterium er derfor at brukeren beholder kontrollen og enkelt kan overstyre forslagene.

## Scope

### In – første versjon

Første versjon skal inneholde:

- grunnleggende oppgavehåndtering (CRUD)
- status og forfallsdato
- etikett og prioritet
- KI-forslag til etikett, prioritet og sammendrag
- mulighet til å endre KI-forslag
- enkel filtrering og sortering
- et enkelt webgrensesnitt

### Out – ikke i første versjon

Følgende holdes utenfor første versjon:

- mobilapplikasjon
- deling og samarbeid mellom brukere
- kalender- og e-postintegrasjoner
- push-varsler
- avansert prosjektstyring
- KI som utfører oppgaver på vegne av brukeren

Dette holder første versjon liten nok til at kjernefunksjonaliteten kan prioriteres.

## Vision

På lengre sikt kan orgAnIzed utvikles fra en enkel To-Do-liste til en mer intelligent personlig oppgaveassistent.

En fremtidig versjon kan lære av hvordan brukeren organiserer oppgaver, foreslå hva som bør gjøres først og hjelpe med planlegging av dagen eller uken. Løsningen kan også integreres med kalender og andre produktivitetsverktøy.

Visjonen er likevel å beholde enkelheten: **orgAnIzed skal redusere tiden brukeren bruker på å organisere oppgaver, ikke gjøre oppgavehåndtering mer komplisert.**
