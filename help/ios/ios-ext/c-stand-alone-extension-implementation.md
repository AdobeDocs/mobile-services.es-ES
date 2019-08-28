---
description: A partir de iOS 10, Apple permite la creación de una extensión llamada extensión independiente, que puede distribuirse sin necesidad de aplicación contenedora. De este modo, no se necesita un grupo de aplicaciones, ya que no hay ninguna aplicación contenedora con la que compartir datos.
seo-description: A partir de iOS 10, Apple permite la creación de una extensión llamada extensión independiente, que puede distribuirse sin necesidad de aplicación contenedora. De este modo, no se necesita un grupo de aplicaciones, ya que no hay ninguna aplicación contenedora con la que compartir datos.
seo-title: Implementación de extensiones independientes
solution: Marketing Cloud, Analytics
title: Implementación de extensiones independientes
topic: Desarrollador e implementación
uuid: 9 b 47 f 082-b 78 f -4611-968 d -014 c 32 ede 6 bc
translation-type: tm+mt
source-git-commit: e481b046769c3010c41e1e17c235af22fc762b7e

---


# Stand-alone extension implementation {#stand-alone-extension-implementation}

A partir de iOS 10, Apple permite la creación de una extensión llamada extensión independiente, que puede distribuirse sin necesidad de aplicación contenedora. De este modo, no se necesita un grupo de aplicaciones, ya que no hay ninguna aplicación contenedora con la que compartir datos.

>[!IMPORTANT]
>
>Para utilizar extensiones independientes, debe tener la versión 4.13.0 o posterior del SDK móvil.

## Configurar la extensión independiente para su uso con el SDK {#section_B7A84603BB9D4B48BB46BE8D3B9E3CF0}

Para configurar su extensión independiente:

1. Ensure that the `ADBMobileConfig.json` file is a member of your extension's target.
1. Vincule las siguientes bibliotecas y marcos:

   * `AdobeMobileLibrary_Extension.a`
   * `libsqlite3.tbd`
   * `SystemConfiguration.framework`

1. En el controlador de vista principal de la extensión, establezca el tipo de extensión en `ADBMobileAppExtensionTypeStandAlone` en el SDK antes de completar cualquier actividad relacionada con el SDK.

   ```objective-c
   [ADBMobile setAppExtensionType:ADBMobileAppExtensionTypeStandAlone];
   ```

1. Confirme que la aplicación se compila sin errores inesperados.

## Additional notes {#section_1C9A55E2309A44BF842310F735702B3D}

Alguna información adicional:

* Se ha agregado un valor de contexto adicional, `a.RunMode`, para indicar si los datos proceden de la aplicación contenedora o de la extensión:

   * `a.RunMode = Application`

      Este valor significa que la visita procede de la aplicación contendora.
   * `a.RunMode = Extension`

      Este valor significa que la visita procede de la extensión.

* En las aplicaciones de extensión iOS no se activa ninguna llamada de ciclo vital.
