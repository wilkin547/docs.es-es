---
description: 'Más información acerca de: Procedimientos: Personalización de una directiva de caché de duración definida'
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
ms.openlocfilehash: bb00faa5c2cd3170a0f56b74032867d489c1fb8a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747457"
---
# <a name="how-to-customize-a-time-based-cache-policy"></a><span data-ttu-id="34778-103">Procedimientos: Personalización de una directiva de caché de duración definida</span><span class="sxs-lookup"><span data-stu-id="34778-103">How to: customize a time-based cache policy</span></span>

<span data-ttu-id="34778-104">Al crear una directiva de caché de duración definida, puede personalizar el comportamiento de almacenamiento en caché. Para ello, especifique valores de antigüedad máxima, actualización mínima, obsolescencia máxima o una fecha de sincronización de caché.</span><span class="sxs-lookup"><span data-stu-id="34778-104">When creating a time-based cache policy, you can customize caching behavior by specifying values for maximum age, minimum freshness, maximum staleness, or cache synchronization date.</span></span> <span data-ttu-id="34778-105">El objeto <xref:System.Net.Cache.HttpRequestCachePolicy> proporciona varios constructores que permiten especificar combinaciones válidas de estos valores.</span><span class="sxs-lookup"><span data-stu-id="34778-105">The <xref:System.Net.Cache.HttpRequestCachePolicy> object provides several constructors that allow you to specify valid combinations of these values.</span></span>

## <a name="to-create-a-time-based-cache-policy-that-uses-a-cache-synchronization-date"></a><span data-ttu-id="34778-106">Para crear una directiva de caché de duración definida que use una fecha de sincronización de caché</span><span class="sxs-lookup"><span data-stu-id="34778-106">To create a time-based cache policy that uses a cache synchronization date</span></span>

<span data-ttu-id="34778-107">Para crear una directiva de caché de duración definida que use una fecha de sincronización de caché, pase un objeto <xref:System.DateTime> al constructor <xref:System.Net.Cache.HttpRequestCachePolicy>:</span><span class="sxs-lookup"><span data-stu-id="34778-107">Create a time-based cache policy that uses a cache synchronization date by passing a <xref:System.DateTime> object to the <xref:System.Net.Cache.HttpRequestCachePolicy> constructor:</span></span>

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

<span data-ttu-id="34778-108">La salida será similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="34778-108">The output is similar to the following:</span></span>

```output
When: 1/14/2004 8:07:30 AM
Level:Default CacheSyncDate:1/14/2004 8:07:30 AM
```

## <a name="to-create-a-time-based-cache-policy-that-is-based-on-minimum-freshness"></a><span data-ttu-id="34778-109">Para crear una directiva de caché de duración definida basada en la actualización mínima</span><span class="sxs-lookup"><span data-stu-id="34778-109">To create a time-based cache policy that is based on minimum freshness</span></span>

<span data-ttu-id="34778-110">Para crear una directiva de caché de duración definida basada en la actualización mínima, especifique <xref:System.Net.Cache.HttpCacheAgeControl.MinFresh> como el valor del parámetro `cacheAgeControl` y pase un objeto <xref:System.TimeSpan> al constructor <xref:System.Net.Cache.HttpRequestCachePolicy>:</span><span class="sxs-lookup"><span data-stu-id="34778-110">Create a time-based cache policy that is based on minimum freshness by specifying <xref:System.Net.Cache.HttpCacheAgeControl.MinFresh> as the `cacheAgeControl` parameter value and passing a <xref:System.TimeSpan> object to the <xref:System.Net.Cache.HttpRequestCachePolicy> constructor:</span></span>

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

<span data-ttu-id="34778-111">Para la invocación siguiente:</span><span class="sxs-lookup"><span data-stu-id="34778-111">For the following invocation:</span></span>

```csharp
CreateMinFreshPolicy(new TimeSpan(1,0,0));
```

<span data-ttu-id="34778-112">La salida es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="34778-112">The output is:</span></span>

```output
Level:Default MinFresh:3600
```

## <a name="to-create-a-time-based-cache-policy-that-is-based-on-minimum-freshness-and-maximum-age"></a><span data-ttu-id="34778-113">Para crear una directiva de caché de duración definida basada en la actualización mínima y la antigüedad máxima</span><span class="sxs-lookup"><span data-stu-id="34778-113">To create a time-based cache policy that is based on minimum freshness and maximum age</span></span>

<span data-ttu-id="34778-114">Para crear una directiva de caché de duración definida basada en la actualización mínima y la antigüedad máxima, especifique <xref:System.Net.Cache.HttpCacheAgeControl.MaxAgeAndMinFresh> como valor del parámetro `cacheAgeControl` y pase dos objetos <xref:System.TimeSpan> al constructor <xref:System.Net.Cache.HttpRequestCachePolicy>, uno para especificar la antigüedad máxima de los recursos y otro para especificar la actualización mínima permitida para un objeto devuelto desde la caché:</span><span class="sxs-lookup"><span data-stu-id="34778-114">Create a time-based cache policy that is based on minimum freshness and maximum age by specifying <xref:System.Net.Cache.HttpCacheAgeControl.MaxAgeAndMinFresh> as the `cacheAgeControl` parameter value and passing two <xref:System.TimeSpan> objects to the <xref:System.Net.Cache.HttpRequestCachePolicy> constructor, one to specify the maximum age for resources and a second to specify the minimum freshness permitted for an object returned from the cache:</span></span>

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

<span data-ttu-id="34778-115">Para la invocación siguiente:</span><span class="sxs-lookup"><span data-stu-id="34778-115">For the following invocation:</span></span>
  
```csharp
CreateFreshAndAgePolicy(new TimeSpan(5,0,0), new TimeSpan(10,0,0));  
```  

<span data-ttu-id="34778-116">La salida es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="34778-116">The output is:</span></span>
  
```output
Level:Default MaxAge:36000 MinFresh:18000  
```  
  
## <a name="see-also"></a><span data-ttu-id="34778-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="34778-117">See also</span></span>

- [<span data-ttu-id="34778-118">Administración de la memoria caché para aplicaciones de red</span><span class="sxs-lookup"><span data-stu-id="34778-118">Cache Management for Network Applications</span></span>](cache-management-for-network-applications.md)
- [<span data-ttu-id="34778-119">Directiva de caché</span><span class="sxs-lookup"><span data-stu-id="34778-119">Cache Policy</span></span>](cache-policy.md)
- [<span data-ttu-id="34778-120">Location-Based Cache Policies (Directivas de caché basadas en la ubicación)</span><span class="sxs-lookup"><span data-stu-id="34778-120">Location-Based Cache Policies</span></span>](location-based-cache-policies.md)
- <span data-ttu-id="34778-121">[Time-Based Cache Policies](time-based-cache-policies.md) (Directivas de caché de duración definida)</span><span class="sxs-lookup"><span data-stu-id="34778-121">[Time-Based Cache Policies](time-based-cache-policies.md)</span></span>
- [<span data-ttu-id="34778-122">Elemento \<requestCaching> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="34778-122">\<requestCaching> Element (Network Settings)</span></span>](../configure-apps/file-schema/network/requestcaching-element-network-settings.md)
