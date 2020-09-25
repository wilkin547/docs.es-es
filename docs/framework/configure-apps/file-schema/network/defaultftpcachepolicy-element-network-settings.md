---
title: Elemento <defaultFtpCachePolicy> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultFtpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultFtpCachePolicy
helpviewer_keywords:
- <defaultFtpCachePolicy> element
- defaultFtpCachePolicy element
ms.assetid: 0eb0c5cb-dd97-484d-8614-785e88877abb
ms.openlocfilehash: e081882aa8df89c0a1bf5d4c60f1395a3319c417
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190376"
---
# <a name="defaultftpcachepolicy-element-network-settings"></a><span data-ttu-id="3b0d2-102">Elemento \<defaultFtpCachePolicy> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="3b0d2-102">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>

<span data-ttu-id="3b0d2-103">Describe si el almacenamiento en caché de FTP está activo y describe la Directiva de almacenamiento en caché predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3b0d2-103">Describes whether FTP caching is active and describes the default caching policy.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<requestCaching>**](requestcaching-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultFtpCachePolicy>**

## <a name="syntax"></a><span data-ttu-id="3b0d2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3b0d2-104">Syntax</span></span>  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3b0d2-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3b0d2-105">Attributes and Elements</span></span>  

 <span data-ttu-id="3b0d2-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3b0d2-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3b0d2-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="3b0d2-107">Attributes</span></span>  
  
|<span data-ttu-id="3b0d2-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="3b0d2-108">Attribute</span></span>|<span data-ttu-id="3b0d2-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b0d2-109">Description</span></span>|  
|---------------|-----------------|  
|`policyLevel`|<span data-ttu-id="3b0d2-110">Especifica la Directiva de almacenamiento en caché de FTP.</span><span class="sxs-lookup"><span data-stu-id="3b0d2-110">Specifies the FTP caching policy.</span></span> <span data-ttu-id="3b0d2-111">El valor predeterminado es `Default`.</span><span class="sxs-lookup"><span data-stu-id="3b0d2-111">The default value is `Default`.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="3b0d2-112">Atributo policyLevel</span><span class="sxs-lookup"><span data-stu-id="3b0d2-112">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="3b0d2-113">Value</span><span class="sxs-lookup"><span data-stu-id="3b0d2-113">Value</span></span>|<span data-ttu-id="3b0d2-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b0d2-114">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="3b0d2-115">Devuelve el recurso almacenado en caché si el recurso es nuevo, la longitud del contenido es precisa y los atributos expiración, modificación y longitud del contenido están presentes.</span><span class="sxs-lookup"><span data-stu-id="3b0d2-115">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="3b0d2-116">Devuelve el recurso del servidor.</span><span class="sxs-lookup"><span data-stu-id="3b0d2-116">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="3b0d2-117">Devuelve el recurso almacenado en caché si la longitud del contenido está presente y coincide con el tamaño de entrada.</span><span class="sxs-lookup"><span data-stu-id="3b0d2-117">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="3b0d2-118">Devuelve el recurso almacenado en caché si se proporciona la longitud del contenido y coincide con el tamaño de entrada; de lo contrario, el recurso se descarga del servidor y se devuelve al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3b0d2-118">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="3b0d2-119">Devuelve el recurso almacenado en caché si la marca de tiempo del recurso almacenado en caché es igual que la marca de tiempo del recurso en el servidor; de lo contrario, el recurso se descarga del servidor, se almacena en la memoria caché y se devuelve al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3b0d2-119">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="3b0d2-120">Descarga el recurso del servidor, lo almacena en la memoria caché y devuelve el recurso al llamador.</span><span class="sxs-lookup"><span data-stu-id="3b0d2-120">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="3b0d2-121">Si existe un recurso almacenado en caché, se elimina.</span><span class="sxs-lookup"><span data-stu-id="3b0d2-121">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="3b0d2-122">El recurso se descarga del servidor y se devuelve al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3b0d2-122">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="3b0d2-123">Atiende una solicitud utilizando la copia almacenada en caché del recurso si la marca de tiempo es igual que la marca de tiempo del recurso en el servidor; de lo contrario, el recurso se descarga del servidor, se presenta al llamador y se almacena en la caché.</span><span class="sxs-lookup"><span data-stu-id="3b0d2-123">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and stored in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3b0d2-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3b0d2-124">Child Elements</span></span>  

 <span data-ttu-id="3b0d2-125">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3b0d2-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3b0d2-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3b0d2-126">Parent Elements</span></span>  
  
|<span data-ttu-id="3b0d2-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="3b0d2-127">Element</span></span>|<span data-ttu-id="3b0d2-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b0d2-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3b0d2-129">requestCaching</span><span class="sxs-lookup"><span data-stu-id="3b0d2-129">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="3b0d2-130">Controla el mecanismo de almacenamiento en caché para las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="3b0d2-130">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b0d2-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3b0d2-131">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b0d2-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3b0d2-132">Example</span></span>  

 <span data-ttu-id="3b0d2-133">En el ejemplo siguiente se muestra cómo especificar una directiva de almacenamiento en caché de FTP de `NoCacheNoStore` .</span><span class="sxs-lookup"><span data-stu-id="3b0d2-133">The following example shows how to specify an FTP caching policy of `NoCacheNoStore`.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultFtpCachePolicy  
        policyLevel="NoCacheNoStore">  
      </defaultFtpCachePolicy>  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3b0d2-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3b0d2-134">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="3b0d2-135">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="3b0d2-135">Network Settings Schema</span></span>](index.md)
