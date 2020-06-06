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
ms.openlocfilehash: 9261a430642cb4d5ac4507835bd0fd3561bd8c02
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088430"
---
# <a name="defaultftpcachepolicy-element-network-settings"></a><span data-ttu-id="27f27-102">Elemento \<defaultFtpCachePolicy> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="27f27-102">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>
<span data-ttu-id="27f27-103">Describe si el almacenamiento en caché de FTP está activo y describe la Directiva de almacenamiento en caché predeterminada.</span><span class="sxs-lookup"><span data-stu-id="27f27-103">Describes whether FTP caching is active and describes the default caching policy.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<requestCaching>**](requestcaching-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultFtpCachePolicy>**

## <a name="syntax"></a><span data-ttu-id="27f27-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="27f27-104">Syntax</span></span>  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="27f27-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="27f27-105">Attributes and Elements</span></span>  
 <span data-ttu-id="27f27-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="27f27-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="27f27-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="27f27-107">Attributes</span></span>  
  
|<span data-ttu-id="27f27-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="27f27-108">Attribute</span></span>|<span data-ttu-id="27f27-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="27f27-109">Description</span></span>|  
|---------------|-----------------|  
|`policyLevel`|<span data-ttu-id="27f27-110">Especifica la Directiva de almacenamiento en caché de FTP.</span><span class="sxs-lookup"><span data-stu-id="27f27-110">Specifies the FTP caching policy.</span></span> <span data-ttu-id="27f27-111">El valor predeterminado es `Default`.</span><span class="sxs-lookup"><span data-stu-id="27f27-111">The default value is `Default`.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="27f27-112">Atributo policyLevel</span><span class="sxs-lookup"><span data-stu-id="27f27-112">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="27f27-113">Value</span><span class="sxs-lookup"><span data-stu-id="27f27-113">Value</span></span>|<span data-ttu-id="27f27-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="27f27-114">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="27f27-115">Devuelve el recurso almacenado en caché si el recurso es nuevo, la longitud del contenido es precisa y los atributos expiración, modificación y longitud del contenido están presentes.</span><span class="sxs-lookup"><span data-stu-id="27f27-115">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="27f27-116">Devuelve el recurso del servidor.</span><span class="sxs-lookup"><span data-stu-id="27f27-116">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="27f27-117">Devuelve el recurso almacenado en caché si la longitud del contenido está presente y coincide con el tamaño de entrada.</span><span class="sxs-lookup"><span data-stu-id="27f27-117">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="27f27-118">Devuelve el recurso almacenado en caché si se proporciona la longitud del contenido y coincide con el tamaño de entrada; de lo contrario, el recurso se descarga del servidor y se devuelve al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="27f27-118">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="27f27-119">Devuelve el recurso almacenado en caché si la marca de tiempo del recurso almacenado en caché es igual que la marca de tiempo del recurso en el servidor; de lo contrario, el recurso se descarga del servidor, se almacena en la memoria caché y se devuelve al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="27f27-119">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="27f27-120">Descarga el recurso del servidor, lo almacena en la memoria caché y devuelve el recurso al llamador.</span><span class="sxs-lookup"><span data-stu-id="27f27-120">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="27f27-121">Si existe un recurso almacenado en caché, se elimina.</span><span class="sxs-lookup"><span data-stu-id="27f27-121">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="27f27-122">El recurso se descarga del servidor y se devuelve al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="27f27-122">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="27f27-123">Atiende una solicitud utilizando la copia almacenada en caché del recurso si la marca de tiempo es igual que la marca de tiempo del recurso en el servidor; de lo contrario, el recurso se descarga del servidor, se presenta al llamador y se almacena en la caché.</span><span class="sxs-lookup"><span data-stu-id="27f27-123">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and stored in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="27f27-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="27f27-124">Child Elements</span></span>  
 <span data-ttu-id="27f27-125">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="27f27-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="27f27-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="27f27-126">Parent Elements</span></span>  
  
|<span data-ttu-id="27f27-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="27f27-127">Element</span></span>|<span data-ttu-id="27f27-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="27f27-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="27f27-129">requestCaching</span><span class="sxs-lookup"><span data-stu-id="27f27-129">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="27f27-130">Controla el mecanismo de almacenamiento en caché para las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="27f27-130">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27f27-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="27f27-131">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="27f27-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="27f27-132">Example</span></span>  
 <span data-ttu-id="27f27-133">En el ejemplo siguiente se muestra cómo especificar una directiva de almacenamiento en caché de FTP de `NoCacheNoStore` .</span><span class="sxs-lookup"><span data-stu-id="27f27-133">The following example shows how to specify an FTP caching policy of `NoCacheNoStore`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="27f27-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="27f27-134">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="27f27-135">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="27f27-135">Network Settings Schema</span></span>](index.md)
