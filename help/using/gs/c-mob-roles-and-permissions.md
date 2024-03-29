---
description: En Adobe Analytics, puede administrar los roles en la página principal de las herramientas de administración.
title: Roles y permisos
uuid: ad350f8d-ef51-4519-98aa-3025bc0f5588
exl-id: 70f0b427-60d5-4a79-a8d3-e03274edd917
source-git-commit: 7cfaa5f6d1318151e87698a45eb6006f7850aad4
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 49%

---

# Roles y permisos{#roles-and-permissions}

{#eol}

En Adobe Analytics, puede administrar los roles en la página principal de las herramientas de administración.

## Información general {#section_91B8192891E14E5285718C8118912500}

Los roles siguientes administran los permisos en la interfaz de usuario de Mobile Services:

### Administrador de Analytics

Un administrador de Analytics administra grupos de usuarios y asigna permisos, uno de los cuales es el de los administradores de aplicaciones móviles. El administrador del Experience Cloud vincula su Adobe ID a su cuenta de Adobe Analytics, lo que le permite iniciar sesión en la interfaz de usuario de Mobile Services con su Adobe ID. Para obtener más información sobre el administrador de Experience Cloud, consulte [Administración de usuarios y productos de Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=es) en la guía Componentes de la interfaz central de Experience Cloud.

>[!TIP]
>
>Un administrador existente de Analytics tiene la capacidad de asignar el rol de administrador de Analytics a cualquier usuario.

### Administrador de aplicaciones móviles

Este rol es el administrador de la interfaz de usuario de Mobile Services.

>[!IMPORTANT]
>
>En algunas funciones, como la mensajería push, el administrador de Analytics debe seleccionar la casilla de verificación **[!UICONTROL Creación de segmentos]** en Administración de usuarios.

## Administración del acceso {#section_E6939C2695AA4A0DBF432D50B2670920}

A continuación, presentamos información adicional sobre el acceso a las opciones en la interfaz de usuario de Mobile Services:

### Aplicaciones y grupos de informes

Todas las aplicaciones de Mobile Services están vinculadas a los grupos de informes. Si los usuarios no tienen acceso a un grupo de informes, no tendrán acceso a la aplicación asociada a dicho grupo de informes.

### Funciones de Mobile Services y Analytics

Si su empresa no tiene un contrato de Analytics para acceder a alguna función de la interfaz de usuario, como la mensajería push, ningún usuario de la empresa tendrá acceso a ella, sea cual sea su nivel de permiso.

## Roles y permisos {#section_20AA029D5B8C413C8659777E79B11620}

Estos son los roles de la interfaz de usuario de Mobile Services y sus respectivos permisos:

### Administrador de Analytics permissions

* Todos los permisos de administración de usuarios y aplicaciones móviles
* Crear aplicación con nuevo grupo de informes
* Eliminar aplicación de Mobile Services

   >[!IMPORTANT]
   >
   >Aunque la aplicación se haya eliminado en la interfaz de usuario de Mobile Services, el grupo de informes sigue existiendo en Analytics.

* Administrar configuración de aplicación

   * Habilitar informes de ciclo vital
   * Activar informes de ubicación
   * Crear/actualizar/eliminar variables y métricas

### Administrador de aplicaciones móviles permissions

* Todos los permisos de usuario
* Crear aplicación con grupo de informes existente
* Administrar configuración de aplicación

   * Configurar las opciones del SDK móvil de la aplicación
   * Configuración de la IU de la aplicación
   * Configuración de aplicaciones de App Store vinculadas
   * Configurar las opciones de vínculo universal de la aplicación
   * Configuración de certificados de servicios push y claves API
   * Crear/actualizar/activar/desactivar/duplicar/archivar/eliminar postbacks
   * Crear/actualizar/archivar/eliminar destinos de vínculo

* Crear/actualizar/archivar vínculos de marketing
* Crear/importar/actualizar/eliminar vínculos de adquisición heredados
* Crear/importar/actualizar/eliminar configuración de lugares (puntos de interés)
* Crear/actualizar/enviar/programar/cancelar/duplicar/archivar/eliminar mensajes push
* Crear/actualizar/activar/desactivar/duplicar/archivar/eliminar mensajes en la aplicación

Para obtener más información sobre grupos y usuarios, consulte los siguientes temas en la documentación de Adobe Analytics:

* [Configuración de grupos de usuarios (heredada)](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/home.html?lang=es)
* [Agregar un usuario a un grupo](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/home.html?lang=es)

### Usuario de Mobile Services

Esta función tiene permisos de solo vista y puede proporcionar comentarios en la interfaz de usuario de Mobile Services.

* Proporcionar comentarios sobre la interfaz de usuario de Mobile Services
* Ver aplicaciones

   >[!IMPORTANT]
   >
   >Los usuarios solo pueden ver los grupos de informes a los que tienen acceso en Adobe Analytics.

* Ver configuración de la aplicación

   * Descargar configuración de App SDK
   * Ver toda la configuración de IU y SDK
   * Ver la configuración de variables y métricas
   * Ver postbacks
   * Ver destinos de vínculo

* Ver y ejecutar informes
* Ver vínculos de marketing
* Ver y exportar vínculos de adquisición heredados
* Ver y exportar la configuración de lugares (puntos de interés)
* Ver mensajes push
* Ver mensajes en la aplicación
