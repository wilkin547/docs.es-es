---
title: Elemento <defaultHttpCachePolicy> (configuración de red)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultHttpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultHttpCachePolicy
helpviewer_keywords:
- defaultHttpCachePolicy element
- <defaultHttpCachePolicy> element
ms.assetid: 2c1247d0-39b0-4c12-919a-a925ce075c79
ms.openlocfilehash: f3b029e8b931e976bee85c98dd926e020c5b8743
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698275"
---
# <a name="defaulthttpcachepolicy-element-network-settings"></a><span data-ttu-id="9fe20-102">\<defaultHttpCachePolicy (elemento >) (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="9fe20-102">\<defaultHttpCachePolicy> Element (Network Settings)</span></span>
<span data-ttu-id="9fe20-103">Describe si el almacenamiento en caché de HTTP está activo y describe la Directiva de almacenamiento en caché predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9fe20-103">Describes whether HTTP caching is active and describes the default caching policy.</span></span>  
  
[<span data-ttu-id="9fe20-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="9fe20-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="9fe20-105">&nbsp; @ no__t-1[ **@no__t -4System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="9fe20-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="9fe20-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<requestCaching >** ](requestcaching-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="9fe20-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<requestCaching>**](requestcaching-element-network-settings.md)</span></span>  
<span data-ttu-id="9fe20-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<defaultHttpCachePolicy >**</span><span class="sxs-lookup"><span data-stu-id="9fe20-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultHttpCachePolicy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fe20-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9fe20-108">Syntax</span></span>  
  
```xml  
<defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss|minValue|maxValue"  
  maximumAge="d.hh:mm:ss|minValue|maxValue"  
  maximumStale="d.hh:mm:ss|minValue|maxValue"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9fe20-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9fe20-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9fe20-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9fe20-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9fe20-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="9fe20-111">Attributes</span></span>  
  
|<span data-ttu-id="9fe20-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="9fe20-112">Attribute</span></span>|<span data-ttu-id="9fe20-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="9fe20-113">Description</span></span>|  
|---------------|-----------------|  
|`maximumAge`|<span data-ttu-id="9fe20-114">Especifica el intervalo de tiempo máximo antes de que un objeto almacenado en memoria caché se marque como expirado.</span><span class="sxs-lookup"><span data-stu-id="9fe20-114">Specifies the maximum time interval before a cached object is marked as expired.</span></span>|  
|`maximumStale`|<span data-ttu-id="9fe20-115">Especifica el tiempo máximo después del tiempo de actualización calculado antes de que un objeto almacenado en memoria caché se marque como expirado.</span><span class="sxs-lookup"><span data-stu-id="9fe20-115">Specifies the maximum time past the computed freshness time before a cached object is marked as expired.</span></span>|  
|`minimumFresh`|<span data-ttu-id="9fe20-116">Especifica el tiempo mínimo que un objeto almacenado en memoria caché se debe considerar actualizado.</span><span class="sxs-lookup"><span data-stu-id="9fe20-116">Specifies the minimum time for a cached object to be considered fresh.</span></span>|  
|`policyLevel`|<span data-ttu-id="9fe20-117">Especifica si la Directiva de almacenamiento en caché es automática o si se omite la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="9fe20-117">Specifies whether the caching policy is automatic, or whether the cache is bypassed.</span></span> <span data-ttu-id="9fe20-118">El valor predeterminado es `BypassCache`.</span><span class="sxs-lookup"><span data-stu-id="9fe20-118">The default value is `BypassCache`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9fe20-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9fe20-119">Child Elements</span></span>  
 <span data-ttu-id="9fe20-120">Ninguna</span><span class="sxs-lookup"><span data-stu-id="9fe20-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9fe20-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9fe20-121">Parent Elements</span></span>  
  
|<span data-ttu-id="9fe20-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="9fe20-122">Element</span></span>|<span data-ttu-id="9fe20-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="9fe20-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9fe20-124">requestCaching</span><span class="sxs-lookup"><span data-stu-id="9fe20-124">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="9fe20-125">Controla el mecanismo de almacenamiento en caché para las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="9fe20-125">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9fe20-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9fe20-126">Remarks</span></span>  
 <span data-ttu-id="9fe20-127">El valor del atributo `policyLevel` es `BypassCache` o `Default`.</span><span class="sxs-lookup"><span data-stu-id="9fe20-127">The value for the `policyLevel` attribute is either `BypassCache` or `Default`.</span></span>  
  
 <span data-ttu-id="9fe20-128">Los valores de los elementos `maximumAge`, `maximumStale` y `minimumFresh` son un intervalo de tiempo explícito con un formato de *d*. *HH*:*mm*:*SS* (días, horas, minutos y segundos), o las constantes `minValue` o `maxValue`, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="9fe20-128">Values for the `maximumAge`, `maximumStale`, and `minimumFresh` elements are either an explicit time interval with a format of *d*.*hh*:*mm*:*ss* (days, hours, minutes, and seconds), or the constants `minValue` or `maxValue`, as appropriate.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="9fe20-129">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="9fe20-129">Configuration Files</span></span>  
 <span data-ttu-id="9fe20-130">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="9fe20-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9fe20-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9fe20-131">Example</span></span>  
 <span data-ttu-id="9fe20-132">En el ejemplo siguiente se muestra cómo especificar una hora de actualización mínima de seis horas, una duración máxima de dos días y un tiempo de expiración máximo de cuatro horas.</span><span class="sxs-lookup"><span data-stu-id="9fe20-132">The following example shows how to specify a minimum fresh time of six hours, a maximum age time of two days, and a maximum stale time of four hours.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultHttpCachePolicy  
        minimumFresh="0.06:00:00"  
        maximumAge="2.00:00:00"  
        maximumStale="0.04:00:00"
      />  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9fe20-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="9fe20-133">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="9fe20-134">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="9fe20-134">Network Settings Schema</span></span>](index.md)
