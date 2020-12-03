---
title: Cómo establecer en una aplicación una directiva de caché basada en la ubicación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- explicitly defining cache behavior
- location-based cache policies
- local cache
- request cache policies
- cache [.NET Framework], location-based policies
ms.assetid: 683bb88e-3411-4f46-9686-3411b6ba511c
ms.openlocfilehash: 7331845c391265d72d3025fd9bf7856d83c783e9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253497"
---
# <a name="how-to-set-a-location-based-cache-policy-for-an-application"></a>Cómo establecer en una aplicación una directiva de caché basada en la ubicación

Las directivas de caché basadas en la ubicación permiten que una aplicación defina explícitamente el comportamiento de caché basándose en la ubicación del recurso solicitado. En este tema se muestra cómo establecer la directiva de caché mediante programación. Para obtener información sobre cómo establecer la directiva de una aplicación mediante los archivos de configuración, vea [Elemento \<requestCaching> (configuración de red)](../configure-apps/file-schema/network/requestcaching-element-network-settings.md).  
  
### <a name="to-set-a-location-based-cache-policy-for-an-application"></a>Para establecer en una aplicación una directiva de caché basada en la ubicación  
  
1. Cree un objeto <xref:System.Net.Cache.RequestCachePolicy> o <xref:System.Net.Cache.HttpRequestCachePolicy>.  
  
2. Establezca el objeto de directiva como el valor predeterminado para el dominio de aplicación.  
  
### <a name="to-set-a-policy-that-takes-requested-resources-from-a-cache"></a>Para establecer una directiva que toma recursos solicitados de una caché  
  
- Cree una directiva que tome recursos solicitados de una caché si están disponibles, y en caso contrario, que envíe solicitudes al servidor estableciendo el nivel de caché en <xref:System.Net.Cache.HttpRequestCacheLevel.CacheIfAvailable>. Una solicitud se puede satisfacer mediante cualquier caché entre el cliente y el servidor, incluidas las memorias caché remotas.  
  
    ```csharp  
    public static void UseCacheIfAvailable()  
    {  
        HttpRequestCachePolicy policy = new HttpRequestCachePolicy  
            (HttpRequestCacheLevel.CacheIfAvailable);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub UseCacheIfAvailable()  
        Dim policy As New HttpRequestCachePolicy _  
             (HttpRequestCacheLevel.CacheIfAvailable)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### <a name="to-set-a-policy-that-prevents-any-cache-from-supplying-resources"></a>Para establecer una directiva que impida que cualquier caché proporcione recursos  
  
- Cree una directiva que impida que cualquier caché proporcione recursos solicitados estableciendo el nivel de caché en <xref:System.Net.Cache.HttpRequestCacheLevel.NoCacheNoStore>. Este nivel de directiva quita el recurso de la caché local si está presente e indica a las memorias caché remotas que también deben quitar el recurso.  
  
    ```csharp  
    public static void DoNotUseCache()  
    {  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy
            (HttpRequestCacheLevel.NoCacheNoStore);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub DoNotUseCache()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.NoCacheNoStore)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### <a name="to-set-a-policy-that-returns-requested-resources-only-if-they-are-in-the-local-cache"></a>Para establecer una directiva que devuelve recursos solicitados solo si están en la caché local  
  
- Cree una directiva que devuelva recursos solicitados solo si se encuentran en la caché local estableciendo el nivel de caché en <xref:System.Net.Cache.HttpRequestCacheLevel.CacheOnly>. Si el recurso solicitado no está en la caché, se genera una excepción <xref:System.Net.WebException>.  
  
    ```csharp  
    public static void OnlyUseCache()  
    {  
        HttpRequestCachePolicy policy = new HttpRequestCachePolicy
            (HttpRequestCacheLevel.CacheOnly);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub OnlyUseCache()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.CacheOnly)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### <a name="to-set-a-policy-that-prevents-the-local-cache-from-supplying-resources"></a>Para establecer una directiva que impida que la caché local proporcione recursos  
  
- Cree una directiva que impida que la caché local proporcione recursos solicitados estableciendo el nivel de caché en <xref:System.Net.Cache.HttpRequestCacheLevel.Refresh>. Si el recurso solicitado está en una caché intermedia y se ha vuelto a validar correctamente, la caché intermedia puede proporcionar el recurso solicitado.  
  
    ```csharp  
    public static void DoNotUseLocalCache()  
    {  
     HttpRequestCachePolicy policy = new HttpRequestCachePolicy
            (HttpRequestCacheLevel.Refresh);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub DoNotUseLocalCache()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.Refresh)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### <a name="to-set-a-policy-that-prevents-any-cache-from-supplying-requested-resources"></a>Para establecer una directiva que impida que cualquier caché proporcione recursos solicitados  
  
- Cree una directiva que impida que cualquier caché proporcione recursos solicitados estableciendo el nivel de caché en <xref:System.Net.Cache.HttpRequestCacheLevel.Reload>. El recurso que ha devuelto el servidor puede almacenarse en la caché.  
  
    ```csharp  
    public static void SendToServer()  
    {  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy
            (HttpRequestCacheLevel.Reload);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub SendToServer()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.Reload)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### <a name="to-set-a-policy-that-allows-any-cache-to-supply-requested-resources-if-the-resource-on-the-server-is-not-newer-than-the-cached-copy"></a>Para establecer una directiva que permita que cualquier caché proporcione recursos solicitados si el recurso del servidor no es más reciente que la copia almacenada en caché  
  
- Cree una directiva que permita que cualquier caché proporcione recursos solicitados si el recurso del servidor no es más reciente que la copia almacenada en caché estableciendo el nivel de caché en <xref:System.Net.Cache.HttpRequestCacheLevel.Revalidate>.  
  
    ```csharp  
    public static void CheckServer()  
    {  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy  
             (HttpRequestCacheLevel.Revalidate);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub CheckServer()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.Revalidate)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
## <a name="see-also"></a>Vea también

- [Administración de la memoria caché para aplicaciones de red](cache-management-for-network-applications.md)
- [Directiva de caché](cache-policy.md)
- [Location-Based Cache Policies (Directivas de caché basadas en la ubicación)](location-based-cache-policies.md)
- [Time-Based Cache Policies](time-based-cache-policies.md) (Directivas de caché de duración definida)
- [Elemento \<requestCaching> (configuración de red)](../configure-apps/file-schema/network/requestcaching-element-network-settings.md)
