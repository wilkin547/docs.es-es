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
ms.openlocfilehash: 7ff44f0251936d51b4e396c37c53322efa110227
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659423"
---
# <a name="defaultftpcachepolicy-element-network-settings"></a><span data-ttu-id="59aec-102">\<defaultFtpCachePolicy > elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="59aec-102">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>
<span data-ttu-id="59aec-103">Describe si el almacenamiento en caché de FTP está activo y describe la Directiva de almacenamiento en caché predeterminada.</span><span class="sxs-lookup"><span data-stu-id="59aec-103">Describes whether FTP caching is active and describes the default caching policy.</span></span>  
  
 <span data-ttu-id="59aec-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="59aec-104">\<configuration></span></span>  
<span data-ttu-id="59aec-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="59aec-105">\<system.net></span></span>  
<span data-ttu-id="59aec-106">\<requestCaching></span><span class="sxs-lookup"><span data-stu-id="59aec-106">\<requestCaching></span></span>  
<span data-ttu-id="59aec-107">\<defaultFtpCachePolicy></span><span class="sxs-lookup"><span data-stu-id="59aec-107">\<defaultFtpCachePolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59aec-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="59aec-108">Syntax</span></span>  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59aec-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="59aec-109">Attributes and Elements</span></span>  
 <span data-ttu-id="59aec-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="59aec-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59aec-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="59aec-111">Attributes</span></span>  
  
|<span data-ttu-id="59aec-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="59aec-112">Attribute</span></span>|<span data-ttu-id="59aec-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="59aec-113">Description</span></span>|  
|---------------|-----------------|  
|`policyLevel`|<span data-ttu-id="59aec-114">Especifica la Directiva de almacenamiento en caché de FTP.</span><span class="sxs-lookup"><span data-stu-id="59aec-114">Specifies the FTP caching policy.</span></span> <span data-ttu-id="59aec-115">El valor predeterminado es `Default`.</span><span class="sxs-lookup"><span data-stu-id="59aec-115">The default value is `Default`.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="59aec-116">Atributo policyLevel</span><span class="sxs-lookup"><span data-stu-id="59aec-116">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="59aec-117">Valor</span><span class="sxs-lookup"><span data-stu-id="59aec-117">Value</span></span>|<span data-ttu-id="59aec-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="59aec-118">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="59aec-119">Devuelve el recurso almacenado en caché si el recurso es nuevo, la longitud del contenido es precisa y los atributos expiración, modificación y longitud del contenido están presentes.</span><span class="sxs-lookup"><span data-stu-id="59aec-119">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="59aec-120">Devuelve el recurso del servidor.</span><span class="sxs-lookup"><span data-stu-id="59aec-120">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="59aec-121">Devuelve el recurso almacenado en caché si la longitud del contenido está presente y coincide con el tamaño de entrada.</span><span class="sxs-lookup"><span data-stu-id="59aec-121">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="59aec-122">Devuelve el recurso almacenado en caché si se proporciona la longitud del contenido y coincide con el tamaño de entrada; de lo contrario, el recurso se descarga del servidor y se devuelve al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="59aec-122">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="59aec-123">Devuelve el recurso almacenado en caché si la marca de tiempo del recurso almacenado en caché es igual que la marca de tiempo del recurso en el servidor; de lo contrario, el recurso se descarga del servidor, se almacena en la memoria caché y se devuelve al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="59aec-123">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="59aec-124">Descarga el recurso del servidor, lo almacena en la memoria caché y devuelve el recurso al llamador.</span><span class="sxs-lookup"><span data-stu-id="59aec-124">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="59aec-125">Si existe un recurso almacenado en caché, se elimina.</span><span class="sxs-lookup"><span data-stu-id="59aec-125">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="59aec-126">El recurso se descarga del servidor y se devuelve al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="59aec-126">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="59aec-127">Satisface una solicitud mediante la copia en caché del recurso si la marca de tiempo es igual que la marca de tiempo del recurso en el servidor. de lo contrario, el recurso se descarga del servidor, se presenta al llamador y se almacena en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="59aec-127">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and stored in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="59aec-128">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="59aec-128">Child Elements</span></span>  
 <span data-ttu-id="59aec-129">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="59aec-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="59aec-130">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="59aec-130">Parent Elements</span></span>  
  
|<span data-ttu-id="59aec-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="59aec-131">Element</span></span>|<span data-ttu-id="59aec-132">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="59aec-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="59aec-133">requestCaching</span><span class="sxs-lookup"><span data-stu-id="59aec-133">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="59aec-134">Controla el mecanismo de almacenamiento en caché para las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="59aec-134">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59aec-135">Comentarios</span><span class="sxs-lookup"><span data-stu-id="59aec-135">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="59aec-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="59aec-136">Example</span></span>  
 <span data-ttu-id="59aec-137">En el ejemplo siguiente se muestra cómo especificar una directiva de almacenamiento `NoCacheNoStore`en caché de FTP de.</span><span class="sxs-lookup"><span data-stu-id="59aec-137">The following example shows how to specify an FTP caching policy of `NoCacheNoStore`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="59aec-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="59aec-138">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="59aec-139">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="59aec-139">Network Settings Schema</span></span>](index.md)
