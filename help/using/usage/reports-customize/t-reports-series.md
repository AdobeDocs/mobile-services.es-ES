---
description: Esta información sirve para personalizar los informes integrados mediante la adición de series (métricas) adicionales o aplicaciones en distintos grupos de informes para comparar los datos.
keywords: móvil
solution: Experience Cloud Services,Analytics
title: Agregar series (métricas) a informes
topic-fix: Reports,Metrics
uuid: 84fdfb1f-70e6-4c02-9b3b-526e9c924f74
exl-id: 1b1356c6-7f62-4b88-996a-09ed33b19c9d
source-git-commit: 7cfaa5f6d1318151e87698a45eb6006f7850aad4
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 100%

---

# Agregar series (métricas) a informes {#add-series-metrics-to-reports}

{#eol}

Esta información sirve para personalizar los informes integrados mediante la adición de series (métricas) adicionales o aplicaciones en distintos grupos de informes para comparar los datos.

>[!IMPORTANT]
>
>Las métricas de aplicación de móvil también están disponibles en los informes y análisis de marketing, los análisis específicos, el almacén de datos y otras interfaces de generación de informes de Analytics. Si un tipo de informe o desglose no está disponible en Adobe Mobile, se puede generar usando otra interfaz de generación de informes.

En este ejemplo, personalizaremos el informe **[!UICONTROL Usuarios y sesiones]**, pero las instrucciones se pueden aplicar para cualquier informe.

1. Abra la aplicación y haga clic en **[!UICONTROL Uso]** > **[!UICONTROL Usuarios y sesiones]**.

   ![Resultado de los pasos](assets/customize1.png)

   Este informe proporciona una vista completa de las horas extra de los usuarios de la aplicación. Sin embargo, queremos agregar una serie para informar sobre bloqueos de aplicaciones.

1. Haga clic en **[!UICONTROL Personalizar]**.

   ![Resultado de los pasos](assets/customize2.png)

1. Desplácese hacia abajo y haga clic en **[!UICONTROL Agregar serie]**.

   El nombre de la serie se rellena con el mismo nombre que la última serie de la lista. En la ilustración anterior, la última serie es **[!UICONTROL Descargas de App Store]**, de modo que se agrega una serie nueva que también se llama **[!UICONTROL Descargas de App Store]**.

1. Complete una de las siguientes tareas:

   * Para agregar una serie (métrica) nueva, haga clic en el nombre de la que acaba de crear y seleccione una nueva métrica de ciclo de vida en la lista desplegable.

      ![Resultado de los pasos](assets/add_series.png)

   * Si quiere agregar una aplicación nueva en un grupo de informes diferente para poder comparar los datos de distintas aplicaciones, haga clic en el nombre de la aplicación en la serie recién creada y seleccione la aplicación que desee.

      ![](assets/add_series_app.png)

1. (Condicional) Agregue filtros a la serie nueva.

   Para obtener más información, consulte [Adición de filtros a informes](/help/using/usage/reports-customize/t-reports-customize.md).
1. Haga clic en **[!UICONTROL Actualizar]** y **[!UICONTROL Ejecutar]**.
