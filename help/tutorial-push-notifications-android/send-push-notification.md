---
title: 'Parte 6: Envío de una notificación push para probar el trabajo'
description: 'Parte 6: Envío de una notificación push para probar el trabajo'
feature: Push
jira: KT-4830
user: Admin
level: Experienced
doc-type: tutorial
activity: use
team: TM
exl-id: 10218e1f-6e85-490a-84d9-c5d42bd2321d
source-git-commit: f4712dcf6dec01867414057346f8501c6e1669ec
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 3%

---

# Parte 6: Envío [!UICONTROL Push Notification] para probar su trabajo

Ahora necesitamos crear y enviar un [!UICONTROL Push Notification] uso de Adobe Campaign. Para crear una notificación push simple con fines de prueba, siga los siguientes pasos.

* Inicie sesión en la instancia de Adobe Campaign Standard.
* Haga clic en **[!UICONTROL Marketing Activities]->[!UICONTROL Create]->[!UICONTROL Push Notification]**
* Seleccionar **[!UICONTROL Send push to app subscribers(mobileApp)]** y haga clic en Siguiente
* Seleccione la aplicación móvil adecuada en el **[!UICONTROL Associate a Mobile App to a delivery]** y haga clic en **[!UICONTROL Next]**
* Haga clic en la etiqueta count y debería devolver un valor mayor que 0. Haga clic en **[!UICONTROL Next]**
* Proporcionar una clave [!UICONTROL Message title] y [!UICONTROL Message body] y haga clic en **[!UICONTROL Create]**.
* Haga clic en **[!UICONTROL Prepare]**. Una vez finalizada la preparación, haga clic en **[!UICONTROL Confirm]** para enviar el mensaje.

Si todo va bien, debería ver una notificación en la aplicación de Android™ ejecutándose en el emulador.

## Recursos adicionales

* [Documentación detallada sobre las notificaciones push](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/push-notifications/about-push-notifications.html?lang=en)
* [Creación de una notificación push (vídeo)](/help/communication-channels/mobile/push-notifications/creating-a-push-notification.md)
