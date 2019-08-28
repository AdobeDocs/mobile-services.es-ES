---
description: El valor de duración le permite medir un valor de duración para cada usuario de Android y tomarlo como destino. El valor puede utilizarse para almacenar compras acumuladas, visualizaciones de anuncios, visualizaciones de vídeo completas, usos compartidos en medios sociales, cargas de fotografías, etcétera.
seo-description: El valor de duración le permite medir un valor de duración para cada usuario de Android y tomarlo como destino. El valor puede utilizarse para almacenar compras acumuladas, visualizaciones de anuncios, visualizaciones de vídeo completas, usos compartidos en medios sociales, cargas de fotografías, etcétera.
seo-title: Valor de duración de visitantes
solution: Marketing Cloud, Analytics
title: Valor de duración de visitantes
topic: Desarrollador e implementación
uuid: ba 0308 de -282 e -46 f 9-a 14 c -19 fb 6 d 5 c 363 e
translation-type: tm+mt
source-git-commit: bf076aa8e59d5c3e634fc4ae21f0de0d4541a83f

---


# Visitor lifetime value {#visitor-lifetime-value}

El valor de duración le permite medir un valor de duración para cada usuario de Android y tomarlo como destino. El valor puede utilizarse para almacenar compras acumuladas, visualizaciones de anuncios, visualizaciones de vídeo completas, usos compartidos en medios sociales, cargas de fotografías, etcétera.

Cada vez que envía un valor con `trackLifetimeValueIncrease`, el valor se agrega al valor existente. El valor de duración se almacena en el dispositivo y se puede recuperar en cualquier momento realizando una llamada a `lifetimeValue`.

## Track the visitor lifetime value {#section_390943A49AF841F2941E65D6DF2B3F5A}

1. Agregue la [biblioteca al proyecto e implemente el ciclo vital.

   Para obtener más información, consulte *Agregar el SDK y el archivo de configuración a su proyecto intellij IDEA o Eclipse* en [implementación y ciclo vital de Core](/help/android/getting-started/dev-qs.md).
1. Importe la biblioteca:

   ```java
   import com.adobe.mobile.*;
   ```

1. Llame a `trackLifetimeValueIncrease` con la cantidad en que aumenta el valor:

   ```java
   Analytics.trackLifetimeValueIncrease(BigDecimal.valueOf(5.0), null);
   ```

## Send additional data {#section_3EBE813E54A24F6FB669B2478B5661F9}

Además del valor de duración, puede enviar datos de contexto adicionales con cada llamada de seguimiento de acción:

```java
HashMap cdata = new HashMap<String, Object>(); 
cdata.put("myapp.ImageLiked", imageName); 
Analytics.trackLifetimeValueIncrease(BigDecimal.valueOf(5.0), cdata);
```

El valor de los datos de contexto debe asignarse a variables personalizadas de Adobe Mobile Services:

![](assets/map-variable-context-ltv.png)
