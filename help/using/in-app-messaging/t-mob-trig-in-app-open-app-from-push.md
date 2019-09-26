---
description: Puede configurar el activador de mensajes en la aplicación para que este sea el ID del mensaje push que se envía cuando un usuario abre la aplicación mediante el mensaje push.
seo-description: Puede configurar el activador de mensajes en la aplicación para que este sea el ID del mensaje push que se envía cuando un usuario abre la aplicación mediante el mensaje push.
seo-title: Activador de mensajes en la aplicación al abrirla mediante un mensaje push
title: Activador de mensajes en la aplicación al abrirla mediante un mensaje push
uuid: e 1 c 8 e 29 d -1 c 2 b -47 b 2-8 ab 2-6 b 6 e 15 df 86 f 6
translation-type: tm+mt
source-git-commit: 114bce95e41c8e13695689dd2da2dbc04cb17ad7

---


# Trigger an in-app message when the app is opened from a push message{#trigger-an-in-app-message-when-the-app-is-opened-from-a-push-message}

Puede configurar el activador de mensajes en la aplicación para que este sea el ID del mensaje push que se envía cuando un usuario abre la aplicación mediante el mensaje push.

1. Obtenga el ID del mensaje push que se enviará al usuario.

   Puede encontrar el ID del mensaje push en la URL durante el flujo de trabajo de creación del mensaje.

   Vea el siguiente ejemplo:

   ![](assets/brandon_task1.png)

1. Guarde y active el mensaje en la aplicación con el siguiente activador:

   `“a.push.payloadID” =`

   >[!TIP]
   >
   >El ID de mensaje push es el ID que se encuentra en el paso 1.

   El activador debe añadirse manualmente, ya que no está disponible en la lista desplegable **[!UICONTROL Activador].**

   ![](assets/brandon_task2.png)

1. Guarde y envíe el mensaje push que tenga el ID de push del paso 1.
1. Haga clic en el mensaje push para abrir la aplicación y verificar que el mensaje en la aplicación se muestre al abrirla.

   Mientras efectúe las pruebas pertinentes, recuerde la siguiente información:

   * Tras guardar el mensaje en la aplicación, el archivo de configuración hospedado tarda unos 45 segundos en actualizarse con el mensaje nuevo.
   * La aplicación busca actualizaciones del archivo de configuración (el mensaje en la aplicación nuevo) cuando hay un lanzamiento **nuevo**, por lo que debe asegurarse de que la aplicación esté efectuando un nuevo lanzamiento al hacer clic en el mensaje push.
   Esto normalmente significa que deberá asegurarse de haber agotado el tiempo de espera de la sesión. El tiempo de espera predeterminado es de 5 minutos.
