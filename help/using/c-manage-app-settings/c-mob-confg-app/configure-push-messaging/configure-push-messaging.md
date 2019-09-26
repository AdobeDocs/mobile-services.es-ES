---
description: Puede usar esta información para configurar las opciones de los servicios push en la página Administrar configuración de aplicación a la hora de crear una aplicación nueva o editar una existente.
keywords: móvil
seo-description: Puede usar esta información para configurar las opciones de los servicios push en la página Administrar configuración de aplicación a la hora de crear una aplicación nueva o editar una existente.
seo-title: Configurar la mensajería push
solution: Marketing Cloud, Analytics
title: Configurar la mensajería push
topic: Métricas
uuid: 6763858 d -6046-4 d 36-87 c 0-cf 3600 a 44 fb 1
translation-type: tm+mt
source-git-commit: 2c85c31d2fa54de26771553a6d349d3101e0048c

---


# Configure push messaging{#configure-push-messaging}

Puede utilizar esta información para configurar las opciones de los servicios push en la página Administrar configuración de aplicación al crear una aplicación nueva o editar una existente.

Antes de configurar la mensajería push, complete las tareas previas en [Requisitos previos para activar la mensajería push](/help/using/c-manage-app-settings/c-mob-confg-app/configure-push-messaging/prerequisites-push-messaging.md).

* **Consideraciones sobre los grupos de informes**

   Puede configurar una aplicación de tienda de aplicaciones para Apple y otra para Google en cada grupo de informes. Si necesita más aplicaciones, por ejemplo, una para un entorno de producción y otra para uno de desarrollo, configure una aplicación de tienda de aplicaciones y un grupo de informes para cada entorno.

>[!IMPORTANT]
>
>No se admite la transferencia de la aplicación a un nuevo grupo de informes. En caso de hacerlo, podría desajustarse la configuración de push y los mensajes no se enviarían.

1. En **[!UICONTROL Servicios push, rellene los siguientes campos]**:

   * Apple

      **[!UICONTROL Clave privada]**

      Browse to and select your valid private key `.p12`, `.key`, or `.pen`.

      >[!IMPORTANT]
      >If the file that you select for the **[!UICONTROL Private Key]** input also contains a certificate, you do not need to specify the certificate.

   * **[!UICONTROL Certificado]**

      Especifique un certificado válido. Esta opción solo es necesaria si la entrada de **[!UICONTROL Clave privada]** **no** contiene ningún certificado. Para obtener más información sobre cómo obtener el certificado SSL y la clave privada, consulte [Configurar aplicación para utilizar APNS o FCM](/help/using/c-manage-app-settings/c-mob-confg-app/configure-push-messaging/configure-app-apns-gcm.md).

   * Google

      **[!UICONTROL Clave de API]**

      Especifique una clave de API válida. Para obtener más información sobre cómo obtener la clave de API, consulte [Configurar aplicación para utilizar APNS o FCM](/help/using/c-manage-app-settings/c-mob-confg-app/configure-push-messaging/configure-app-apns-gcm.md).

      Para obtener más información, consulte los temas siguientes:

      * [Mensajería push en Android](/help/android/messaging-main/push-messaging/push-messaging.md)
      * [Mensajería push en iOS](/help/ios/messaging-main/push-messaging/push-messaging.md)

1. Haga clic en **[!UICONTROL Guardar]**.