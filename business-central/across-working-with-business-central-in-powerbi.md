---
title: Arbejde med Business Central-data i Power BI| Microsoft Docs
description: 'Få indsigt, business intelligence og KPI''er fra Business Central-data ved hjælp af Power BI.'
author: jswymer
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'account schedule, analysis, reporting, financial report, business intelligence, KPI'
ms.date: 09/07/2022
ms.author: jswymer
---
# <a name="work-with-include-prodshortincludesprodshortmd-data-in-power-bi" />Arbejde med [!INCLUDE [prod_short](includes/prod_short.md)] data i Power BI

I denne artikel lærer du nogle af de grundlæggende oplysninger om arbejde med rapporter og dashboards i Power BI, der bruger [!INCLUDE [prod_short](includes/prod_short.md)] som datakilde. I artiklen diskuteres nogle aspekter, som kan hjælpe dig med at komme i gang som [!INCLUDE[prod_short](includes/prod_short.md)]-bruger. Du kan finde generelle retningslinjer og instruktioner i brugen af Power BI i [Power BI-dokumentationen til forbrugerne](/power-bi/consumer).

## <a name="get-ready" />Gør dig klar

Tilmeld dig Power BI-tjenesten. Hvis du ikke allerede har tilmeldt dig, skal du gå til [https://powerbi.microsoft.com](https://powerbi.microsoft.com). Når du tilmelder dig, skal du bruge din mailadresse og adgangskode.

## <a name="get-started" />Kom i gang

Når du har en Power BI-konto, kan du logge på [https://powerbi.microsoft.com/](https://powerbi.microsoft.com/).

Power BI-tjenesten er vært for alle de rapporter, der er tilgængelige. Hvis du vil have vist rapporten, skal du vælge **Mit arbejdsområde** > **Rapporter**. Derefter skal du blot vælge den rapport, du vil have vist.

Med [!INCLUDE[prod_short](includes/prod_short.md)] online får du automatisk et sæt standardrapporter i arbejdsområdet. Hvis du vil oprette dine egne rapporter, kan du bruge Power BI Desktop til at oprette rapporter og derefter udgive dem i arbejdsområdet. Du kan finde flere oplysninger i [Introduktion til oprettelse af rapporter i Power BI Desktop for at få vist [!INCLUDE [prod_long](includes/prod_long.md)]-data](across-how-use-financials-data-source-powerbi.md).

[!INCLUDE[note-multicompany-reports](includes/note-multicompany-reports.md)]

Hvis du bruger [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, skal du starte fra bunden ved hjælp af Power BI Desktop. Power BI-rapporter kan også distribueres som filer, som du kan overføre.

## <a name="get-the-latest-data" />Hente de seneste data

Hver Power BI-rapport er baseret på et datasæt, som henter data fra [!INCLUDE[prod_short](includes/prod_short.md)]-kilderne. Du skal være sikker på, at dataene i dine Power BI-rapporter er opdaterede med dataene i [!INCLUDE[prod_short](includes/prod_short.md)]. Dette begreb omtales som *opdatering*.  Afhængigt af, hvordan din organisation har oprettet Power BI, sker opdateringen muligvis ikke automatisk. Du kan opdatere data på to måder: manuelt eller ved at planlægge en opdatering. Manuel opdatering udføres efter behov. Planlagt opdatering giver dig automatisk opdatering med bestemte tidsintervaller.

### <a name="refresh-manually" />Opdatere manuelt

Vælg **Flere indstillinger (...)** ud for datasættet i navigationsruden under **Datasæt**, og vælg derefter **Opdater nu**.

### <a name="schedule-a-refresh" />Planlægge en opdatering

Vælg Flere indstillinger (...) ud for datasættet i navigationsruden under Datasæt, og vælg derefter **Planlæg opdatering**. Udfyld oplysningerne under **Planlæg opdatering**, og vælg **Anvend**.

Du kan finde flere oplysninger i [Konfigurere planlagt opdatering](/power-bi/connect-data/refresh-scheduled-refresh)

## <a name="a-nameuploadaupload-reports-from-files" /><a name="upload"></a>Overføre rapporter fra filer

Power BI-rapporter kan distribueres blandt brugere som .pbix-filer. Hvis du har en .pbix-fil, kan du overføre filen til et arbejdsområde. Benyt følgende fremgangsmåde for at overføre en rapport:

1. Vælg **Hent data** i det nye arbejdsområde .

2. I feltet Filer skal du vælge **Hent**.

3. Vælg **Lokal fil**, gå til det sted, hvor du har gemt filen, og vælg **Åbn**.

Du kan finde flere oplysninger i [Overføre rapporten til tjenesten](/power-bi/paginated-reports/paginated-reports-quickstart-aw#upload-the-report-to-the-service).

> [!NOTE]
> Hvis du overfører en rapport, kræver det, at du har et arbejdsområde med [Premium-kapacitet](/power-bi/service-premium-what-is). Du kan finde flere oplysninger i [Administrere Premium-kapaciteter](/power-bi/admin/service-premium-capacity-manage). 

> [!TIP]
> Hvis du bruger [!INCLUDE[prod_short](includes/prod_short.md)] online, kan du også overføre en rapport inde fra [!INCLUDE[prod_short](includes/prod_short.md)]. Du kan finde flere oplysninger i [Arbejde med Power BI-rapporter i [!INCLUDE [prod_short](includes/prod_short.md)] - Overføre rapporter](across-working-with-powerbi.md#upload).

## <a name="a-nameshareashare-reports-with-others" /><a name="share"></a>Dele rapporter med andre

Når en rapport findes i dit arbejdsområde, kan du dele den med andre i din organisation.

Hvis du vil dele en rapport i en listerapport eller i en åben rapport, skal du vælge **Del**. I ruden **Del rapport** skal du indtaste de fulde mailadresser for de enkeltpersoner eller distributionsgrupper, du vil dele med. Følg instruktionerne på skærmen for at fuldføre delingen. Du kan finde flere oplysninger i [Dele et dashboard eller en rapport](/power-bi/collaborate-share/service-share-dashboards#share-a-dashboard-or-report).

> [!NOTE]
> Du skal have [Power BI Pro-licens](/power-bi/service-features-license-type), og det samme gælder de personer, som du deler med. Indholdet skal være i et arbejdsområde med en [Premium-kapacitet](/power-bi/service-premium-what-is). Du kan få flere oplysninger i [Sådan deler du dit arbejde i Power BI](/power-bi/service-how-to-collaborate-distribute-dashboards-reports).

## <a name="see-related-microsoft-trainingtrainingmodulesconfigure-powerbi-excel-dynamics-365-business-centralindex" />Se relateret [Microsoft-træning](/training/modules/configure-powerbi-excel-dynamics-365-business-central/index)

## <a name="see-also" />Se også

[Business Central og Power BI](admin-powerbi.md)  
[Oprette Power BI-rapporter, der viser [!INCLUDE [prod_long](includes/prod_long.md)]-data](across-how-use-financials-data-source-powerbi.md)  
[Oversigt over Power BI-integrationskomponent og -arkitektur for [!INCLUDE[prod_short](includes/prod_short.md)]](admin-powerbi-overview.md)  
[Arbejde med Power BI-rapporter i [!INCLUDE [prod_short](includes/prod_short.md)]](across-working-with-powerbi.md)  
[Power BI for forbrugere](/power-bi/consumer/end-user-consumer)  
[Power BI-tjenestens nye udseende](/power-bi/service-new-look)  
[Hurtig start: Opret forbindelse til data i Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data)  
[Power BI-dokumentation](/power-bi/)  
[Business Intelligence](bi.md)  
[Blive køreklar](ui-get-ready-business.md)  
[Import af virksomhedsdata fra andre økonomisystemer](across-import-data-configuration-packages.md)  
[Opsætning af [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)  
[Brug af [!INCLUDE[prod_short](includes/prod_short.md)] som Power BI-datakilde](across-how-use-financials-data-source-powerbi.md)  
[Brug af [!INCLUDE[prod_short](includes/prod_short.md)] som Power Apps-datakilde](across-how-use-financials-data-source-powerapps.md)  
[Brug [!INCLUDE[prod_short](includes/prod_short.md)] i Power Automate](across-how-use-financials-data-source-flow.md)  




[!INCLUDE[footer-include](includes/footer-banner.md)]
