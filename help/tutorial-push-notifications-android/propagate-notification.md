---
title: 'Paso 5: Propagación de las notificaciones'
description: En esta parte, propagaremos el mensaje recibido de Adobe Campaign mediante Android Notification Manager.Firebase
feature: Push
jira: KT-4829
doc-type: tutorial
activity: use
team: TM
exl-id: b0e01224-4ddc-4999-b8c6-794e49245428
source-git-commit: c84867ef59a10448a377a959d0b67ae71343a4aa
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 2%

---

# Añadir servicio para enviar notificaciones

En esta parte, propagaremos el mensaje recibido de Adobe Campaign mediante [!DNL Android Notification Manager]. [!DNL Notification manager] se utiliza para notificar al usuario de los eventos que se producen.
Así es como le dices al usuario que algo ha pasado en segundo plano:

* Launch [!DNL Android Studio]
* Abrir *[!DNL ACSPushTutorial]* proyecto
* Expandir la estructura del proyecto
* Haga clic con el botón derecho en la carpeta del paquete ([!DNL com.example.acspushtutorial]) y [!DNL New ->Java Class]
* Asigne un nombre a esta clase *[!DNL MyService]* y asegúrese de que se extiende [!DNL FirebaseMessagingService]
* Crear *[!DNL sendNotification]* en esta clase. En este método, es necesario establecer el contenido y el canal de la notificación mediante una [!DNL NotificationCompat.Builder] objeto. Para que aparezca la notificación, llame a [!DNL NotificationManagerCompat.notify()], pasándole un ID único para la notificación y el resultado de [!DNL NotificationCompat.Builder.build()].

<!--
Removed `{.line-numbers}` below
-->

```java
package com.example.pushmessaging;
import android.app.NotificationChannel;
import android.app.NotificationManager;
import android.app.PendingIntent;
import android.content.Context;
import android.content.Intent;
import android.media.RingtoneManager;
import android.net.Uri;
import android.os.Build;
import android.util.Log;

import androidx.core.app.NotificationCompat;

import com.google.firebase.messaging.FirebaseMessagingService;
import com.google.firebase.messaging.RemoteMessage;

import java.util.Map;

public class MyService extends FirebaseMessagingService {
@Override
public void onMessageReceived(RemoteMessage remoteMessage)
{
Map<String,String> data  = remoteMessage.getData();
Log.d("data payload: ", data.toString());
sendNotification(remoteMessage);
}


private void sendNotification(RemoteMessage message) {
Intent intent = new Intent(this, MainActivity.class);
intent.addFlags(Intent.FLAG_ACTIVITY_CLEAR_TOP);
PendingIntent pendingIntent = PendingIntent.getActivity(this, 0 /* Request code */, intent, PendingIntent.FLAG_ONE_SHOT);

String channelId = "0";
Uri defaultSoundUri = RingtoneManager.getDefaultUri(RingtoneManager.TYPE_NOTIFICATION);
NotificationCompat.Builder notificationBuilder =
        new NotificationCompat.Builder(this, channelId)
                .setSmallIcon(R.drawable.ic_launcher_background)
                .setContentTitle("Message from AEM")
                .setContentText(message.getData().get("body"))
                .setAutoCancel(true)
                .setSound(defaultSoundUri)
                .setContentIntent(pendingIntent);

NotificationManager notificationManager =
        (NotificationManager) getSystemService(Context.NOTIFICATION_SERVICE);

// Since android Oreo notification channel is needed.
if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.O) {
    NotificationChannel channel = new NotificationChannel(channelId,
            "Channel human readable title",
            NotificationManager.IMPORTANCE_DEFAULT);
    notificationManager.createNotificationChannel(channel);
}

notificationManager.notify(0 /* ID of notification */, notificationBuilder.build());
}
}
```

## Modificar [!DNL AndroidManifest.xml]

Añada el servicio que se creó a su [!DNL AndroidManifest.xml]. La final [!DNL AndroidManifest.xml] debería tener el siguiente aspecto:

<!--
Removed `{.line-numbers}` below
-->

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.example.pushmessaging">

    <uses-permission android:name="android.permission.INTERNET" />
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />

    <application
        android:name=".MainApp"
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/AppTheme">
        <service
            android:name=".MyService"
            android:exported="false">
            <intent-filter>
                <action android:name="com.google.firebase.MESSAGING_EVENT" />
            </intent-filter>
        </service>

        <activity android:name=".MainActivity">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>

</manifest>
```

## Ejecute la aplicación

Ejecute la aplicación haciendo clic en **flecha verde** en la barra de herramientas o desde el [!DNL Run] menú.
