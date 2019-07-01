---
title: Procedimiento para establecer en una aplicación una directiva de caché basada en la ubicación
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
ms.openlocfilehash: 5b4936a54627e6016cabc41954d1a18ae82cdf90
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/28/2019
ms.locfileid: "67422474"
---
# <a name="how-to-set-a-location-based-cache-policy-for-an-application"></a><span data-ttu-id="11186-102">Procedimiento para establecer en una aplicación una directiva de caché basada en la ubicación</span><span class="sxs-lookup"><span data-stu-id="11186-102">How to: Set a Location-Based Cache Policy for an Application</span></span>
<span data-ttu-id="11186-103">Las directivas de caché basadas en la ubicación permiten que una aplicación defina explícitamente el comportamiento de caché basándose en la ubicación del recurso solicitado.</span><span class="sxs-lookup"><span data-stu-id="11186-103">Location-based cache policies allow an application to explicitly define caching behavior based on the location of the requested resource.</span></span> <span data-ttu-id="11186-104">En este tema se muestra cómo establecer la directiva de caché mediante programación.</span><span class="sxs-lookup"><span data-stu-id="11186-104">This topic demonstrates setting the cache policy programmatically.</span></span> <span data-ttu-id="11186-105">Para obtener información sobre cómo establecer la directiva de una aplicación con los archivos de configuración, vea [Elemento \<requestCaching> (configuración de red)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="11186-105">For information on setting the policy for an application using the configuration files, see [\<requestCaching> Element (Network Settings)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md).</span></span>  
  
### <a name="to-set-a-location-based-cache-policy-for-an-application"></a><span data-ttu-id="11186-106">Para establecer en una aplicación una directiva de caché basada en la ubicación</span><span class="sxs-lookup"><span data-stu-id="11186-106">To set a location-based cache policy for an application</span></span>  
  
1. <span data-ttu-id="11186-107">Cree un objeto <xref:System.Net.Cache.RequestCachePolicy> o <xref:System.Net.Cache.HttpRequestCachePolicy>.</span><span class="sxs-lookup"><span data-stu-id="11186-107">Create a <xref:System.Net.Cache.RequestCachePolicy> or <xref:System.Net.Cache.HttpRequestCachePolicy> object.</span></span>  
  
2. <span data-ttu-id="11186-108">Establezca el objeto de directiva como el valor predeterminado para el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="11186-108">Set the policy object as the default for the application domain.</span></span>  
  
### <a name="to-set-a-policy-that-takes-requested-resources-from-a-cache"></a><span data-ttu-id="11186-109">Para establecer una directiva que toma recursos solicitados de una caché</span><span class="sxs-lookup"><span data-stu-id="11186-109">To set a policy that takes requested resources from a cache</span></span>  
  
- <span data-ttu-id="11186-110">Cree una directiva que tome recursos solicitados de una caché si están disponibles, y en caso contrario, que envíe solicitudes al servidor estableciendo el nivel de caché en <xref:System.Net.Cache.HttpRequestCacheLevel.CacheIfAvailable>.</span><span class="sxs-lookup"><span data-stu-id="11186-110">Create a policy that takes requested resources from a cache if available, and otherwise, sends requests to the server, by setting the cache level to <xref:System.Net.Cache.HttpRequestCacheLevel.CacheIfAvailable>.</span></span> <span data-ttu-id="11186-111">Una solicitud se puede satisfacer mediante cualquier caché entre el cliente y el servidor, incluidas las memorias caché remotas.</span><span class="sxs-lookup"><span data-stu-id="11186-111">A request can be fulfilled by any cache between the client and server, including remote caches.</span></span>  
  
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
  
### <a name="to-set-a-policy-that-prevents-any-cache-from-supplying-resources"></a><span data-ttu-id="11186-112">Para establecer una directiva que impida que cualquier caché proporcione recursos</span><span class="sxs-lookup"><span data-stu-id="11186-112">To set a policy that prevents any cache from supplying resources</span></span>  
  
- <span data-ttu-id="11186-113">Cree una directiva que impida que cualquier caché proporcione recursos solicitados estableciendo el nivel de caché en <xref:System.Net.Cache.HttpRequestCacheLevel.NoCacheNoStore>.</span><span class="sxs-lookup"><span data-stu-id="11186-113">Create a policy that prevents any cache from supplying requested resources by setting the cache level to <xref:System.Net.Cache.HttpRequestCacheLevel.NoCacheNoStore>.</span></span> <span data-ttu-id="11186-114">Este nivel de directiva quita el recurso de la caché local si está presente e indica a las memorias caché remotas que también deben quitar el recurso.</span><span class="sxs-lookup"><span data-stu-id="11186-114">This policy level removes the resource from the local cache if it is present and indicates to remote caches that they should also remove the resource.</span></span>  
  
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
  
### <a name="to-set-a-policy-that-returns-requested-resources-only-if-they-are-in-the-local-cache"></a><span data-ttu-id="11186-115">Para establecer una directiva que devuelve recursos solicitados solo si están en la caché local</span><span class="sxs-lookup"><span data-stu-id="11186-115">To set a policy that returns requested resources only if they are in the local cache</span></span>  
  
- <span data-ttu-id="11186-116">Cree una directiva que devuelva recursos solicitados solo si se encuentran en la caché local estableciendo el nivel de caché en <xref:System.Net.Cache.HttpRequestCacheLevel.CacheOnly>.</span><span class="sxs-lookup"><span data-stu-id="11186-116">Create a policy that returns requested resources only if they are in the local cache by setting the cache level to <xref:System.Net.Cache.HttpRequestCacheLevel.CacheOnly>.</span></span> <span data-ttu-id="11186-117">Si el recurso solicitado no está en la caché, se genera una excepción <xref:System.Net.WebException>.</span><span class="sxs-lookup"><span data-stu-id="11186-117">If the requested resource is not in the cache, a <xref:System.Net.WebException> exception is thrown.</span></span>  
  
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
  
### <a name="to-set-a-policy-that-prevents-the-local-cache-from-supplying-resources"></a><span data-ttu-id="11186-118">Para establecer una directiva que impida que la caché local proporcione recursos</span><span class="sxs-lookup"><span data-stu-id="11186-118">To set a policy that prevents the local cache from supplying resources</span></span>  
  
- <span data-ttu-id="11186-119">Cree una directiva que impida que la caché local proporcione recursos solicitados estableciendo el nivel de caché en <xref:System.Net.Cache.HttpRequestCacheLevel.Refresh>.</span><span class="sxs-lookup"><span data-stu-id="11186-119">Create a policy that prevents the local cache from supplying requested resources by setting the cache level to <xref:System.Net.Cache.HttpRequestCacheLevel.Refresh>.</span></span> <span data-ttu-id="11186-120">Si el recurso solicitado está en una caché intermedia y se ha vuelto a validar correctamente, la caché intermedia puede proporcionar el recurso solicitado.</span><span class="sxs-lookup"><span data-stu-id="11186-120">If the requested resource is in an intermediate cache and is successfully revalidated, the intermediate cache can supply the requested resource.</span></span>  
  
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
  
### <a name="to-set-a-policy-that-prevents-any-cache-from-supplying-requested-resources"></a><span data-ttu-id="11186-121">Para establecer una directiva que impida que cualquier caché proporcione recursos solicitados</span><span class="sxs-lookup"><span data-stu-id="11186-121">To set a policy that prevents any cache from supplying requested resources</span></span>  
  
- <span data-ttu-id="11186-122">Cree una directiva que impida que cualquier caché proporcione recursos solicitados estableciendo el nivel de caché en <xref:System.Net.Cache.HttpRequestCacheLevel.Reload>.</span><span class="sxs-lookup"><span data-stu-id="11186-122">Create a policy that prevents any cache from supplying requested resources by setting the cache level to <xref:System.Net.Cache.HttpRequestCacheLevel.Reload>.</span></span> <span data-ttu-id="11186-123">El recurso que ha devuelto el servidor puede almacenarse en la caché.</span><span class="sxs-lookup"><span data-stu-id="11186-123">The resource returned by the server can be stored in the cache.</span></span>  
  
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
  
### <a name="to-set-a-policy-that-allows-any-cache-to-supply-requested-resources-if-the-resource-on-the-server-is-not-newer-than-the-cached-copy"></a><span data-ttu-id="11186-124">Para establecer una directiva que permita que cualquier caché proporcione recursos solicitados si el recurso del servidor no es más reciente que la copia almacenada en caché</span><span class="sxs-lookup"><span data-stu-id="11186-124">To set a policy that allows any cache to supply requested resources if the resource on the server is not newer than the cached copy</span></span>  
  
- <span data-ttu-id="11186-125">Cree una directiva que permita que cualquier caché proporcione recursos solicitados si el recurso del servidor no es más reciente que la copia almacenada en caché estableciendo el nivel de caché en <xref:System.Net.Cache.HttpRequestCacheLevel.Revalidate>.</span><span class="sxs-lookup"><span data-stu-id="11186-125">Create a policy that allows any cache to supply requested resources if the resource on the server is not newer than the cached copy by setting the cache level to <xref:System.Net.Cache.HttpRequestCacheLevel.Revalidate>.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="11186-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="11186-126">See also</span></span>

- [<span data-ttu-id="11186-127">Administración de la memoria caché para aplicaciones de red</span><span class="sxs-lookup"><span data-stu-id="11186-127">Cache Management for Network Applications</span></span>](../../../docs/framework/network-programming/cache-management-for-network-applications.md)
- [<span data-ttu-id="11186-128">Directiva de caché</span><span class="sxs-lookup"><span data-stu-id="11186-128">Cache Policy</span></span>](../../../docs/framework/network-programming/cache-policy.md)
- [<span data-ttu-id="11186-129">Location-Based Cache Policies (Directivas de caché basadas en la ubicación)</span><span class="sxs-lookup"><span data-stu-id="11186-129">Location-Based Cache Policies</span></span>](../../../docs/framework/network-programming/location-based-cache-policies.md)
- <span data-ttu-id="11186-130">[Time-Based Cache Policies](../../../docs/framework/network-programming/time-based-cache-policies.md) (Directivas de caché de duración definida)</span><span class="sxs-lookup"><span data-stu-id="11186-130">[Time-Based Cache Policies](../../../docs/framework/network-programming/time-based-cache-policies.md)</span></span>
- [<span data-ttu-id="11186-131">Elemento \<requestCaching> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="11186-131">\<requestCaching> Element (Network Settings)</span></span>](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)
