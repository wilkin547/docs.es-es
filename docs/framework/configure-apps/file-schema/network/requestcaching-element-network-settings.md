---
description: 'Más información acerca de: <requestCaching> elemento (configuración de red)'
title: Elemento <requestCaching> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requestCaching
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching
helpviewer_keywords:
- requestCaching element
- <requestCaching> element
ms.assetid: 9962a2fe-cbda-41a6-9377-571811eaea84
ms.openlocfilehash: d09da8ad7a38ac363aaa740cca4de25e33fa8c56
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698562"
---
# <a name="requestcaching-element-network-settings"></a><span data-ttu-id="912f5-103">Elemento \<requestCaching> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="912f5-103">\<requestCaching> Element (Network Settings)</span></span>

<span data-ttu-id="912f5-104">Controla el mecanismo de almacenamiento en caché para las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="912f5-104">Controls the caching mechanism for network requests.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<requestCaching>**  
  
## <a name="syntax"></a><span data-ttu-id="912f5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="912f5-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="912f5-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="912f5-106">Attributes and Elements</span></span>  

 <span data-ttu-id="912f5-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="912f5-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="912f5-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="912f5-108">Attributes</span></span>  
  
|<span data-ttu-id="912f5-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="912f5-109">Attribute</span></span>|<span data-ttu-id="912f5-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="912f5-110">Description</span></span>|  
|---------------|-----------------|  
|`isPrivateCache`|<span data-ttu-id="912f5-111">Especifica si la memoria caché proporciona aislamiento entre la información de los distintos usuarios.</span><span class="sxs-lookup"><span data-stu-id="912f5-111">Specifies whether the cache provides isolation between the information of different users.</span></span> <span data-ttu-id="912f5-112">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="912f5-112">The default value is `true`.</span></span> <span data-ttu-id="912f5-113">Este valor debe ser `false` para las aplicaciones de nivel intermedio.</span><span class="sxs-lookup"><span data-stu-id="912f5-113">This value should be `false` for middle tier applications.</span></span>|  
|`disableAllCaching`|<span data-ttu-id="912f5-114">Especifica que el almacenamiento en caché está deshabilitado para todas las respuestas web y no se puede invalidar mediante programación.</span><span class="sxs-lookup"><span data-stu-id="912f5-114">Specifies that caching is disabled for all Web responses, and cannot be overridden programmatically.</span></span>|  
|`defaultPolicyLevel`|<span data-ttu-id="912f5-115">Uno de los valores de la enumeración <xref:System.Net.Cache.RequestCacheLevel>.</span><span class="sxs-lookup"><span data-stu-id="912f5-115">One of the values in the <xref:System.Net.Cache.RequestCacheLevel> enumeration.</span></span> <span data-ttu-id="912f5-116">El valor predeterminado es `BypassCache`.</span><span class="sxs-lookup"><span data-stu-id="912f5-116">The default value is `BypassCache`.</span></span>|  
|`unspecifiedMaximumAge`|<span data-ttu-id="912f5-117">Especifica el tiempo predeterminado después del cual el contenido se marca como expirado.</span><span class="sxs-lookup"><span data-stu-id="912f5-117">Specifies the default time after which content is marked as expired.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="912f5-118">Atributo policyLevel</span><span class="sxs-lookup"><span data-stu-id="912f5-118">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="912f5-119">Value</span><span class="sxs-lookup"><span data-stu-id="912f5-119">Value</span></span>|<span data-ttu-id="912f5-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="912f5-120">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="912f5-121">Devuelve el recurso almacenado en caché si el recurso es nuevo, la longitud del contenido es precisa y los atributos expiración, modificación y longitud del contenido están presentes.</span><span class="sxs-lookup"><span data-stu-id="912f5-121">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="912f5-122">Devuelve el recurso del servidor.</span><span class="sxs-lookup"><span data-stu-id="912f5-122">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="912f5-123">Devuelve el recurso almacenado en caché si la longitud del contenido está presente y coincide con el tamaño de entrada.</span><span class="sxs-lookup"><span data-stu-id="912f5-123">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="912f5-124">Devuelve el recurso almacenado en caché si se proporciona la longitud del contenido y coincide con el tamaño de entrada; de lo contrario, el recurso se descarga del servidor y se devuelve al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="912f5-124">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="912f5-125">Devuelve el recurso almacenado en caché si la marca de tiempo del recurso almacenado en caché es igual que la marca de tiempo del recurso en el servidor; de lo contrario, el recurso se descarga del servidor, se almacena en la memoria caché y se devuelve al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="912f5-125">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and is returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="912f5-126">Descarga el recurso del servidor, lo almacena en la memoria caché y devuelve el recurso al llamador.</span><span class="sxs-lookup"><span data-stu-id="912f5-126">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="912f5-127">Si existe un recurso almacenado en caché, se elimina.</span><span class="sxs-lookup"><span data-stu-id="912f5-127">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="912f5-128">El recurso se descarga del servidor y se devuelve al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="912f5-128">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="912f5-129">Satisface una solicitud mediante la copia en caché del recurso si la marca de tiempo es igual que la marca de tiempo del recurso en el servidor. de lo contrario, el recurso se descarga del servidor, se presenta al autor de la llamada y se almacena en la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="912f5-129">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and is stored in the cache,</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="912f5-130">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="912f5-130">Child Elements</span></span>  
  
|<span data-ttu-id="912f5-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="912f5-131">Element</span></span>|<span data-ttu-id="912f5-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="912f5-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="912f5-133">defaultHttpCachePolicy</span><span class="sxs-lookup"><span data-stu-id="912f5-133">defaultHttpCachePolicy</span></span>](defaulthttpcachepolicy-element-network-settings.md)|<span data-ttu-id="912f5-134">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="912f5-134">Optional element.</span></span><br /><br /> <span data-ttu-id="912f5-135">Describe si el almacenamiento en caché de HTTP está activo y describe la Directiva de almacenamiento en caché predeterminada.</span><span class="sxs-lookup"><span data-stu-id="912f5-135">Describes whether HTTP caching is active and describes the default caching policy.</span></span>|  
|[<span data-ttu-id="912f5-136">Elemento \<defaultFtpCachePolicy> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="912f5-136">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>](defaultftpcachepolicy-element-network-settings.md)|<span data-ttu-id="912f5-137">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="912f5-137">Optional element.</span></span><br /><br /> <span data-ttu-id="912f5-138">Describe si el almacenamiento en caché de FTP está activo y describe la Directiva de almacenamiento en caché predeterminada.</span><span class="sxs-lookup"><span data-stu-id="912f5-138">Describes whether FTP caching is active and describes the default caching policy.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="912f5-139">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="912f5-139">Parent Elements</span></span>  
  
|<span data-ttu-id="912f5-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="912f5-140">Element</span></span>|<span data-ttu-id="912f5-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="912f5-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="912f5-142">system.net</span><span class="sxs-lookup"><span data-stu-id="912f5-142">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="912f5-143">Contiene valores que especifican cómo se conecta .NET Framework a la red.</span><span class="sxs-lookup"><span data-stu-id="912f5-143">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="912f5-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="912f5-144">Example</span></span>  

 <span data-ttu-id="912f5-145">En el ejemplo siguiente se muestra cómo deshabilitar todo el almacenamiento en caché.</span><span class="sxs-lookup"><span data-stu-id="912f5-145">The following example shows how to disable all caching.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching  
      disableAllCaching="true"  
    />  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="912f5-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="912f5-146">See also</span></span>

- <xref:System.Net.Cache?displayProperty=nameWithType>
- [<span data-ttu-id="912f5-147">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="912f5-147">Network Settings Schema</span></span>](index.md)
