---
title: "C&#243;mo establecer en una aplicaci&#243;n una directiva de cach&#233; predeterminada de duraci&#243;n definida | Microsoft Docs"
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
  - "caché [.NET Framework], directivas de duración definida"
  - "directivas de caché predeterminadas de duración definida "
ms.assetid: 6bfce066-a2e7-4add-a05e-85c12ec9f07f
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# C&#243;mo establecer en una aplicaci&#243;n una directiva de cach&#233; predeterminada de duraci&#243;n definida
La directiva Tiempo\- basada predeterminado de caché permite que una aplicación tenga el comportamiento de la caché definido por los encabezados enviados al recurso en caché y el comportamiento de la caché definido en las secciones 13 y 14 de RFC 2616, disponible en [http:\/\/www.ietf.org](http://www.ietf.org/).  Éste es el comportamiento adecuado de caché para la mayoría de las aplicaciones.  
  
### Para establecer la directiva automático predeterminado para una aplicación  
  
1.  Cree un objeto Tiempo\- basado predeterminado de la directiva.  
  
2.  Establezca el objeto de directiva como valor predeterminado para el dominio de aplicación.  
  
## Ejemplo  
 Los dos ejemplos de esta sección muestran directivas idénticas.  
  
 El ejemplo siguiente se crea una directiva Tiempo\- basada predeterminado y la establece como valor predeterminado para el dominio de aplicación.  
  
```csharp  
public static void SetDefaultTimeBasedPolicy ()  
{  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy ();  
    HttpWebRequest.DefaultCachePolicy = policy ;  
}  
```  
  
```vb  
Public Shared Sub SetDefaultTimeBasedPolicy ()  
    Dim policy = New HttpRequestCachePolicy ()  
    HttpWebRequest.DefaultCachePolicy = policy  
End Sub  
```  
  
 También puede crear la directiva Tiempo\- basada predeterminado de la memoria caché utilizando la clase de <xref:System.Net.Cache.RequestCachePolicy> tal y como se muestra en el ejemplo siguiente:  
  
```csharp  
public static void SetDefaultTimeBasedPolicy2()  
{  
    RequestCachePolicy policy = new RequestCachePolicy ();  
    HttpWebRequest.DefaultCachePolicy = policy ;  
}  
```  
  
```vb  
Public Shared Sub SetDefaultTimeBasedPolicy2()  
    Dim policy As New RequestCachePolicy()  
    HttpWebRequest.DefaultCachePolicy = policy  
End Sub  
  
```  
  
## Vea también  
 [Administración de la memoria caché para aplicaciones de red](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [Directiva de caché](../../../docs/framework/network-programming/cache-policy.md)   
 [directivas de caché basadas en la ubicación](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [directivas de caché de duración definida](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [\<requestCaching\> \(Elemento, Configuración de red\)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)