---
title: 'Paso 2: Integración del SDK de Mobile'
description: En esta parte, integraremos la aplicación de Android con Mobile SDK. Para integrar SDK móvil con la aplicación de Android
feature: Push
user: Admin
level: Experienced
jira: KT-4826
doc-type: tutorial
activity: use
team: TM
recommendations: noDisplay
exl-id: 0fa53536-8330-4e96-be2f-afc078609bcd
TQID: https://experienceleague.adobe.com/6WL8yj7aMoS9C6l-HwQZZ3Hg0B2jmNtlmaFnsAi0Ohw
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 7d15c0a5dc01907ff529b3684eaddaca5321facc
workflow-type: tm+mt
source-wordcount: 164
ht-degree: 3%

---

# PASO 2: Integrar [!UICONTROL Mobile SDK] con la aplicación de Android

En esta parte, integraremos la aplicación [!DNL Android] con [!UICONTROL Mobile SDK]. Para integrar [!UICONTROL mobile SDK] con la aplicación [!DNL Android], siga los siguientes pasos:

* Abrir el proyecto *ACSPushTutorial* en [!DNL Android Studio]
* Cree una nueva clase Java llamada *MainApp* que extienda [!DNL android.app.Application]
* La estructura del proyecto en este punto debería ser la siguiente

![aplicación principal](assets/android-main-app.PNG)

* Expanda la carpeta [!DNL Gradle Scripts]. Haga doble clic en [!DNL build.gradle] del módulo. Pegue las siguientes dependencias en la sección de dependencias del archivo [!DNL build.gradle]. El archivo de [!DNL build.gradle] debería tener el siguiente aspecto

<!--
Removed `{.line-numbers}` below
-->

```java
implementation 'com.adobe.marketing.mobile:campaign:1.+'
implementation 'com.adobe.marketing.mobile:userprofile:1.+'
implementation 'com.adobe.marketing.mobile:sdk-core:1.+'
```

![gradle de módulo](assets/module-build-gradle.PNG)

* Sincroniza tu proyecto [!DNL Android] haciendo clic en el botón sincronizar ahora para sincronizar tu proyecto

## Modificar [!DNL AndroidManifest.xml]{#modify-android-manifest}

Abra *AndroidManifest.xml* y pegue las 2 líneas siguientes después del elemento de manifiesto y antes del elemento de aplicación. Esto permite que la aplicación se comunique con el mundo exterior

<!--
Removed `{.line-numbers}` below
-->

```xml
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

Copie la línea siguiente en el elemento de aplicación
[!DNL android:name=&quot;.MainApp&quot;]
Guarde su [!DNL AndroidManifest.xml]
Su [!DNL AndroidManifest.xml] debe tener un aspecto similar al siguiente

<!--
Removed `{.line-numbers}` below
-->

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.example.acspushtutorial">
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

<activity android:name=".MainActivity">
<intent-filter>
    <action android:name="android.intent.action.MAIN" />
    <category android:name="android.intent.category.LAUNCHER" />
</intent-filter>
</activity>
</application>

</manifest>
```
