---
title: Administración de la memoria caché para aplicaciones de red
ms.date: 03/30/2017
helpviewer_keywords:
- cache [.NET Framework], network applications
- network resources, caching
- Internet, caching
ms.assetid: fc258a40-f370-434f-ae09-4a8cb11ddaeb
ms.openlocfilehash: 7e131963999db3e3d5e0e6f3fa110da36e6452a1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048877"
---
# <a name="cache-management-for-network-applications"></a><span data-ttu-id="797c7-102">Administración de la memoria caché para aplicaciones de red</span><span class="sxs-lookup"><span data-stu-id="797c7-102">Cache Management for Network Applications</span></span>
<span data-ttu-id="797c7-103">Este tema y los temas secundarios relacionados describen el almacenamiento en caché de los recursos obtenidos mediante las clases <xref:System.Net.WebClient>, <xref:System.Net.WebRequest>, <xref:System.Net.HttpWebRequest> y <xref:System.Net.FtpWebRequest>.</span><span class="sxs-lookup"><span data-stu-id="797c7-103">This topic and its related subtopics describe caching for resources obtained using the <xref:System.Net.WebClient>, <xref:System.Net.WebRequest>, <xref:System.Net.HttpWebRequest>, and <xref:System.Net.FtpWebRequest> classes.</span></span>  
  
 <span data-ttu-id="797c7-104">Una memoria caché proporciona almacenamiento temporal de recursos solicitados por una aplicación.</span><span class="sxs-lookup"><span data-stu-id="797c7-104">A cache provides temporary storage of resources that have been requested by an application.</span></span> <span data-ttu-id="797c7-105">Si una aplicación solicita el mismo recurso más de una vez, este se puede devolver desde la memoria caché, con lo que se evita la sobrecarga de volver a solicitarlo desde el servidor.</span><span class="sxs-lookup"><span data-stu-id="797c7-105">If an application requests the same resource more than once, the resource can be returned from the cache, avoiding the overhead of re-requesting it from the server.</span></span> <span data-ttu-id="797c7-106">El almacenamiento en caché puede mejorar el rendimiento de la aplicación al reducir el tiempo necesario para obtener un recurso solicitado.</span><span class="sxs-lookup"><span data-stu-id="797c7-106">Caching can improve application performance by reducing the time required to get a requested resource.</span></span> <span data-ttu-id="797c7-107">El almacenamiento en caché también puede disminuir el tráfico de red al reducir el número de viajes al servidor.</span><span class="sxs-lookup"><span data-stu-id="797c7-107">Caching can also decrease network traffic by reducing the number of trips to the server.</span></span> <span data-ttu-id="797c7-108">Aunque el almacenamiento en caché mejora el rendimiento, aumenta el riesgo de que el recurso devuelto a la aplicación esté obsoleto, lo que significa que no es idéntico al recurso que habría enviado el servidor si no se estuviera usando el almacenamiento en caché.</span><span class="sxs-lookup"><span data-stu-id="797c7-108">While caching improves performance, it increases the risk that the resource returned to the application is stale, meaning that it is not identical to the resource that would have been sent by the server if caching were not in use.</span></span>  
  
 <span data-ttu-id="797c7-109">El almacenamiento en caché puede permitir que usuarios o procesos no autorizados lean datos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="797c7-109">Caching may allow unauthorized users or processes to read sensitive data.</span></span> <span data-ttu-id="797c7-110">Se puede recuperar una respuesta autenticada almacenada en caché sin ninguna autorización adicional.</span><span class="sxs-lookup"><span data-stu-id="797c7-110">An authenticated response that is cached may be retrieved from the cache without an additional authorization.</span></span> <span data-ttu-id="797c7-111">Si el almacenamiento en caché está habilitado, cambie <xref:System.Net.WebRequest.CachePolicy%2A> a <xref:System.Net.Cache.RequestCacheLevel.BypassCache> o <xref:System.Net.Cache.RequestCacheLevel.NoCacheNoStore> para deshabilitar el almacenamiento en caché de esta solicitud.</span><span class="sxs-lookup"><span data-stu-id="797c7-111">If caching is enabled, change to <xref:System.Net.WebRequest.CachePolicy%2A> to <xref:System.Net.Cache.RequestCacheLevel.BypassCache> or <xref:System.Net.Cache.RequestCacheLevel.NoCacheNoStore> to disable caching for this request.</span></span>  
  
 <span data-ttu-id="797c7-112">Por motivos de seguridad, el almacenamiento en caché **no** se recomienda para escenarios de nivel intermedio.</span><span class="sxs-lookup"><span data-stu-id="797c7-112">Due to security concerns, caching is **not** recommended for middle tier scenarios.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="797c7-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="797c7-113">In This Section</span></span>  
 [<span data-ttu-id="797c7-114">Directiva de caché</span><span class="sxs-lookup"><span data-stu-id="797c7-114">Cache Policy</span></span>](cache-policy.md)  
 <span data-ttu-id="797c7-115">Explica qué es una directiva de caché y cómo definirla.</span><span class="sxs-lookup"><span data-stu-id="797c7-115">Explains what a cache policy is and how to define one.</span></span>  
  
 [<span data-ttu-id="797c7-116">Location-Based Cache Policies (Directivas de caché basadas en la ubicación)</span><span class="sxs-lookup"><span data-stu-id="797c7-116">Location-Based Cache Policies</span></span>](location-based-cache-policies.md)  
 <span data-ttu-id="797c7-117">Define cada tipo de directiva de caché basada en la ubicación disponible para recursos de protocolo de transferencia de hipertexto (http y https).</span><span class="sxs-lookup"><span data-stu-id="797c7-117">Defines each type of location-based cache policy available for Hypertext Transfer Protocol (http and https) resources.</span></span>  
  
 <span data-ttu-id="797c7-118">[Time-Based Cache Policies](time-based-cache-policies.md) (Directivas de caché de duración definida)</span><span class="sxs-lookup"><span data-stu-id="797c7-118">[Time-Based Cache Policies](time-based-cache-policies.md)</span></span>  
 <span data-ttu-id="797c7-119">Describe los criterios que pueden usarse para personalizar una directiva de caché basada en el tiempo.</span><span class="sxs-lookup"><span data-stu-id="797c7-119">Describes the criteria that can be used to customize a time-based cache policy.</span></span>  
  
 [<span data-ttu-id="797c7-120">Configurar el almacenamiento en caché de las aplicaciones de red</span><span class="sxs-lookup"><span data-stu-id="797c7-120">Configuring Caching in Network Applications</span></span>](configuring-caching-in-network-applications.md)  
 <span data-ttu-id="797c7-121">Explica cómo crear directivas de caché mediante programación y solicitudes que usen el almacenamiento en caché.</span><span class="sxs-lookup"><span data-stu-id="797c7-121">Describes how to programmatically create cache policies and requests that use caching.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="797c7-122">Referencia</span><span class="sxs-lookup"><span data-stu-id="797c7-122">Reference</span></span>  
 <xref:System.Net.Cache>  
 <span data-ttu-id="797c7-123">Define los tipos y las enumeraciones usados para definir directivas de caché para los recursos obtenidos mediante las clases <xref:System.Net.WebRequest>, <xref:System.Net.HttpWebRequest> y <xref:System.Net.FtpWebRequest>.</span><span class="sxs-lookup"><span data-stu-id="797c7-123">Defines the types and enumerations used to define cache policies for resources obtained using the <xref:System.Net.WebRequest>, <xref:System.Net.HttpWebRequest>, and <xref:System.Net.FtpWebRequest> classes.</span></span>
