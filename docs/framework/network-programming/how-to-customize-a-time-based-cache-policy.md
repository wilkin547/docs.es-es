---
title: "C&#243;mo: personalizar una directiva de cach&#233; de duraci&#243;n definida | Microsoft Docs"
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
  - "personalizar directivas de caché de duración definida"
  - "caché [.NET Framework], directivas de duración definida"
ms.assetid: 8d84f936-2376-4356-9264-03162e0f9279
caps.latest.revision: 15
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 15
---
# C&#243;mo: personalizar una directiva de cach&#233; de duraci&#243;n definida
Al crear una directiva Tiempo\- basada de caché, puede personalizar el almacenamiento en caché comportamiento especificando los valores para la edad máxima, la actualización mínima, el deterioro máximo, o la fecha de sincronización de la memoria caché.  El objeto de <xref:System.Net.Cache.HttpRequestCachePolicy> proporciona varios constructores que permiten especificar combinaciones válidas de estos valores.  
  
### Para crear una directiva Tiempo\- basada de caché que utiliza una fecha de sincronización de caché  
  
-   Cree una directiva Tiempo\- basada de caché que utilice una fecha de sincronización de caché pasando un objeto de <xref:System.DateTime> al constructor de <xref:System.Net.Cache.HttpRequestCachePolicy> .  
  
    ```csharp  
    public static HttpRequestCachePolicy CreateLastSyncPolicy(DateTime when)  
    {  
        HttpRequestCachePolicy policy =   
            new HttpRequestCachePolicy(when);  
        Console.WriteLine("When: {0}", when);  
        Console.WriteLine(policy.ToString());  
        return policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Function CreateLastSyncPolicy([when] As DateTime) As HttpRequestCachePolicy  
        Dim policy As New HttpRequestCachePolicy([when])  
        Console.WriteLine("When: {0}", [when])  
        Console.WriteLine(policy.ToString())  
        Return policy  
    End Function  
    ```  
  
 El resultado es similar al siguiente:  
  
```  
When: 1/14/2004 8:07:30 AM  
Level:Default CacheSyncDate:1/14/2004 8:07:30 AM  
```  
  
### Para crear una directiva Tiempo\- basada de caché basado en actualización mínima  
  
-   Cree una directiva Tiempo\- basada de caché que está basada en actualización mínima especificando <xref:System.Net.Cache.HttpCacheAgeControl> como valor del parámetro de `cacheAgeControl` y pasando un objeto de <xref:System.TimeSpan> al constructor de <xref:System.Net.Cache.HttpRequestCachePolicy> .  
  
    ```csharp  
    public static HttpRequestCachePolicy CreateMinFreshPolicy(TimeSpan span)  
    {  
        HttpRequestCachePolicy policy =   
            new HttpRequestCachePolicy(HttpCacheAgeControl.MinFresh, span);  
        Console.WriteLine(policy.ToString());  
        return policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Function CreateMinFreshPolicy(span As TimeSpan) As HttpRequestCachePolicy  
        Dim policy As New HttpRequestCachePolicy(HttpCacheAgeControl.MinFresh, span)  
        Console.WriteLine(policy.ToString())  
        Return policy  
    End Function  
    ```  
  
 Para la invocación siguiente:  
  
```  
CreateMinFreshPolicy(new TimeSpan(1,0,0));  
```  
  
```  
Level:Default MinFresh:3600  
  
```  
  
### Para crear una directiva Tiempo\- basada de caché basado en actualización mínima y edad máxima  
  
-   Cree una directiva Tiempo\- basada de caché que está basada en actualización mínima y edad máxima especificando <xref:System.Net.Cache.HttpCacheAgeControl> como valor del parámetro de `cacheAgeControl` y pasando dos objetos de <xref:System.TimeSpan> al constructor de <xref:System.Net.Cache.HttpRequestCachePolicy> , uno para especificar la edad máxima para que los recursos y un segundo especifican la actualización mínima permitida para un objeto devuelto de caché.  
  
    ```csharp  
    public static HttpRequestCachePolicy CreateFreshAndAgePolicy(TimeSpan freshMinimum, TimeSpan ageMaximum)  
    {  
        HttpRequestCachePolicy policy =   
        new HttpRequestCachePolicy(HttpCacheAgeControl.MaxAgeAndMinFresh, ageMaximum, freshMinimum);  
        Console.WriteLine(policy.ToString());  
        return policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Function CreateFreshAndAgePolicy(freshMinimum As TimeSpan, ageMaximum As TimeSpan) As HttpRequestCachePolicy  
        Dim policy As New HttpRequestCachePolicy(HttpCacheAgeControl.MaxAgeAndMinFresh, ageMaximum, freshMinimum)  
        Console.WriteLine(policy.ToString())  
        Return policy  
    End Function  
    ```  
  
 Para la invocación siguiente:  
  
```  
CreateFreshAndAgePolicy(new TimeSpan(5,0,0), new TimeSpan(10,0,0));  
```  
  
```  
Level:Default MaxAge:36000 MinFresh:18000  
```  
  
## Vea también  
 [Administración de la memoria caché para aplicaciones de red](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [Directiva de caché](../../../docs/framework/network-programming/cache-policy.md)   
 [directivas de caché basadas en la ubicación](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [directivas de caché de duración definida](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [\<requestCaching\> \(Elemento, Configuración de red\)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)