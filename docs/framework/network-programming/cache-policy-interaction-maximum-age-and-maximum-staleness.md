---
title: "Interacci&#243;n de la directiva de cach&#233;, antig&#252;edad m&#225;xima y obsolencia m&#225;xima | Microsoft Docs"
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
  - "obsolencia máxima"
  - "actualización de los recursos almacenados en caché"
  - "tiempo, recursos almacenados en caché"
  - "directiva de antigüedad máxima"
  - "obsolescencia de los recursos almacenados en caché"
  - "antigüedad de los recursos almacenados en caché"
ms.assetid: 7f775925-89a1-4956-ba90-c869c1749a94
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# Interacci&#243;n de la directiva de cach&#233;, antig&#252;edad m&#225;xima y obsolencia m&#225;xima
Para asegurarse de que el contenido más reciente se devuelto a la aplicación cliente, la interacción de la directiva de caché del cliente y los requisitos de volver a validar de servidor generan siempre a la directiva más conservadora de caché.  Todos los ejemplos de este tema muestran la directiva de caché para un recurso que está almacenado en memoria caché el 1 de enero y expira el 4 de enero.  
  
 En los ejemplos siguientes, el valor máximo de deterioro \(`maxStale`\) se utiliza junto con una edad máxima \(`maxAge`\):  
  
-   Si la directiva de caché establece `maxAge` \= 5 días y no especifica un valor de `maxStale` , según el valor de `maxAge` , el contenido se puede hasta el 6 de enero.  Sin embargo, según los requisitos de volver a validar de servidor, el contenido expira el 4 de enero.  Dado que la fecha de expiración de contenido es más conservadora \(antes\), tiene prioridad sobre la directiva de `maxAge` .  Por consiguiente, el contenido expira el 4 de enero y debe aunque volverá a su edad máxima no se ha cumplido.  
  
-   Si la directiva de caché establece `maxAge` \= 5 días y `maxStale` \= 3 días, según el valor de `maxAge` , el contenido se puede hasta el 6 de enero.  Según el valor de `maxStale` , el contenido se puede hasta el 7 de enero.  Por consiguiente, el contenido obtiene el 6 de enero volverá.  
  
-   Si la directiva de caché establece `maxAge` \= 5 días y `maxStale` \= 1 día, según el valor de `maxAge` , el contenido se puede hasta el 6 de enero.  Según el valor de `maxStale` , el contenido se puede hasta el 5 de enero.  Por consiguiente, el contenido obtiene el 5 de enero volverá.  
  
 Cuando la edad máxima es menor que la fecha de expiración de contenido, el comportamiento del almacenamiento en caché más conservador prevalece siempre y el valor máximo de deterioro no tiene ningún efecto.  Los ejemplos siguientes se muestra el efecto de establecer un valor máximo de deterioro \(`maxStale`\) cuando se alcanza la edad máxima \(`maxAge`\) antes de que expire el contenido:  
  
-   Si la directiva de caché establece `maxAge` \= 1 día y no especifica un valor por valor de `maxStale` , el contenido el 2 de enero volverá aunque no haya expirado.  
  
-   Si la directiva de caché establece`maxAge` \= 1 día y `maxStale` \= 3 días, el contenido el 2 de enero volverá a aplicar el valor más conservador de la directiva.  
  
-   Si la directiva de caché establece `maxAge` \= 1 día y `maxStale` \= 1 día, el contenido el 2 de enero volverá.  
  
## Vea también  
 [Administración de la memoria caché para aplicaciones de red](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [Directiva de caché](../../../docs/framework/network-programming/cache-policy.md)   
 [directivas de caché basadas en la ubicación](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [directivas de caché de duración definida](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [Configurar el almacenamiento en caché de las aplicaciones de red](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)   
 [Interacción de la directiva de caché, antigüedad máxima y actualización mínima](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-minimum-freshness.md)