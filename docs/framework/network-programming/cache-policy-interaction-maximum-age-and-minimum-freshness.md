---
title: "Interacci&#243;n de la directiva de cach&#233;, antig&#252;edad m&#225;xima y actualizaci&#243;n m&#237;nima | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "directivas de caché de duración definida"
  - "Revalidar la directiva"
  - "caché [.NET Framework], directivas de duración definida"
  - "actualización de los recursos almacenados en caché"
  - "directiva de antigüedad máxima"
  - "directiva de actualización mínima"
  - "antigüedad de los recursos almacenados en caché"
ms.assetid: 6567d451-ecec-496c-95a3-a415b99ba52a
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Interacci&#243;n de la directiva de cach&#233;, antig&#252;edad m&#225;xima y actualizaci&#243;n m&#237;nima
Para asegurarse de que el contenido más reciente se devuelto a la aplicación cliente, la interacción de la directiva de caché del cliente y los requisitos de volver a validar de servidor generan siempre a la directiva más conservadora de caché.  Todos los ejemplos de este tema muestran la directiva de caché para un recurso que está almacenado en memoria caché el 1 de enero y expira el 4 de enero.  
  
 Los ejemplos siguientes muestran la directiva de caché que los resultados de interacción age máxima \(`maxAge`\) y los valores mínimos de la actualización \(`minFresh`\).  
  
-   Si la directiva de caché establece `maxAge` \= 2 días y `minFresh` no se especifica, el contenido el 3 de enero volverá.  
  
-   Si la directiva de caché establece `maxAge` \= 2 días y `minFresh` \= 1 día, como `maxAge`, el contenido es nuevo hasta el 3 de enero.  Como `minFresh`, el contenido es nuevo hasta el 3 de enero.  Por consiguiente, el contenido se debe el 3 de enero volverá.  
  
-   Si la directiva de caché establece `maxAge`\= 2 días y `minFresh` \= 2 días, como `maxAge`, el contenido es nuevo hasta el 3 de enero.  Como `minFresh` el contenido es nuevo hasta el 2 de enero.  Por consiguiente, el contenido se debe el 2 de enero volverá.  
  
## Vea también  
 [Administración de la memoria caché para aplicaciones de red](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [Directiva de caché](../../../docs/framework/network-programming/cache-policy.md)   
 [directivas de caché basadas en la ubicación](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [directivas de caché de duración definida](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [Configurar el almacenamiento en caché de las aplicaciones de red](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)   
 [Interacción de la directiva de caché, antigüedad máxima y obsolencia máxima](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-maximum-staleness.md)