---
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
ms.openlocfilehash: e9398beee7051d88867600b79c615356c2d4cc28
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96241699"
---
# <a name="how-to-set-the-default-time-based-cache-policy-for-an-application"></a>Cómo establecer en una aplicación una directiva de caché predeterminada de duración definida

La directiva de caché predeterminada de duración definida permite que una aplicación tenga su comportamiento de caché definido mediante los encabezados que se han enviado con el recurso almacenado en caché y el comportamiento de caché definido en las secciones 13 y 14 de RFC 2616, disponibles en el sitio web de [Internet Engineering Task Force (IETF)](https://www.ietf.org/). Este es el comportamiento de caché apropiado para la mayoría de aplicaciones.  
  
### <a name="to-set-the-default-automatic-policy-for-an-application"></a>Para establecer la directiva automática predeterminada para una aplicación  
  
1. Cree un objeto de directiva predeterminado de duración definida.  
  
2. Establezca el objeto de directiva como el valor predeterminado para el dominio de aplicación.  
  
## <a name="example"></a>Ejemplo  

 Los dos ejemplos de esta sección generan directivas idénticas.  
  
 En el ejemplo siguiente se crea una directiva predeterminada de duración definida y se establece como el valor predeterminado para el dominio de aplicación.  
  
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
  
 También puede crear la directiva de caché predeterminada de duración definida con la clase <xref:System.Net.Cache.RequestCachePolicy> como se muestra en el ejemplo siguiente:  
  
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
  
## <a name="see-also"></a>Vea también

- [Administración de la memoria caché para aplicaciones de red](cache-management-for-network-applications.md)
- [Directiva de caché](cache-policy.md)
- [Location-Based Cache Policies (Directivas de caché basadas en la ubicación)](location-based-cache-policies.md)
- [Time-Based Cache Policies](time-based-cache-policies.md) (Directivas de caché de duración definida)
- [Elemento \<requestCaching> (configuración de red)](../configure-apps/file-schema/network/requestcaching-element-network-settings.md)
