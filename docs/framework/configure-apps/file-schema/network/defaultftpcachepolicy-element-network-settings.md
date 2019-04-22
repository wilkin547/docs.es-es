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
ms.openlocfilehash: 36d174beea58ff96674bd873bfbcb8be89591669
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59132540"
---
# <a name="defaultftpcachepolicy-element-network-settings"></a><span data-ttu-id="7cc05-102">\<defaultFtpCachePolicy > elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="7cc05-102">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>
<span data-ttu-id="7cc05-103">Describe si el almacenamiento en caché de FTP está activo y describe la directiva de caché de predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7cc05-103">Describes whether FTP caching is active and describes the default caching policy.</span></span>  
  
 <span data-ttu-id="7cc05-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7cc05-104">\<configuration></span></span>  
<span data-ttu-id="7cc05-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="7cc05-105">\<system.net></span></span>  
<span data-ttu-id="7cc05-106">\<requestCaching></span><span class="sxs-lookup"><span data-stu-id="7cc05-106">\<requestCaching></span></span>  
<span data-ttu-id="7cc05-107">\<defaultFtpCachePolicy></span><span class="sxs-lookup"><span data-stu-id="7cc05-107">\<defaultFtpCachePolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cc05-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7cc05-108">Syntax</span></span>  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7cc05-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7cc05-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7cc05-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7cc05-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7cc05-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="7cc05-111">Attributes</span></span>  
  
|<span data-ttu-id="7cc05-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="7cc05-112">Attribute</span></span>|<span data-ttu-id="7cc05-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="7cc05-113">Description</span></span>|  
|---------------|-----------------|  
|`policyLevel`|<span data-ttu-id="7cc05-114">Especifica la directiva de caché de FTP.</span><span class="sxs-lookup"><span data-stu-id="7cc05-114">Specifies the FTP caching policy.</span></span> <span data-ttu-id="7cc05-115">El valor predeterminado es `Default`.</span><span class="sxs-lookup"><span data-stu-id="7cc05-115">The default value is `Default`.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="7cc05-116">Atributo policyLevel</span><span class="sxs-lookup"><span data-stu-id="7cc05-116">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="7cc05-117">Valor</span><span class="sxs-lookup"><span data-stu-id="7cc05-117">Value</span></span>|<span data-ttu-id="7cc05-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="7cc05-118">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="7cc05-119">Devuelve el recurso almacenado en caché si el recurso está actualizado, la longitud del contenido es precisa y están presentes los atributos de la longitud del contenido, modificación y caducidad.</span><span class="sxs-lookup"><span data-stu-id="7cc05-119">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="7cc05-120">Devuelve el recurso desde el servidor.</span><span class="sxs-lookup"><span data-stu-id="7cc05-120">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="7cc05-121">Devuelve el recurso almacenado en caché si la longitud del contenido está presente y coincide con el tamaño de entrada.</span><span class="sxs-lookup"><span data-stu-id="7cc05-121">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="7cc05-122">Devuelve el recurso almacenado en caché si la longitud del contenido se proporciona y coincide con el tamaño de la entrada; en caso contrario, el recurso se descarga desde el servidor y se devuelve al llamador.</span><span class="sxs-lookup"><span data-stu-id="7cc05-122">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="7cc05-123">Devuelve el recurso almacenado en caché si la marca de tiempo del recurso almacenado en caché es igual que la marca de tiempo del recurso en el servidor. en caso contrario, el recurso se descarga desde el servidor, almacenado en la memoria caché y devuelve al llamador.</span><span class="sxs-lookup"><span data-stu-id="7cc05-123">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="7cc05-124">Descarga el recurso desde el servidor, lo almacena en la memoria caché y devuelve el recurso al llamador.</span><span class="sxs-lookup"><span data-stu-id="7cc05-124">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="7cc05-125">Si existe un recurso almacenado en caché, se elimina.</span><span class="sxs-lookup"><span data-stu-id="7cc05-125">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="7cc05-126">El recurso se descarga desde el servidor y se devuelve al llamador.</span><span class="sxs-lookup"><span data-stu-id="7cc05-126">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="7cc05-127">Atiende una solicitud mediante el uso de la copia en caché del recurso si la marca de tiempo es igual que la marca de tiempo del recurso en el servidor. en caso contrario, el recurso se descarga desde el servidor, presenta al llamador y almacenado en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="7cc05-127">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and stored in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7cc05-128">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7cc05-128">Child Elements</span></span>  
 <span data-ttu-id="7cc05-129">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7cc05-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7cc05-130">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7cc05-130">Parent Elements</span></span>  
  
|<span data-ttu-id="7cc05-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="7cc05-131">Element</span></span>|<span data-ttu-id="7cc05-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="7cc05-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7cc05-133">requestCaching</span><span class="sxs-lookup"><span data-stu-id="7cc05-133">requestCaching</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="7cc05-134">Controla el mecanismo de almacenamiento en caché para las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="7cc05-134">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7cc05-135">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7cc05-135">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="7cc05-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7cc05-136">Example</span></span>  
 <span data-ttu-id="7cc05-137">En el ejemplo siguiente se muestra cómo especificar la directiva de almacenamiento en caché de FTP `NoCacheNoStore`.</span><span class="sxs-lookup"><span data-stu-id="7cc05-137">The following example shows how to specify an FTP caching policy of `NoCacheNoStore`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7cc05-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="7cc05-138">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="7cc05-139">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="7cc05-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
