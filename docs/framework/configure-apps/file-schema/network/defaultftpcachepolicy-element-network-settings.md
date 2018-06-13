---
title: '&lt;defaultFtpCachePolicy&gt; Element (Network Settings)'
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
manager: markl
ms.openlocfilehash: e4ea16c925114d4ad4054af5f340c764ed6fe4fd
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743152"
---
# <a name="ltdefaultftpcachepolicygt-element-network-settings"></a><span data-ttu-id="a3e94-102">&lt;defaultFtpCachePolicy&gt; Element (Network Settings)</span><span class="sxs-lookup"><span data-stu-id="a3e94-102">&lt;defaultFtpCachePolicy&gt; Element (Network Settings)</span></span>
<span data-ttu-id="a3e94-103">Describe si el almacenamiento en caché de FTP está activo y describe la predeterminada de directiva de caché.</span><span class="sxs-lookup"><span data-stu-id="a3e94-103">Describes whether FTP caching is active and describes the default caching policy.</span></span>  
  
 <span data-ttu-id="a3e94-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a3e94-104">\<configuration></span></span>  
<span data-ttu-id="a3e94-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="a3e94-105">\<system.net></span></span>  
<span data-ttu-id="a3e94-106">\<requestCaching ></span><span class="sxs-lookup"><span data-stu-id="a3e94-106">\<requestCaching></span></span>  
<span data-ttu-id="a3e94-107">\<defaultFtpCachePolicy ></span><span class="sxs-lookup"><span data-stu-id="a3e94-107">\<defaultFtpCachePolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3e94-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a3e94-108">Syntax</span></span>  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a3e94-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a3e94-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a3e94-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a3e94-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a3e94-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="a3e94-111">Attributes</span></span>  
  
|<span data-ttu-id="a3e94-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="a3e94-112">Attribute</span></span>|<span data-ttu-id="a3e94-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="a3e94-113">Description</span></span>|  
|---------------|-----------------|  
|`policyLevel`|<span data-ttu-id="a3e94-114">Especifica la directiva de caché de FTP.</span><span class="sxs-lookup"><span data-stu-id="a3e94-114">Specifies the FTP caching policy.</span></span> <span data-ttu-id="a3e94-115">El valor predeterminado es `Default`.</span><span class="sxs-lookup"><span data-stu-id="a3e94-115">The default value is `Default`.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="a3e94-116">Atributo policyLevel</span><span class="sxs-lookup"><span data-stu-id="a3e94-116">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="a3e94-117">Valor</span><span class="sxs-lookup"><span data-stu-id="a3e94-117">Value</span></span>|<span data-ttu-id="a3e94-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="a3e94-118">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="a3e94-119">Devuelve el recurso almacenado en caché si el recurso es nuevo, la longitud del contenido es precisa y la expiración, modificación y atributos de longitud de contenido están presentes.</span><span class="sxs-lookup"><span data-stu-id="a3e94-119">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="a3e94-120">Devuelve el recurso desde el servidor.</span><span class="sxs-lookup"><span data-stu-id="a3e94-120">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="a3e94-121">Devuelve el recurso almacenado en caché si la longitud del contenido está presente y coincide con el tamaño de la entrada.</span><span class="sxs-lookup"><span data-stu-id="a3e94-121">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="a3e94-122">Devuelve el recurso almacenado en caché si la longitud del contenido se proporciona y coincide con el tamaño de la entrada; en caso contrario, el recurso se descarga desde el servidor y se devuelve al llamador.</span><span class="sxs-lookup"><span data-stu-id="a3e94-122">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="a3e94-123">Devuelve el recurso almacenado en caché si la marca de tiempo del recurso almacenado en caché es igual que la marca de tiempo del recurso en el servidor; en caso contrario, el recurso se descargan desde el servidor, almacenado en la memoria caché y devuelve al llamador.</span><span class="sxs-lookup"><span data-stu-id="a3e94-123">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="a3e94-124">Descarga el recurso del servidor, lo almacena en la memoria caché y devuelve el recurso al llamador.</span><span class="sxs-lookup"><span data-stu-id="a3e94-124">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="a3e94-125">Si existe un recurso almacenado en caché, se elimina.</span><span class="sxs-lookup"><span data-stu-id="a3e94-125">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="a3e94-126">El recurso se descarga desde el servidor y se devuelve al llamador.</span><span class="sxs-lookup"><span data-stu-id="a3e94-126">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="a3e94-127">Satisface una solicitud mediante la copia en caché del recurso si la marca de tiempo es el mismo que la marca de tiempo del recurso en el servidor; en caso contrario, el recurso se descarga desde el servidor, presenta al llamador y almacenado en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="a3e94-127">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and stored in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a3e94-128">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a3e94-128">Child Elements</span></span>  
 <span data-ttu-id="a3e94-129">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a3e94-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a3e94-130">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a3e94-130">Parent Elements</span></span>  
  
|<span data-ttu-id="a3e94-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="a3e94-131">Element</span></span>|<span data-ttu-id="a3e94-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="a3e94-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a3e94-133">requestCaching</span><span class="sxs-lookup"><span data-stu-id="a3e94-133">requestCaching</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="a3e94-134">Controla el mecanismo de almacenamiento en caché las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="a3e94-134">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3e94-135">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a3e94-135">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3e94-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a3e94-136">Example</span></span>  
 <span data-ttu-id="a3e94-137">En el ejemplo siguiente se muestra cómo especificar un FTP almacenamiento en caché de la directiva de `NoCacheNoStore`.</span><span class="sxs-lookup"><span data-stu-id="a3e94-137">The following example shows how to specify an FTP caching policy of `NoCacheNoStore`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a3e94-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3e94-138">See Also</span></span>  
 <xref:System.Net.Cache>  
 <xref:System.Net.WebRequest>  
 <xref:System.Net.Cache.RequestCacheLevel>  
 [<span data-ttu-id="a3e94-139">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="a3e94-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
