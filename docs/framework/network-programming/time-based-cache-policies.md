---
title: "directivas de cach&#233; de duraci&#243;n definida | Microsoft Docs"
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
  - "directiva de fecha de sincronización de caché"
  - "caché [.NET Framework], directivas de duración definida"
  - "actualización de los recursos almacenados en caché"
  - "tiempo, recursos almacenados en caché"
  - "directiva de antigüedad máxima"
  - "sincronización, caché"
  - "obsolescencia de los recursos almacenados en caché"
  - "directivas de caché predeterminadas de duración definida "
  - "directiva de obsolescencia máxima"
  - "directivas de caché de contenido"
  - "contenido caducado"
  - "directiva de actualización mínima"
  - "antigüedad de los recursos almacenados en la caché"
ms.assetid: 74f0bcaf-5c95-40c1-9967-f3bbf1d2360a
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# directivas de cach&#233; de duraci&#243;n definida
Una directiva Tiempo\- basada de caché define la actualización de entradas almacenadas en caché utilizando el tiempo que recuperada el recurso, los encabezados devueltos al recurso, y la hora actual.  Al establecer una directiva Tiempo\- basada de caché, puede utilizar la directiva Tiempo\- basada <xref:System.Net.Cache.HttpRequestCacheLevel> o crear una directiva Tiempo\- basada personalizada.  Al utilizar la directiva Tiempo\- basada predeterminado para los recursos recopilados mediante el Protocolo de transferencia de hipertexto \(HTTP\), el comportamiento exacto de caché está determinado por los encabezados incluidos en la respuesta almacenada en memoria caché y los comportamientos especificados en las secciones 13 y 14 de RFC 2616, disponible en [http:\/\/www.ietf.org](http://www.ietf.org/).  Para obtener un ejemplo de código que muestra cómo establecer el valor predeterminado Tiempo\- según la directiva para los recursos de HTTP, vea [Cómo: Establezca la Directiva Tiempo\- Basada predeterminado de caché para una aplicación](../../../docs/framework/network-programming/how-to-set-the-default-time-based-cache-policy-for-an-application.md).  Para obtener ejemplos de código que muestran cómo crear y utilizar las directivas de caché, vea [El almacenamiento en caché de configuración en aplicaciones de red](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md).  
  
## Criterios para determinar Freshness de entradas almacenadas en caché  
 Para personalizar una directiva Tiempo\- basada de caché, puede especificar que una o más de los siguientes criterios se utilizan para determinar la actualización de entradas almacenadas en caché:  
  
-   Edad máxima  
  
-   Deterioro máximo  
  
-   Actualización mínima  
  
-   Fecha de sincronización de caché  
  
> [!NOTE]
>  Mediante la directiva Tiempo\- basada predeterminado de la memoria caché no debe confundirse con establecer una directiva predeterminada de la aplicación.  La directiva Tiempo\- basada predeterminado es una directiva concreta que se puede utilizar a petición o nivel de aplicación.  La directiva predeterminada de caché de la aplicación es una directiva \(ubicación\- basada o Tiempo\- basada\) que tendrá efecto cuando no se establece ninguna directiva en una solicitud.  Para obtener información detallada sobre cómo establecer una directiva predeterminada de caché de la aplicación, vea <xref:System.Net.WebRequest.DefaultCachePolicy%2A>.  
  
### Edad máxima  
 El criterio máximo de directiva age especifica la cantidad de tiempo que una copia en caché de un recurso se puede usar.  Si la copia en caché de recursos es más antigua que el tiempo especificado, el recurso volverá debe comprobar con el contenido del servidor.  Si la edad máxima permitiría que utilizaran el recurso después de que expire, este los criterios no se admiten a menos que un valor máximo de deterioro también se especifique.  
  
### Deterioro máximo  
 El criterio máximo de directivas del deterioro especifica el intervalo de tiempo después de la expiración del contenido que la copia en caché de recursos puede utilizar.  Éste es el único criterio de la directiva de caché que permite que utilicen los recursos después de que haya expirado.  
  
### Actualización mínima  
 El criterio mínimo de la directiva de la actualización especifica el período de tiempo antes de la expiración del contenido que la copia en caché de recursos puede utilizar.  Esta directiva tiene el efecto de hacer que una entrada de caché expire antes de la fecha de expiración; por consiguiente, la actualización y los valores mínimos de deterioro de máximo son mutuamente excluyentes.  
  
## Fecha de sincronización de caché  
 El criterio de la directiva de fecha de sincronización de caché determina cuando una copia en caché de un recurso volverá debe comprobar con el contenido del servidor.  Si el contenido ha cambiado desde que el elemento se ha almacenado en caché, se recupera del servidor, se almacena en caché, y se devuelve a la aplicación.  Si el contenido no ha cambiado, se actualiza la marca de tiempo y la aplicación obtiene el contenido almacenado en caché.  
  
 La fecha de sincronización de caché permite especificar una fecha absoluta en la que debe volver a validarse el contenido almacenado en memoria caché.  Si una nueva entrada de caché volverá en último lugar antes de la fecha de sincronización de caché, al volver a validar con el servidor todavía aparece.  Si la entrada de caché volverá después de la fecha de sincronización de caché y que no es ningún requisito adicional de volver a validar de la actualización o servidor que reemplaza la entrada almacenada en memoria caché, la entrada de caché se utiliza.  Si la fecha de sincronización de caché se establece en una fecha futura, la entrada se vuelve a validar cada vez que se solicita, hasta que pasa la fecha de sincronización de caché.  
  
 Los temas siguientes proporcionan información sobre los efectos de combinar criterios Tiempo\- en función de la directiva de caché:  
  
-   [Interacción de la directiva de caché, antigüedad máxima y obsolencia máxima](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-maximum-staleness.md)  
  
-   [Interacción de la directiva de caché, antigüedad máxima y actualización mínima](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-minimum-freshness.md)  
  
## Vea también  
 [Administración de la memoria caché para aplicaciones de red](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [Directiva de caché](../../../docs/framework/network-programming/cache-policy.md)   
 [directivas de caché basadas en la ubicación](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [Configurar el almacenamiento en caché de las aplicaciones de red](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)   
 [\<requestCaching\> \(Elemento, Configuración de red\)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)