---
title: 'Procedimientos: Personalización de una directiva de caché de duración definida'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time-based cache policies
- customizing time-based cache policies
- cache [.NET Framework], time-based policies
ms.assetid: 8d84f936-2376-4356-9264-03162e0f9279
ms.openlocfilehash: 1a2ba404e333eeec2a23758c834876d0df5aba81
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73040633"
---
# <a name="how-to-customize-a-time-based-cache-policy"></a>Procedimientos: Personalización de una directiva de caché de duración definida

Al crear una directiva de caché de duración definida, puede personalizar el comportamiento de almacenamiento en caché. Para ello, especifique valores de antigüedad máxima, actualización mínima, obsolescencia máxima o una fecha de sincronización de caché. El objeto <xref:System.Net.Cache.HttpRequestCachePolicy> proporciona varios constructores que permiten especificar combinaciones válidas de estos valores.

## <a name="to-create-a-time-based-cache-policy-that-uses-a-cache-synchronization-date"></a>Para crear una directiva de caché de duración definida que use una fecha de sincronización de caché

Para crear una directiva de caché de duración definida que use una fecha de sincronización de caché, pase un objeto <xref:System.DateTime> al constructor <xref:System.Net.Cache.HttpRequestCachePolicy>:

```csharp
public static HttpRequestCachePolicy CreateLastSyncPolicy(DateTime when)
{
    var policy = new HttpRequestCachePolicy(when);
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

La salida será similar a la siguiente:

```output
When: 1/14/2004 8:07:30 AM
Level:Default CacheSyncDate:1/14/2004 8:07:30 AM
```

## <a name="to-create-a-time-based-cache-policy-that-is-based-on-minimum-freshness"></a>Para crear una directiva de caché de duración definida basada en la actualización mínima

Para crear una directiva de caché de duración definida basada en la actualización mínima, especifique <xref:System.Net.Cache.HttpCacheAgeControl.MinFresh> como el valor del parámetro `cacheAgeControl` y pase un objeto <xref:System.TimeSpan> al constructor <xref:System.Net.Cache.HttpRequestCachePolicy>:

```csharp
public static HttpRequestCachePolicy CreateMinFreshPolicy(TimeSpan span)
{
    var policy = new HttpRequestCachePolicy(HttpCacheAgeControl.MinFresh, span);
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

```csharp
CreateMinFreshPolicy(new TimeSpan(1,0,0));
```

El resultado es el siguiente:

```output
Level:Default MinFresh:3600
```

## <a name="to-create-a-time-based-cache-policy-that-is-based-on-minimum-freshness-and-maximum-age"></a>Para crear una directiva de caché de duración definida basada en la actualización mínima y la antigüedad máxima

Para crear una directiva de caché de duración definida basada en la actualización mínima y la antigüedad máxima, especifique <xref:System.Net.Cache.HttpCacheAgeControl.MaxAgeAndMinFresh> como valor del parámetro `cacheAgeControl` y pase dos objetos <xref:System.TimeSpan> al constructor <xref:System.Net.Cache.HttpRequestCachePolicy>, uno para especificar la antigüedad máxima de los recursos y otro para especificar la actualización mínima permitida para un objeto devuelto desde la caché:

```csharp
public static HttpRequestCachePolicy CreateFreshAndAgePolicy(TimeSpan freshMinimum, TimeSpan ageMaximum)
{
    var policy = new HttpRequestCachePolicy(HttpCacheAgeControl.MaxAgeAndMinFresh, ageMaximum, freshMinimum);
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
  
```csharp
CreateFreshAndAgePolicy(new TimeSpan(5,0,0), new TimeSpan(10,0,0));  
```  

El resultado es el siguiente:
  
```output
Level:Default MaxAge:36000 MinFresh:18000  
```  
  
## <a name="see-also"></a>Vea también

- [Administración de la memoria caché para aplicaciones de red](cache-management-for-network-applications.md)
- [Directiva de caché](cache-policy.md)
- [Location-Based Cache Policies (Directivas de caché basadas en la ubicación)](location-based-cache-policies.md)
- [Time-Based Cache Policies](time-based-cache-policies.md) (Directivas de caché de duración definida)
- [Elemento \<requestCaching> (configuración de red)](../configure-apps/file-schema/network/requestcaching-element-network-settings.md)
