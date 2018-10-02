---
title: '&lt;defaultFtpCachePolicy&gt; elemento (configuración de red)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultFtpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultFtpCachePolicy
helpviewer_keywords:
- <defaultFtpCachePolicy> element
- defaultFtpCachePolicy element
ms.assetid: 0eb0c5cb-dd97-484d-8614-785e88877abb
author: mcleblanc
ms.author: markl
ms.openlocfilehash: e03fb02bd351058c1fcdedb8367d03318418a12c
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48032379"
---
# <a name="ltdefaultftpcachepolicygt-element-network-settings"></a><span data-ttu-id="0154e-102">&lt;defaultFtpCachePolicy&gt; elemento (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="0154e-102">&lt;defaultFtpCachePolicy&gt; Element (Network Settings)</span></span>
<span data-ttu-id="0154e-103">Describe si el almacenamiento en caché de FTP está activo y describe la directiva de caché de predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0154e-103">Describes whether FTP caching is active and describes the default caching policy.</span></span>  
  
 <span data-ttu-id="0154e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="0154e-104">\<configuration></span></span>  
<span data-ttu-id="0154e-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="0154e-105">\<system.net></span></span>  
<span data-ttu-id="0154e-106">\<requestCaching ></span><span class="sxs-lookup"><span data-stu-id="0154e-106">\<requestCaching></span></span>  
<span data-ttu-id="0154e-107">\<defaultFtpCachePolicy ></span><span class="sxs-lookup"><span data-stu-id="0154e-107">\<defaultFtpCachePolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0154e-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0154e-108">Syntax</span></span>  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0154e-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0154e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0154e-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0154e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0154e-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="0154e-111">Attributes</span></span>  
  
|<span data-ttu-id="0154e-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="0154e-112">Attribute</span></span>|<span data-ttu-id="0154e-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="0154e-113">Description</span></span>|  
|---------------|-----------------|  
|`policyLevel`|<span data-ttu-id="0154e-114">Especifica la directiva de caché de FTP.</span><span class="sxs-lookup"><span data-stu-id="0154e-114">Specifies the FTP caching policy.</span></span> <span data-ttu-id="0154e-115">El valor predeterminado es `Default`.</span><span class="sxs-lookup"><span data-stu-id="0154e-115">The default value is `Default`.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="0154e-116">Atributo policyLevel</span><span class="sxs-lookup"><span data-stu-id="0154e-116">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="0154e-117">Valor</span><span class="sxs-lookup"><span data-stu-id="0154e-117">Value</span></span>|<span data-ttu-id="0154e-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="0154e-118">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="0154e-119">Devuelve el recurso almacenado en caché si el recurso está actualizado, la longitud del contenido es precisa y están presentes los atributos de la longitud del contenido, modificación y caducidad.</span><span class="sxs-lookup"><span data-stu-id="0154e-119">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="0154e-120">Devuelve el recurso desde el servidor.</span><span class="sxs-lookup"><span data-stu-id="0154e-120">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="0154e-121">Devuelve el recurso almacenado en caché si la longitud del contenido está presente y coincide con el tamaño de entrada.</span><span class="sxs-lookup"><span data-stu-id="0154e-121">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="0154e-122">Devuelve el recurso almacenado en caché si la longitud del contenido se proporciona y coincide con el tamaño de la entrada; en caso contrario, el recurso se descarga desde el servidor y se devuelve al llamador.</span><span class="sxs-lookup"><span data-stu-id="0154e-122">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="0154e-123">Devuelve el recurso almacenado en caché si la marca de tiempo del recurso almacenado en caché es igual que la marca de tiempo del recurso en el servidor. en caso contrario, el recurso se descarga desde el servidor, almacenado en la memoria caché y devuelve al llamador.</span><span class="sxs-lookup"><span data-stu-id="0154e-123">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="0154e-124">Descarga el recurso desde el servidor, lo almacena en la memoria caché y devuelve el recurso al llamador.</span><span class="sxs-lookup"><span data-stu-id="0154e-124">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="0154e-125">Si existe un recurso almacenado en caché, se elimina.</span><span class="sxs-lookup"><span data-stu-id="0154e-125">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="0154e-126">El recurso se descarga desde el servidor y se devuelve al llamador.</span><span class="sxs-lookup"><span data-stu-id="0154e-126">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="0154e-127">Atiende una solicitud mediante el uso de la copia en caché del recurso si la marca de tiempo es igual que la marca de tiempo del recurso en el servidor. en caso contrario, el recurso se descarga desde el servidor, presenta al llamador y almacenado en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="0154e-127">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and stored in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0154e-128">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0154e-128">Child Elements</span></span>  
 <span data-ttu-id="0154e-129">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0154e-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0154e-130">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0154e-130">Parent Elements</span></span>  
  
|<span data-ttu-id="0154e-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="0154e-131">Element</span></span>|<span data-ttu-id="0154e-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="0154e-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0154e-133">requestCaching</span><span class="sxs-lookup"><span data-stu-id="0154e-133">requestCaching</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="0154e-134">Controla el mecanismo de almacenamiento en caché para las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="0154e-134">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0154e-135">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0154e-135">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="0154e-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0154e-136">Example</span></span>  
 <span data-ttu-id="0154e-137">En el ejemplo siguiente se muestra cómo especificar la directiva de almacenamiento en caché de FTP `NoCacheNoStore`.</span><span class="sxs-lookup"><span data-stu-id="0154e-137">The following example shows how to specify an FTP caching policy of `NoCacheNoStore`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0154e-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="0154e-138">See Also</span></span>  
 <xref:System.Net.Cache>  
 <xref:System.Net.WebRequest>  
 <xref:System.Net.Cache.RequestCacheLevel>  
 [<span data-ttu-id="0154e-139">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="0154e-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
