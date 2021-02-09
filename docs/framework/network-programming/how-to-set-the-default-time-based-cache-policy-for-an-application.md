---
description: 'Más información acerca de: Procedimiento: para establecer en una aplicación una directiva de caché predeterminada de duración definida'
title: Cómo establecer en una aplicación una directiva de caché predeterminada de duración definida
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time-based cache policies
- cache [.NET Framework], time-based policies
- default time-based cache policy
ms.assetid: 6bfce066-a2e7-4add-a05e-85c12ec9f07f
ms.openlocfilehash: 1ca9504d8a6df20d3824230d5fb96eb0f13636eb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662772"
---
# <a name="how-to-set-the-default-time-based-cache-policy-for-an-application"></a><span data-ttu-id="09587-103">Procedimiento para establecer en una aplicación una directiva de caché predeterminada de duración definida</span><span class="sxs-lookup"><span data-stu-id="09587-103">How to: Set the Default Time-Based Cache Policy for an Application</span></span>

<span data-ttu-id="09587-104">La directiva de caché predeterminada de duración definida permite que una aplicación tenga su comportamiento de caché definido mediante los encabezados que se han enviado con el recurso almacenado en caché y el comportamiento de caché definido en las secciones 13 y 14 de RFC 2616, disponibles en el sitio web de [Internet Engineering Task Force (IETF)](https://www.ietf.org/).</span><span class="sxs-lookup"><span data-stu-id="09587-104">The default time-based cache policy allows an application to have its cache behavior defined by the headers sent with the cached resource and the cache behavior defined in sections 13 and 14 of RFC 2616, available at [Internet Engineering Task Force (IETF)](https://www.ietf.org/) website.</span></span> <span data-ttu-id="09587-105">Este es el comportamiento de caché apropiado para la mayoría de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="09587-105">This is the appropriate cache behavior for most applications.</span></span>  
  
### <a name="to-set-the-default-automatic-policy-for-an-application"></a><span data-ttu-id="09587-106">Para establecer la directiva automática predeterminada para una aplicación</span><span class="sxs-lookup"><span data-stu-id="09587-106">To set the default automatic policy for an application</span></span>  
  
1. <span data-ttu-id="09587-107">Cree un objeto de directiva predeterminado de duración definida.</span><span class="sxs-lookup"><span data-stu-id="09587-107">Create a default time-based policy object.</span></span>  
  
2. <span data-ttu-id="09587-108">Establezca el objeto de directiva como el valor predeterminado para el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="09587-108">Set the policy object as the default for the application domain.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09587-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="09587-109">Example</span></span>  

 <span data-ttu-id="09587-110">Los dos ejemplos de esta sección generan directivas idénticas.</span><span class="sxs-lookup"><span data-stu-id="09587-110">The two examples in this section produce identical policies.</span></span>  
  
 <span data-ttu-id="09587-111">En el ejemplo siguiente se crea una directiva predeterminada de duración definida y se establece como el valor predeterminado para el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="09587-111">The following example creates a default time-based policy and sets it as the default for the application domain.</span></span>  
  
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
  
 <span data-ttu-id="09587-112">También puede crear la directiva de caché predeterminada de duración definida con la clase <xref:System.Net.Cache.RequestCachePolicy> como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="09587-112">You can also create the default time-based cache policy using the <xref:System.Net.Cache.RequestCachePolicy> class as shown in the following example:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="09587-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="09587-113">See also</span></span>

- [<span data-ttu-id="09587-114">Administración de la memoria caché para aplicaciones de red</span><span class="sxs-lookup"><span data-stu-id="09587-114">Cache Management for Network Applications</span></span>](cache-management-for-network-applications.md)
- [<span data-ttu-id="09587-115">Directiva de caché</span><span class="sxs-lookup"><span data-stu-id="09587-115">Cache Policy</span></span>](cache-policy.md)
- [<span data-ttu-id="09587-116">Location-Based Cache Policies (Directivas de caché basadas en la ubicación)</span><span class="sxs-lookup"><span data-stu-id="09587-116">Location-Based Cache Policies</span></span>](location-based-cache-policies.md)
- <span data-ttu-id="09587-117">[Time-Based Cache Policies](time-based-cache-policies.md) (Directivas de caché de duración definida)</span><span class="sxs-lookup"><span data-stu-id="09587-117">[Time-Based Cache Policies](time-based-cache-policies.md)</span></span>
- [<span data-ttu-id="09587-118">Elemento \<requestCaching> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="09587-118">\<requestCaching> Element (Network Settings)</span></span>](../configure-apps/file-schema/network/requestcaching-element-network-settings.md)
