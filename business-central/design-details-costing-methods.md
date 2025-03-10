---
title: Designoplysningers omkostningsmetoder
description: 'Dette emne beskriver, hvordan kostmetoden afgør, om en faktisk og budgetteret værdi føres som aktiv og bruges i beregningen af kostprisen.'
author: bholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: null
ms.date: 05/12/2023
ms.author: bholtorf
---
# Designoplysninger: Kostmetoder

Kostmetoden afgør, om en faktisk eller en budgetteret værdi føres som aktiv og bruges i beregningen af kostprisen. Sammen med bogføringsdatoen og rækkefølgen har kostmetoden også indflydelse på, hvordan kostprisforløbet registreres.

> [!NOTE]
> Du kan ikke ændre en vares kostmetode, hvis der findes vareposter for varen. Du kan finde flere oplysninger i [Design detaljer: Ændre kostmetoden for varer](design-details-changing-costing-methods.md).

Følgende metoder understøttes i [!INCLUDE[prod_short](includes/prod_short.md)]:  

| Kostmetode | Beskrivelse | Hvornår skal den bruges |
|--|--|--|
| FIFO | En vares kostpris er den faktiske værdi af alle modtagelser af varen, som vælges af FIFO-reglen.<br /><br /> I lagerværdien forudsættes det, at de første varer, der lægges på lager, bliver solgt først. | I virksomhedsmiljøer, hvor produktomkostninger er stabile.<br /><br /> (Når priser stiger, viser balancen højere værdi. Dette betyder, at skatteforpligtelserne øges, men kreditvurderinger og muligheden for at låne penge forbedres.)<br /><br /> For varer med en begrænset hyldelevetid, fordi de ældste varer skal sælges, inden de overskrider deres sidste salgsdato. |
| LIFO | En vares kostpris er den faktiske værdi af alle modtagelser af varen, som vælges af LIFO-reglen.<br /><br /> I lagerværdien forudsættes det, at de sidste varer, der lægges på lager, bliver solgt først. | Forbudt i mange lande/områder, da det kan bruges til at holde avancen nede.<br /><br /> (Når priser stiger, falder værdien på resultatopgørelsen. Dette betyder, at skatteforpligtelserne reduceres, men muligheden for at låne penge forringes.) |
| Gennemsnit | En vares kostpris beregnes som den gennemsnitlige kostpris på hvert enkelt tidspunkt efter et køb.<br /><br /> For værdiansættelse af lageret antages det, at alle lagerbeholdninger sælges samtidig. | I virksomhedsmiljøer, hvor produktomkostninger er ustabile.<br /><br /> Når lagre stables eller blandes sammen, og der ikke kan skelnes mellem dem, f.eks. kemikalier. |
| Bestemt | En vares kostpris er den præcise kostpris, som den aktuelle enhed er modtaget til. | I produktion eller handel med varer, der nemt kan identificeres, med forholdsvis høje kostpriser.<br /><br /> For varer, der er omfattet af regulering.<br /><br /> For varer med serienumre. |
| Standard | En vares kostpris forudindstilles baseret på forventninger.<br /><br /> Når det faktiske kostbeløb realiseres senere, skal standardkostprisen reguleres til de faktiske omkostninger gennem variansværdier. | Hvor omkostningsstyring er afgørende.<br /><br /> I serieproduktion til at evaluere kostpriserne for direkte materialeomkostninger, arbejdsomkostninger og produktionsomkostninger.<br /><br /> Hvor der er disciplin og personale til at vedligeholde standarderne. |

Følgende billede viser, hvordan omkostningerne passerer gennem lageret for hver kostmetode.  

![Omkostningsmetoder visualiseret.](media/design_details_inventory_costing_7_costing_methods.png "Omkostningsmetoder visualiseret")  

Kostmetoder varierer i den måde, hvorpå de værdiansætter lagerreduceringer, og om de bruger faktiske omkostninger eller standardomkostninger som værdigrundlag. Den følgende tabel beskriver de forskellige karakteristika. (LIFO-metoden er udelukket, da den minder meget om FIFO-metoden).  
<!--Old  table
|Category|FIFO|Average|Standard|Specific|  
|-|----------|-------------|--------------|--------------|  
|General characteristic|Easy to understand|Based on period options: **Day**/**Week**/**Month**/**Quarter**/**Accounting Period**.<br /><br /> Can be calculated per item or per item/location/variant.|Easy to use, but requires qualified maintenance.|Requires item tracking on both inbound and outbound transaction.<br /><br /> Typically used for serialized items.|  
|Application/Adjustment|Application keeps track of **the remaining quantity**.<br /><br /> Adjustment forwards costs according to quantity application.|Application keeps track of the **remaining quantity**.<br /><br /> Costs are calculated and forwarded per the **valuation date**.|Application keeps track of the **remaining quantity**.<br /><br /> Application is based on FIFO.|All applications are fixed.|  
|Revaluation|Revalues invoiced quantity only.<br /><br /> Can be done per item or per item ledger entry.<br /><br /> Can be done backward in time.|Revalues invoiced quantity only.<br /><br /> Can be done per item only.<br /><br /> Can be done backward in time.|Revalues invoiced and un-invoiced quantities.<br /><br /> Can be done per item or per item ledger entry.<br /><br /> Can be done backward in time.|Revalues invoiced quantity only.<br /><br /> Can be done per item or per item ledger entry.<br /><br /> Can be done backward in time.|  
|Miscellaneous|If you back-date an inventory decrease, then existing entries are NOT reapplied to provide a correct FIFO cost flow.|If you back-date an inventory increase or decrease, then the average cost is recalculated, and all affected entries are adjusted.<br /><br /> If you change the period or calculation type, then all affected entries must be adjusted.|Use the **Standard Worksheet** page to periodically update and roll up standard costs.<br /><br /> Is NOT supported per SKU.<br /><br /> No historic records exist for standard costs.|You can use specific item tracking without using the Specific costing method. Then the cost will NOT follow the lot number, but the cost assumption of the selected costing method.|  
-->
<!--Table flipped for slightly better readability -->

||Generelle egenskaber|Udligning/justering |Værdiregulering|Diverse |
|-|---------|---------|---------|---------|
|**FIFO**     |Let at forstå|Udligning holder styr på **det resterende antal**.<br /><br /> Justering overfører omkostninger i henhold til antalsudligning. |Værdiregulerer kun fakturerede antal.<br /><br /> Kan foretages pr. vare eller pr. varepost.<br /><br /> Kan foretages bagudrettet.|Hvis du baguddaterer en lagerreducering, bliver eksisterende poster IKKE genanvendt for at sikre et korrekt FIFO-omkostningsforløb.|
|**Gennemsnit**     |Baseret på periodeindstillinger: **dag**/**uge**/**måned**/**kvartal**/**regnskabsperiode**.<br /><br /> Kan beregnes pr. vare eller pr. vare/lokation/variant.|Udligning holder styr på **det resterende antal**.<br /><br /> Omkostninger beregnes og overføres pr. **værdiansættelsesdato**. |Værdiregulerer kun fakturerede antal.<br /><br /> Kan kun foretages pr. vare.<br /><br /> Kan foretages bagudrettet. |Hvis du baguddaterer en lagerforøgelse eller -reducering, genberegnes den gennemsnitlige kostpris, og alle berørte poster justeres.<br /><br /> Hvis du ændrer perioden eller beregningstypen, skal alle berørte poster reguleres.|
|**Standard**     |Let at bruge, men kræver kvalificeret vedligeholdelse.|Udligning holder styr på **det resterende antal**.<br /><br /> Udligning er baseret på FIFO.|Værdiregulerer fakturerede og ikke-fakturerede antal.<br /><br /> Kan foretages pr. vare eller pr. varepost.<br /><br /> Kan foretages bagudrettet.|Brug siden **Standardkladde** til regelmæssigt at opdatere og akkumulere standardomkostninger.<br /><br /> Understøttes ikke pr. lagervare.<br /><br /> Der findes ingen historiske poster for standardomkostninger.|
|**Specifik**     |Kræver varesporing på både indgående og udgående transaktion.<br /><br /> Bruges typisk til serienummererede varer.|Alle udligninger er faste.|Værdiregulerer kun fakturerede antal.<br /><br /> Kan foretages pr. vare eller pr. varepost.<br /><br /> Kan foretages bagudrettet.|Du kan bruge specifik varesporing uden at bruge den specifikke kostmetode. Derefter følger prisen IKKE lotnummeret, men omkostningsforventningen for den valgte kostmetode.|

## Eksempel

Dette afsnit indeholder eksempler på, hvordan forskellige kostmetoder påvirker lagerværdien.  

Følgende tabel viser lagerforøgelser og -reduceringer, som eksemplerne er baseret på.  

|Bogføringsdato|Antal|Løbenr.|  
|------------------|--------------|---------------|  
|01-01-20|1|1|  
|01-01-20|1|2|  
|01-01-20|1|3|  
|02-01-20|-1|4|  
|03-01-20|-1|5|  
|04-01-20|-1|6|  

> [!NOTE]  
> Det resulterende antal i lageret er nul. Derfor skal lagerværdien også være nul, uanset hvilken kostmetode der anvendes.  

### Kostmetoders indflydelse på værdiansættelse af lagerforøgelser  

For varer med kostmetoder, der bruger de faktiske omkostninger som grundlag for værdiansættelsen (**FIFO**, **LIFO**, **Gennemsnit**, eller **Specifik**), værdiansættes lagerforøgelser til varens anskaffelsesomkostninger.  

- **Standard**  

    For varer, der bruger kostmetoden **Standard**, værdiansættes lagerforøgelser til varens aktuelle standardkostpris.  

#### Standard  

For varer, der bruger kostmetoden **Standard**, værdiansættes lagerforøgelser til varens aktuelle standardkostpris.  

### Kostmetoders indflydelse på værdiansættelse af lagerreduktioner

- **FIFO**  

    For varer, der benytter kostmetoden **FIFO**, sælges varer, der er købt først, altid først (løbenumre 3, 2 og 1 i dette eksempel). Ligeledes værdiansættes lagerreducering ved at tage værdien af den første lagerforøgelse.  

     VAREFORBRUG beregnes ud fra værdien af de første lageranskaffelser.  

     Følgende tabel viser, hvordan lagerreduktioner værdisættes til **FIFO**-kostmetoden.  

    |Bogføringsdato|Antal|Kostbeløb (faktisk)|Løbenr.|  
    |------------------|--------------|----------------------------|---------------|  
    |02-01-20|-1|-10,00|4|  
    |03-01-20|-1|-20,00|5|  
    |04-01-20|-1|-30,00|6|  

- **LIFO**  

    For varer, der benytter kostmetoden **LIFO**, sælges varer, der er købt senest, altid først (løbenumre 3, 2 og 1 i dette eksempel). Ligeledes værdiansættes lagerreduceringer ved at tage værdien af den seneste lagerforøgelse.  

     VAREFORBRUG beregnes ud fra værdien af de seneste lageranskaffelser.  

     Følgende tabel viser, hvordan lagerreduktioner værdisættes til **LIFO**-kostmetoden.  

    |Bogføringsdato|Antal|Kostbeløb (faktisk)|Løbenr.|  
    |------------|--------|--------------------|---------|  
    |02-01-20|-1|-30,00|4|  
    |03-01-20|-1|-20,00|5|  
    |04-01-20|-1|-10,00|6|  

- **Gennemsnit**  

    For varer, der bruger kostmetoden **Gennemsnit**, værdiansættes lagerreduktioner ved at beregne et vægtet gennemsnit af det resterende lager på den sidste dag i den gennemsnitlige omkostningsperiode, hvor lagerreduktionen blev bogført. Du kan finde flere oplysninger i [Designoplysninger: Gennemsnitlig kostpris](design-details-average-cost.md).  

     Følgende tabel viser, hvordan lagerreduktioner værdisættes i **Gennemsnit**-kostmetoden.  

    | Bogføringsdato | Antal | Kostbeløb (faktisk) | Løbenr. |
    |--|--|--|--|
    | 02-01-20 | -1 | -20,00 | 4 |
    | 03-01-20 | -1 | -20,00 | 5 |
    | 04-01-20 | -1 | -20,00 | 6 |

- **Standard**  

    For varer, der benytter kostmetoden **Standard**, værdiansættes lagerreduceringer svarende til kostmetoden **FIFO**, bortset fra at værdiansættelse er baseret på standardomkostninger, ikke på de faktiske omkostninger.  

    Følgende tabel viser, hvordan lagerreduktioner værdisættes i **Standard**-kostmetoden.  

    |Bogføringsdato|Antal|Kostbeløb (faktisk)|Løbenr.|  
    |------------------|--------------|----------------------------|---------------|  
    |02-01-20|-1|-15,00|4|  
    |03-01-20|-1|-15,00|5|  
    |04-01-20|-1|-15,00|6|  

- **Bestemt**  

    I kostmetoder arbejdes der ud fra en antagelse om, hvordan kostprisen flyder fra en lagerforøgelse til en lagerreduktion. Hvis der findes mere nøjagtige oplysninger om kostprisforløbet, kan du dog tilsidesætte denne antagelse ved at oprette en fast udligning mellem poster. En fast udligning opretter et link mellem en lagerreducering og en bestemt lagerforøgelse og angiver kostprisforløbet i overensstemmelse hermed.  

    For varer, der benytter kostmetoden **Specifik**, værdiansættes lagerreduceringer i henhold til den lagerforøgelse, der er tilknyttet med den faste udligning.  

    Følgende tabel viser, hvordan lagerreduktioner værdisættes i **Specifik**-kostmetoden.  

    |Bogføringsdato|Antal|Kostbeløb (faktisk)|Udlign.postløbenr.|Løbenr.|
    |------------|--------|--------------------|----------------|---------|  
    |02-01-20|-1|-20,00|**2**|4|  
    |03-01-20|-1|-10,00|**1**|5|  
    |04-01-20|-1|-30,00|**3**|6|  

## Se også

[Designoplysninger: Lagerberegning](design-details-inventory-costing.md)  
[Designoplysninger: Afvigelse](design-details-variance.md)  
[Designoplysninger: Gennemsnitlig omkostning](design-details-average-cost.md)  
[Designoplysninger: Vareudligning](design-details-item-application.md)  
[Administrere lageromkostninger](finance-manage-inventory-costs.md)  
[Finans](finance.md)  
[Arbejd med [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Ordliste med termer i Dynamics 365 business processes](/dynamics365/guidance/business-processes/glossary)  
[Definere oversigt over produkt-og serviceomkostninger](/dynamics365/guidance/business-processes/product-service-define-cost-overview)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
