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
ms.openlocfilehash: c5029a7d1e53c28d0abb232efdc3e0bd2c9658d4
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088416"
---
# <a name="defaulthttpcachepolicy-element-network-settings"></a><span data-ttu-id="d01d0-102">Elemento \<defaultHttpCachePolicy> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="d01d0-102">\<defaultHttpCachePolicy> Element (Network Settings)</span></span>
<span data-ttu-id="d01d0-103">Describe si el almacenamiento en caché de HTTP está activo y describe la Directiva de almacenamiento en caché predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d01d0-103">Describes whether HTTP caching is active and describes the default caching policy.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<requestCaching>**](requestcaching-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultHttpCachePolicy>**

## <a name="syntax"></a><span data-ttu-id="d01d0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d01d0-104">Syntax</span></span>  
  
```xml  
<defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss|minValue|maxValue"  
  maximumAge="d.hh:mm:ss|minValue|maxValue"  
  maximumStale="d.hh:mm:ss|minValue|maxValue"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d01d0-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d01d0-105">Attributes and Elements</span></span>  
 <span data-ttu-id="d01d0-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d01d0-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d01d0-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="d01d0-107">Attributes</span></span>  
  
|<span data-ttu-id="d01d0-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="d01d0-108">Attribute</span></span>|<span data-ttu-id="d01d0-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="d01d0-109">Description</span></span>|  
|---------------|-----------------|  
|`maximumAge`|<span data-ttu-id="d01d0-110">Especifica el intervalo de tiempo máximo antes de que un objeto almacenado en memoria caché se marque como expirado.</span><span class="sxs-lookup"><span data-stu-id="d01d0-110">Specifies the maximum time interval before a cached object is marked as expired.</span></span>|  
|`maximumStale`|<span data-ttu-id="d01d0-111">Especifica el tiempo máximo después del tiempo de actualización calculado antes de que un objeto almacenado en memoria caché se marque como expirado.</span><span class="sxs-lookup"><span data-stu-id="d01d0-111">Specifies the maximum time past the computed freshness time before a cached object is marked as expired.</span></span>|  
|`minimumFresh`|<span data-ttu-id="d01d0-112">Especifica el tiempo mínimo que un objeto almacenado en memoria caché se debe considerar actualizado.</span><span class="sxs-lookup"><span data-stu-id="d01d0-112">Specifies the minimum time for a cached object to be considered fresh.</span></span>|  
|`policyLevel`|<span data-ttu-id="d01d0-113">Especifica si la Directiva de almacenamiento en caché es automática o si se omite la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="d01d0-113">Specifies whether the caching policy is automatic, or whether the cache is bypassed.</span></span> <span data-ttu-id="d01d0-114">El valor predeterminado es `BypassCache`.</span><span class="sxs-lookup"><span data-stu-id="d01d0-114">The default value is `BypassCache`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d01d0-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d01d0-115">Child Elements</span></span>  
 <span data-ttu-id="d01d0-116">None</span><span class="sxs-lookup"><span data-stu-id="d01d0-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d01d0-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d01d0-117">Parent Elements</span></span>  
  
|<span data-ttu-id="d01d0-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="d01d0-118">Element</span></span>|<span data-ttu-id="d01d0-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="d01d0-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d01d0-120">requestCaching</span><span class="sxs-lookup"><span data-stu-id="d01d0-120">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="d01d0-121">Controla el mecanismo de almacenamiento en caché para las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="d01d0-121">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d01d0-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d01d0-122">Remarks</span></span>  
 <span data-ttu-id="d01d0-123">El valor del `policyLevel` atributo es `BypassCache` o `Default` .</span><span class="sxs-lookup"><span data-stu-id="d01d0-123">The value for the `policyLevel` attribute is either `BypassCache` or `Default`.</span></span>  
  
 <span data-ttu-id="d01d0-124">Los valores de `maximumAge` los `maximumStale` elementos, y `minimumFresh` son un intervalo de tiempo explícito con un formato de *d*.\* HH*:*mm*:*SS\* (días, horas, minutos y segundos), o las constantes `minValue` o `maxValue` , según corresponda.</span><span class="sxs-lookup"><span data-stu-id="d01d0-124">Values for the `maximumAge`, `maximumStale`, and `minimumFresh` elements are either an explicit time interval with a format of *d*.*hh*:*mm*:*ss* (days, hours, minutes, and seconds), or the constants `minValue` or `maxValue`, as appropriate.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="d01d0-125">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="d01d0-125">Configuration Files</span></span>  
 <span data-ttu-id="d01d0-126">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="d01d0-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d01d0-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d01d0-127">Example</span></span>  
 <span data-ttu-id="d01d0-128">En el ejemplo siguiente se muestra cómo especificar una hora de actualización mínima de seis horas, una duración máxima de dos días y un tiempo de expiración máximo de cuatro horas.</span><span class="sxs-lookup"><span data-stu-id="d01d0-128">The following example shows how to specify a minimum fresh time of six hours, a maximum age time of two days, and a maximum stale time of four hours.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d01d0-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d01d0-129">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="d01d0-130">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="d01d0-130">Network Settings Schema</span></span>](index.md)
