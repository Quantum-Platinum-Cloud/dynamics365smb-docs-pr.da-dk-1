---
title: Modtage og konvertere elektroniske dokumenter
description: 'Beskriver, hvordan du kan modtage elektroniske dokumenter direkte fra handelspartnere eller en OCR-tjeneste.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: null
ms.search.form: '189, 190, 191'
ms.date: 06/23/2021
ms.author: edupont
---
# <a name="receive-and-convert-electronic-documents" />Modtage og konvertere elektroniske dokumenter

Den generiske version af [!INCLUDE[prod_short](includes/prod_short.md)] understøtter modtagelse af elektroniske fakturaer og kreditnotaer i PEPPOL-formatet, som understøttes af de største udbydere af dokumentudvekslingstjenester. For at modtage en faktura fra en kreditor som et elektronisk PEPPOL-dokument, skal du behandle dokumentet på siden Indgående bilag for at konvertere det til en købsfaktura eller finanskladdelinje i [!INCLUDE[prod_short](includes/prod_short.md)].

Ud over at modtage elektroniske dokumenter direkte fra handelspartnere kan du modtage elektroniske dokumenter fra en OCR-tjeneste, der har omdannet dine PDF- eller billedfiler til elektroniske dokumenter.  

Før du kan modtage elektroniske dokumenter via dokumentudvekslingstjenesten, skal du konfigurere forskellige stamdata, som firmaoplysninger, kreditorer, varer og måleenheder. Disse bruges til at identificere forretningspartnere og varer ved konvertering af data i elementerne i den indgående bilagsfil til felter i [!INCLUDE[prod_short](includes/prod_short.md)]. Du kan finde flere oplysninger i [Konfigurere en dokumentudvekslingstjeneste](across-how-to-set-up-a-document-exchange-service.md).  

Før du kan modtage elektroniske dokumenter via OCR-tjenesten, skal du konfigurere og aktivere den forudkonfigurerede tjenesteforbindelse. Du kan finde flere oplysninger i [Konfigurere indgående bilag](across-how-setup-income-documents.md).  

Trafikken af elektroniske dokumenter ind og ud af [!INCLUDE[prod_short](includes/prod_short.md)] styres af opgavekøfunktionen. Før du kan modtage elektroniske dokumenter, skal den relevante opgavekø startes.  

Kan du enten starte konverteringen af elektroniske dokumenter manuelt som beskrevet i denne fremgangsmåde, eller du kan aktivere et workflow for at konvertere elektroniske dokumenter automatisk, når de er modtaget. Den generiske version af [!INCLUDE[prod_short](includes/prod_short.md)] indeholder workflowskabelonen *Fra indgående elektronik via OCR til at åbent købsfakturaworkflow*, som er klar til at blive kopieret til et workflow og aktiveret. Du kan finde flere oplysninger i [Workflow](across-workflow.md).  

> [!NOTE]  
> Når du konverterer elektroniske dokumenter, der er modtaget fra tjenesten OCR til dokumenter eller kladdelinjer i [!INCLUDE[prod_short](includes/prod_short.md)], lægges flere linjer i kildedokumentet sammen på én linje. Den enkelte linje er af typen Finanskonto og felterne **Beskrivelse** og Finanskonto **Nr.** er tomme. Værdien i feltet **Beløb** vil være lig med det samlede beløb uden moms for alle linjer i kildedokumentet.  
>
> For at sikre at felterne **Beskrivelse** og **Nummer** felter udfyldes, og du kan vælge knappen **Knyt tekst til konto** på siden **Indgående bilag** for at angive, at en bestemt fakturatekst altid skal knyttes til en bestemt debet- eller kreditkonto i finans. Fremover udfyldes feltet **Beskrivelse** i dokument- eller kladdelinjer, der er oprettet på grundlag af et elektronisk dokument for den pågældende kreditor eller debitor, med den relevante tekst og feltet **Nummer** på finanskontoen med den aktuelle konto.  
>
> I stedet for tilknytning til en finanskonto kan du også knytte til en bankkonto. Dette er nyttigt, f.eks. ved elektroniske dokumenter for udgifter, der allerede er betalt, hvor du vil oprette en finanskladdelinje, der er klar til at blive bogført på en bankkonto.  

Følgende fremgangsmåde beskriver, hvordan du modtager en kreditorfaktura og konvertere den til en købsfaktura i [!INCLUDE[prod_short](includes/prod_short.md)]. Fremgangsmåden er den samme, når du konverterer en kreditorfaktura til en finanskladdelinje.  

### <a name="to-receive-and-convert-an-electronic-invoice-to-a-purchase-invoice" />Sådan modtages og konverteres en elektronisk faktura til en købsfaktura

1. Vælg ![Lightbulb, der åbner funktionen Fortæl mig.](media/ui-search/search_small.png "Fortæl mig, hvad du vil foretage dig") ikon, angiv **Indgående bilag** og derefter vælge det relaterede link.  

2. Vælg linjen med den indgående bilagspost, der repræsenterer en ny indgående elektronisk faktura, og vælg derefter handlingen **Rediger**.  

    På siden **Indgående bilagskort** tilknyttes den relaterede XML-fil, og de fleste felter er udfyldt med oplysninger fra den elektroniske faktura. Du kan finde flere oplysninger i [Oprette indgående bilagsposter](across-how-create-income-document-records.md).  

3. I feltet **Dataudvekslingstype** skal du vælge **PEPPOL – faktura** eller **OCR – faktura** afhængigt af kilden til det elektroniske dokument.  

4. Du kan knytte tekst på kreditorfakturaen til en bestemt debetkonto ved at vælge **Knyt tekst til konto** i gruppen **Generelt** under fanen **Handlinger** og derefter udfylde siden **Kladde til tilknytning af tekst til konto**.  

5. Vælg handlingen **Opret bilag**.  

    Der oprettes en købsfaktura i [!INCLUDE[prod_short](includes/prod_short.md)] baseret på oplysningerne i det elektronisk dokument.  

    Valideringsfejl, der typisk vedrører forkerte eller manglende stamdata i [!INCLUDE[prod_short](includes/prod_short.md)], vises i oversigtspanelet **Fejlmeddelelser**.  

## <a name="see-related-microsoft-trainingtrainingmoduleselectronic-documents-dynamics-365-business-centralindex" />Se relateret [Microsoft-træning](/training/modules/electronic-documents-dynamics-365-business-central/index)

## <a name="see-also" />Se også

[Administrere skyldige beløb](payables-manage-payables.md)  
[Indgående bilag](across-income-documents.md)  
[Konfigurere afsendelse og modtagelse af elektroniske dokumenter](across-how-to-set-up-electronic-document-sending-and-receiving.md)  
[Udveksle data elektronisk](across-data-exchange.md)   
[Generelle forretningsfunktioner](ui-across-business-areas.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
