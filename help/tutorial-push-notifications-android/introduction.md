---
title: Introducción a las notificaciones push con la aplicación de Android™
description: Este tutorial le guía por los pasos necesarios para enviar notificaciones push desde Adobe Campaign y recibir estas notificaciones en la aplicación de Android™.
feature: Push
jira: KT-3846
doc-type: tutorial
activity: use
team: TM
recommendations: noDisplay
exl-id: 8dd772b2-b082-4e1e-842d-c5d6bcec564c
TQID: 'https://experienceleague.adobe.com/Ov4KKtdN-uhIr-TGldJCXw3GYFNUjap-SBE227dImfw'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: a4657621-810c-498b-8a27-7ced9c176dda
    internal-label: Push notifications
source-git-commit: 508c3590ce956401ccfba3a256000cbc5849a684
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 100%
---
# Introducción a las notificaciones push con la aplicación de Android™

Adobe Campaign permite enviar notificaciones push personalizadas y segmentadas a dispositivos móviles iOS y Android™.
Estos mensajes se reciben en aplicaciones móviles que se configuran en Adobe Campaign mediante el uso del SDK V4 de Experience Cloud Mobile o el SDK de Experience Platform.
Este tutorial le guía por los pasos necesarios para enviar notificaciones push desde Adobe Campaign y recibir estas notificaciones en la aplicación de Android™.

## Requisitos previos

* Debe tener la propiedad de inicio configurada con la extensión de Adobe Campaign Standard. Siga la ayuda en línea que se indica a continuación.
  * [Tutorial de vídeo](https://video.tv.adobe.com/v/40904?captions=spa&learn=on){transcript=true}
  * [Documentación](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/mobile/configure-mobile-apps-using-aep-sdk.html?lang=es)

* Asegúrese de que el estado de la propiedad correspondiente en Adobe Campaign Standard esté configurado.
* [Tener una cuenta activa de Google Firebase](https://firebase.google.com)
* [Última versión de Android™ Studio instalada](https://developer.android.com/studio)

## Pasos del tutorial

* [Paso 1: Creación de una aplicación para Android™](/help/tutorial-push-notifications-android/create-android-app.md)
* [Paso 2: Integración del SDK de Mobile](/help/tutorial-push-notifications-android/integrating-with-mobile-sdk.md)
* [Paso 3: Registro de extensiones con la aplicación móvil](/help/tutorial-push-notifications-android/register-mobile-extensions.md)
* [Paso 4: Definición del identificador push](/help/tutorial-push-notifications-android/set-push-identifier.md)
* [Paso 5: Propagación de notificaciones](/help/tutorial-push-notifications-android/propagate-notification.md)
* [Paso 6: Envío de notificaciones push](/help/tutorial-push-notifications-android/send-push-notification.md)
