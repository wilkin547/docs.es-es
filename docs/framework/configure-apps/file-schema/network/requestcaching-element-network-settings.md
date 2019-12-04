---
title: Elemento <requestCaching> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requestCaching
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching
helpviewer_keywords:
- requestCaching element
- <requestCaching> element
ms.assetid: 9962a2fe-cbda-41a6-9377-571811eaea84
ms.openlocfilehash: afee69eb894518b1c88483e34a1d64d452019244
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802126"
---
# <a name="requestcaching-element-network-settings"></a><span data-ttu-id="5e457-102">Elemento \<requestCaching> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="5e457-102">\<requestCaching> Element (Network Settings)</span></span>
<span data-ttu-id="5e457-103">Controla el mecanismo de almacenamiento en caché para las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="5e457-103">Controls the caching mechanism for network requests.</span></span>  
  
[<span data-ttu-id="5e457-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="5e457-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="5e457-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="5e457-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="5e457-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<requestCaching >**</span><span class="sxs-lookup"><span data-stu-id="5e457-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<requestCaching>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e457-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5e457-107">Syntax</span></span>  
  
```xml  
<requestCaching  
  isPrivateCache ="true|false"  
  disableAllCaching="true|false"  
  defaultPolicyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
  unspecifiedMaximumAge= "d.hh:mm:ss">  
    <defaultHttpCachePolicy>...</defaultHttpCachePolicy>  
    <defaultFtpCachePolicy>...</defaultFtpCachePolicy>  
</requestCaching>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5e457-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5e457-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5e457-109">En las secciones siguientes se describen atributos, elementos secundarios y elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5e457-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5e457-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="5e457-110">Attributes</span></span>  
  
|<span data-ttu-id="5e457-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="5e457-111">Attribute</span></span>|<span data-ttu-id="5e457-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="5e457-112">Description</span></span>|  
|---------------|-----------------|  
|`isPrivateCache`|<span data-ttu-id="5e457-113">Especifica si la memoria caché proporciona aislamiento entre la información de los distintos usuarios.</span><span class="sxs-lookup"><span data-stu-id="5e457-113">Specifies whether the cache provides isolation between the information of different users.</span></span> <span data-ttu-id="5e457-114">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="5e457-114">The default value is `true`.</span></span> <span data-ttu-id="5e457-115">Este valor se debe `false` para las aplicaciones de nivel intermedio.</span><span class="sxs-lookup"><span data-stu-id="5e457-115">This value should be `false` for middle tier applications.</span></span>|  
|`disableAllCaching`|<span data-ttu-id="5e457-116">Especifica que el almacenamiento en caché está deshabilitado para todas las respuestas web y no se puede invalidar mediante programación.</span><span class="sxs-lookup"><span data-stu-id="5e457-116">Specifies that caching is disabled for all Web responses, and cannot be overridden programmatically.</span></span>|  
|`defaultPolicyLevel`|<span data-ttu-id="5e457-117">Uno de los valores de la enumeración <xref:System.Net.Cache.RequestCacheLevel>.</span><span class="sxs-lookup"><span data-stu-id="5e457-117">One of the values in the <xref:System.Net.Cache.RequestCacheLevel> enumeration.</span></span> <span data-ttu-id="5e457-118">El valor predeterminado es `BypassCache`.</span><span class="sxs-lookup"><span data-stu-id="5e457-118">The default value is `BypassCache`.</span></span>|  
|`unspecifiedMaximumAge`|<span data-ttu-id="5e457-119">Especifica el tiempo predeterminado después del cual el contenido se marca como expirado.</span><span class="sxs-lookup"><span data-stu-id="5e457-119">Specifies the default time after which content is marked as expired.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="5e457-120">Atributo policyLevel</span><span class="sxs-lookup"><span data-stu-id="5e457-120">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="5e457-121">{2&gt;Value&lt;2}</span><span class="sxs-lookup"><span data-stu-id="5e457-121">Value</span></span>|<span data-ttu-id="5e457-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="5e457-122">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="5e457-123">Devuelve el recurso almacenado en caché si el recurso es nuevo, la longitud del contenido es precisa y los atributos expiración, modificación y longitud del contenido están presentes.</span><span class="sxs-lookup"><span data-stu-id="5e457-123">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="5e457-124">Devuelve el recurso del servidor.</span><span class="sxs-lookup"><span data-stu-id="5e457-124">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="5e457-125">Devuelve el recurso almacenado en caché si la longitud del contenido está presente y coincide con el tamaño de entrada.</span><span class="sxs-lookup"><span data-stu-id="5e457-125">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="5e457-126">Devuelve el recurso almacenado en caché si se proporciona la longitud del contenido y coincide con el tamaño de entrada; de lo contrario, el recurso se descarga del servidor y se devuelve al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5e457-126">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="5e457-127">Devuelve el recurso almacenado en caché si la marca de tiempo del recurso almacenado en caché es igual que la marca de tiempo del recurso en el servidor; de lo contrario, el recurso se descarga del servidor, se almacena en la memoria caché y se devuelve al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5e457-127">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and is returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="5e457-128">Descarga el recurso del servidor, lo almacena en la memoria caché y devuelve el recurso al llamador.</span><span class="sxs-lookup"><span data-stu-id="5e457-128">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="5e457-129">Si existe un recurso almacenado en caché, se elimina.</span><span class="sxs-lookup"><span data-stu-id="5e457-129">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="5e457-130">El recurso se descarga del servidor y se devuelve al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5e457-130">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="5e457-131">Satisface una solicitud mediante la copia en caché del recurso si la marca de tiempo es igual que la marca de tiempo del recurso en el servidor. de lo contrario, el recurso se descarga del servidor, se presenta al autor de la llamada y se almacena en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="5e457-131">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and is stored in the cache,</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5e457-132">Elemento secundario</span><span class="sxs-lookup"><span data-stu-id="5e457-132">Child Elements</span></span>  
  
|<span data-ttu-id="5e457-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="5e457-133">Element</span></span>|<span data-ttu-id="5e457-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="5e457-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5e457-135">defaultHttpCachePolicy</span><span class="sxs-lookup"><span data-stu-id="5e457-135">defaultHttpCachePolicy</span></span>](defaulthttpcachepolicy-element-network-settings.md)|<span data-ttu-id="5e457-136">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="5e457-136">Optional element.</span></span><br /><br /> <span data-ttu-id="5e457-137">Describe si el almacenamiento en caché de HTTP está activo y describe la Directiva de almacenamiento en caché predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5e457-137">Describes whether HTTP caching is active and describes the default caching policy.</span></span>|  
|[<span data-ttu-id="5e457-138">\<elemento > defaultFtpCachePolicy (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="5e457-138">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>](defaultftpcachepolicy-element-network-settings.md)|<span data-ttu-id="5e457-139">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="5e457-139">Optional element.</span></span><br /><br /> <span data-ttu-id="5e457-140">Describe si el almacenamiento en caché de FTP está activo y describe la Directiva de almacenamiento en caché predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5e457-140">Describes whether FTP caching is active and describes the default caching policy.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5e457-141">Elemento principal</span><span class="sxs-lookup"><span data-stu-id="5e457-141">Parent Elements</span></span>  
  
|<span data-ttu-id="5e457-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="5e457-142">Element</span></span>|<span data-ttu-id="5e457-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="5e457-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5e457-144">system.net</span><span class="sxs-lookup"><span data-stu-id="5e457-144">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="5e457-145">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="5e457-145">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5e457-146">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5e457-146">Example</span></span>  
 <span data-ttu-id="5e457-147">En el ejemplo siguiente se muestra cómo deshabilitar todo el almacenamiento en caché.</span><span class="sxs-lookup"><span data-stu-id="5e457-147">The following example shows how to disable all caching.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching  
      disableAllCaching="true"  
    />  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5e457-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e457-148">See also</span></span>

- <xref:System.Net.Cache?displayProperty=nameWithType>
- [<span data-ttu-id="5e457-149">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="5e457-149">Network Settings Schema</span></span>](index.md)
