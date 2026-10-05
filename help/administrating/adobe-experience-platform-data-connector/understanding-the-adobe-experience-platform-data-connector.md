---
title: Comprender el conector de datos de Adobe Experience Platform
description: El conector de datos de Adobe Experience Platform ayuda a los clientes existentes a ofrecer sus datos en Adobe Experience Platform asignando datos XTK (datos incorporados en Campaign) a datos del modelo de datos de experiencia (XDM) en Adobe Experience Platform.
feature: People Core Service Integration
jira: KT-2826
thumbnail: 27304.jpg
role: User
level: Experienced
doc-type: feature video
activity: understand
team: TM
exl-id: 686961f9-5374-4cc6-8b36-7ee0584ea720
TQID: 'https://experienceleague.adobe.com/8z32-bArYoMN41QFSi19bXUFc617UqZvdzxaam0Xr-E'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: a8512b64-d668-4084-b4f0-34baa899e306
    internal-label: People Core Service integration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 508c3590ce956401ccfba3a256000cbc5849a684
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 4%
---
# Comprender el Adobe Experience Platform [!UICONTROL Data Connector]

>[!NOTE]
>
>Esta funcionalidad está en versión beta y sujeta a frecuentes actualizaciones y modificaciones sin previo aviso.
>
>Póngase en contacto con [!UICONTROL Adobe Customer Support] si planea implementar esta capacidad.

## Información general

Adobe Experience Platform [!UICONTROL Data Connector] ayuda a los clientes existentes a ofrecer sus datos en Adobe Experience Platform asignando datos XTK (datos incorporados en Adobe Campaign) a datos [!DNL Experience Data Model] (XDM) en Adobe Experience Platform.

El conector es unidireccional y envía los datos de Adobe Campaign Standard a Adobe Experience Platform. Los datos nunca se envían desde Adobe Experience Platform a Adobe Campaign Standard.

Adobe Experience Platform [!UICONTROL Data Connector] está dirigido a ingenieros de datos que comprenden Adobe Campaign Standard [!UICONTROL custom resources] y tienen una comprensión de cómo debe estar el esquema de datos general del cliente dentro de Adobe Experience Platform.

>[!VIDEO](https://video.tv.adobe.com/v/27304?learn=on){transcript=true}

*Este vídeo ofrece información general sobre Adobe Experience Platform [!UICONTROL Data Connector] (9:35 min)*

>[!NOTE]
>
>No se admite la transferencia predeterminada de [!UICONTROL subscription events]. Para transferir [!UICONTROL subscription events], puede crear el XDM y el conjunto de datos correspondientes en Adobe Experience Platform y, a continuación, configurar una asignación de datos personalizada para estos datos.
>
>No se pueden ingerir [!UICONTROL experience events] existentes en Adobe Experience Platform, pero los [!UICONTROL experience events] generados en curso se transmiten a Adobe Experience Platform.

## Pasos clave para realizar una asignación de datos

En los siguientes tutoriales se describen los pasos clave para realizar una asignación de datos entre Campaign Standard y Adobe Experience Platform:

1. [Asignación de recursos personalizados](/help/administrating/adobe-experience-platform-data-connector/mapping-custom-resources.md)
2. [Asignación de eventos de experiencias](/help/administrating/adobe-experience-platform-data-connector/mapping-experience-events.md)
3. [Asignación de datos de tabla semilla](/help/administrating/adobe-experience-platform-data-connector/mapping-seed-table-data.md)
4. [Modificación de la asignación de datos](/help/administrating/adobe-experience-platform-data-connector/modifying-data-mapping.md)
5. [Comprobación del estado de un trabajo de ingesta de datos](/help/administrating/adobe-experience-platform-data-connector/checking-status-of-data-ingestion-jobs.md)

