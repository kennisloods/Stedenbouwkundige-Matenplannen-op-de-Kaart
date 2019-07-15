# Stedenbouwkundige Matenplannen op de Kaart
Geeft een gemeentedekkend actueel overzicht van actuele en historische stedenbouwkundige matenplannen (SMP's) en van nota's van uitgangspunten (NvU).

## toelichting

De dataset geeft een actueel overzicht van actuele en historische (fasen van) uitgezonden Stedelijke Matenplannen (SMP's). Van de uitzendingen wordt de plangrens weergegeven met aanvullende projectgegevens. Het doel is om een overzicht te geven van lopende SMP's; het kan daarmee een ingang zijn naar de officiele uitzendingen en uitgezonden tekeningen.

Een SMP kan de volgende fasen doorlopen:

1. concept SMP
2. (laatst) voorlopige uitzending (LVUZ / VUZ)
3. goedkeuringsuitzending (GUZ)
4. definitieve uitzending (DUZ)
5. wijzigingsuitzending (WUZ)

Binnen een fase kunnen meerdere revisies voorkomen.

## bronnen

* uitzendingslijsten 2016 t/m 2018
* uitzendlijst nieuwe stijl
* SMP-tekeningen (AutoCAD)

## bewerking
### initiele vulling

De initiele vulling is aangemaakt door:

1. per jaar afleiden van plancontouren uit de plangrenzen in de SMP-tekeningen (AutoCad);
   1. inlezen van lagen met grenzen uit de SMP-tekeningen (zie opsomming met laagnamen hieronder);
   2. clippen op gemeentegrens;
   3. extraheren van SMP-nummer + status + gebiedcode + evt. revisie;
   4. stroken van arcs;
   5. vormen van polygonen uit lijnen, arcs, ellipses / overnemen polygonen;
   6. verwijderen binnengrenzen per combinatie van SMP-nummer + status + gebiedcode + evt. revisie;
   7. aggregeren naar SMP-nummer + status + gebiedcode + evt. revisie;
   8. wegschrijven naar bestand;
2. per jaar koppelen van uitzendinglijsten aan de gevormde plancontouren;
   1. koppelen rijen met tekeningnummers aan bovenliggende rijen met gebiedsnaam;
   2. gebiedsnaam koppelen aan codetabel (vb. Charlois aan "CH");
   3. uit 'soort uitzending' extraheren fase en eventuele revisie
   4. uit 'tekeningnummer' extraheren van SMP-nummer (##-####);
   5. resultaat koppelen aan de aangemaakte contouren uit stap 1 op basis van gebied + tekeningnummer + fase + revisie;
3. samenvoegen jaargangen;
   6. ontdubbelen van combinaties van gebied + tekeningnummer + fase + revisie;
   7. per gebied + tekeningnummer bepalen wat de actuele fase + revisie is.

Ad 1.i). Alleen de volgende AutoCAD-layers zijn gebruikt om contouren te vormen:

* `ALG_Projectgrens`
* `ALG_projectgrens_binnenwereld`
* `N-PV-AL-GRENS_PLAN-1-1000-G`
* `X-XX-AL-FASERINGSGRENS-G`
* `X-XX-AL-GRENS-G`
* `X-XX-AL-PROJECTGRENS HAVENBEDRIJF-G`
* `X-XX-AL-PROJECTGRENS-G`
* `X-XX-AL-PROJECTGRENS_BUITEN`
* `X-XX-AL-PROJECTGRENS_FASE1-G`
* `X-XX-AL-PROJECTGRENS_FASE2-G`
* `X-XX-AL-PROJECTGRENS_NIEUWEDORP-G`
* `X-XX-AL-PROJECTGRENS_SMP-G`
* `X-XX-AL-PROJECTGRENS_SMP_FASE1-G`
* `X-XX-AL-PROJECTGRENS_SMP_FASE2-G`
* `X-XX-AL-PROJECTGRENS_SMP_FASE2_FASE3-G`
* `X-XX-AL-PROJECTGRENS_SMP_FASE4-G`
* `X-XX-AL-PROJECTGRENS_SMP_FASE5-G`
* `X-XX-AL-PROJECTGRENS_SMP_FASE6-G`
* `X-XX-AL-PROJECTGRENS_SMP_FASE7-G`
* `X-XX-AL-PROJECTGRENS_SMP_GYMZAAL-G`
* `X-XX-AL-WIJZIGINGSGRENS-G`
