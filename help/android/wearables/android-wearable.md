---
description: A partir de la versión 4.5 del SDK para Android, se ha añadido una nueva extensión de Android que le permitirá recopilar datos de su aplicación Android Wearable.
seo-description: A partir de la versión 4.5 del SDK para Android, se ha añadido una nueva extensión de Android que le permitirá recopilar datos de su aplicación Android Wearable.
seo-title: Introducción a Android Wearables
solution: Marketing Cloud, Analytics
title: Introducción a Android Wearables
topic: Desarrollador e implementación
uuid: bfe 5 d 41 e-b 17 c -4634-80 ac -7 a 38671 ecb 81
translation-type: tm+mt
source-git-commit: 46a0b8e0087c65880f46545a78f74d5985e36cdc

---


# Android Wearables: getting started{#android-wearables-getting-started}

A partir de la versión 4.5 del SDK para Android, se ha añadido una nueva extensión de Android que le permitirá recopilar datos de su aplicación Android Wearable.

## Configuring the SDK for a handheld app (Android Studio) {#section_262237484EC44C58953891B105F0D000}

Para obtener más información sobre la importación del SDK en su proyecto, consulte [Implementación principal y Ciclo vital](/help/android/getting-started/dev-qs.md).

1. Añada el archivo `ADBMobileConfig.json` a la carpeta de recursos de su proyecto.
1. Añada el archivo `adobeMobileLibrary-*.jar` a la carpeta de bibliotecas o asegúrese de que el proyecto haga referencia a este archivo.

   >[!TIP]
   >
   >You might need to sync the gradle project after adding the `.jar` file.

1. En el método `onCreate`, permita al SDK acceder al contexto de la aplicación utilizando `Config.setContext`:

   ```java
   @Override 
   public void onCreate(Bundle savedInstanceState) { 
       super.onCreate(savedInstanceState); 
       setContentView(R.layout.main); 
   
       // Allow the SDK access to the application context 
       Config.setContext(this.getApplicationContext()); 
   }
   ```

1. Agregue el siguiente código al `AndroidManifest.xml` archivo:

   ```java
       <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" /> 
       <uses-permission android:name="android.permission.INTERNET" /> 
       <uses-permission android:name="android.permission.READ_PHONE_STATE" /> 
   
   <application> 
   ....... 
   <meta-data android:name="com.google.android.gms.version" 
               android:value="@integer/google_play_services_version" /> 
   </application>
   ```

1. Asegúrese de que el proyecto incluya la biblioteca de servicios de Google Play.
1. Implement `WearableListenerService` or add the corresponding code to your `WearableListenerService`:

   ```java
   public class WearListenerService extends WearableListenerService { 
   
       @Override 
       public void onMessageReceived(MessageEvent messageEvent) { 
           super.onMessageReceived(messageEvent); 
       } 
   
       private GoogleApiClient mGoogleApiClient; 
   
       @Override 
       public void onCreate() { 
           super.onCreate(); 
           mGoogleApiClient = new GoogleApiClient.Builder(this) 
                   .addApi(Wearable.API) 
                   .build(); 
           mGoogleApiClient.connect(); 
       } 
       @Override 
       public void onDestroy() { 
           super.onDestroy(); 
           mGoogleApiClient.disconnect(); 
       } 
   
       @Override 
       public void onDataChanged(com.google.android.gms.wearable.DataEventBuffer dataEvents) { 
           DataListenerHandheld.onDataChanged(dataEvents, mGoogleApiClient, this); 
       } 
   }
   ```

1. Agregar `WearListenerService` al `AndroidManifest.xml` archivo:

   ```java
   If you are using Google Play Services  < 8.2 
   <application> 
       ...... 
        <service 
               android:name=".WearListenerService" > 
               <intent-filter> 
                   <action android:name="com.google.android.gms.wearable.BIND_LISTENER" /> 
               </intent-filter> 
       </service> 
   </application> 
   If you are using Google Play Services >= 8.2 
   <application> 
       ...... 
        <service 
               android:name=".WearListenerService" > 
               <intent-filter> 
                     <action android:name="com.google.android.gms.wearable.DATA_CHANGED" /> 
                    <data android:scheme="wear" android:host="*" android:pathPrefix="/abdmobile" /> 
               </intent-filter> 
       </service> 
   </application> 
   
   Please find more information from google's blog https://android-developers.googleblog.com/2016/04/deprecation-of-bindlistener.html. 
   Permalink Edit
   ```

## Configuring the SDK for a Wearable app (Android Studio) {#section_2268EC03E20B4A228A28BDCFEA2E9AE4}

1. Complete una de las siguientes tareas:

   * Añada el mismo archivo `ADBMobileConfig.json` a la carpeta de recursos de su proyecto Wearable.
   * Cambie la configuración de gradle para utilizar `ADBMobileConfig.json` en la carpeta de recursos de la aplicación de mano:

      ```java
      android { 
      
          sourceSets { 
              main { 
                  assets.srcDirs = ['src/main/assets','../mobile/src/main/assets'] 
              } 
         } 
      }
      ```

1. Añada el archivo `adobeMobileLibrary-*.jar` a la carpeta de librerías o asegúrese de que el proyecto hace referencia a él.

   Es posible que deba sincronizar el proyecto de gradle después de agregar el archivo jar.

1. En el método `onCreate`, permita al SDK acceder al contexto de la aplicación utilizando `Config.setContext`:

   ```java
   @Override 
   public void onCreate(Bundle savedInstanceState) { 
       super.onCreate(savedInstanceState); 
       setContentView(R.layout.main);      
       // Allow the SDK access to the application context 
       Config.setContext(this.getApplicationContext(), Config.ApplicationType.APPLICATION_TYPE_WEARABLE); 
   }
   ```

1. Añada el siguiente código a `AndroidManifest.xml`:

   ```java
   <application> 
   ....... 
   <meta-data android:name="com.google.android.gms.version" 
               android:value="@integer/google_play_services_version" /> 
   </application>
   ```

1. Asegúrese de que el proyecto incluya la biblioteca de servicios de Google Play.
1. Implement `WearableListenerService` or add the corresponding code to your `WearableListenerService`:

   ```java
   public class WearListenerService extends WearableListenerService { 
   
       @Override 
       public void onDataChanged(com.google.android.gms.wearable.DataEventBuffer dataEvents) { 
           DataListenerWearable.onDataChanged(dataEvents); 
       } 
   
   }
   ```

1. Agregar `WearListenerService` al `AndroidManifest.xml` archivo:

   ```java
   If you are using Google Play Services  < 8.2 
   <application> 
       ...... 
        <service 
               android:name=".WearListenerService" > 
               <intent-filter> 
                   <action android:name="com.google.android.gms.wearable.BIND_LISTENER" /> 
               </intent-filter> 
       </service> 
   </application> 
   If you are using Google Play Services >= 8.2 
   <application> 
       ...... 
        <service 
               android:name=".WearListenerService" > 
               <intent-filter> 
                     <action android:name="com.google.android.gms.wearable.DATA_CHANGED" /> 
                    <data android:scheme="wear" android:host="*" android:pathPrefix="/abdmobile" /> 
               </intent-filter> 
       </service> 
   </application> 
   Please find more information from google's blog https://android-developers.googleblog.com/2016/04/deprecation-of-bindlistener.html. 
   Permalink Edit
   ```
