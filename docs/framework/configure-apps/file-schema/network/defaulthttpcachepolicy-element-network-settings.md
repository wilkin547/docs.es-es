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
ms.openlocfilehash: 4120c57fbb65da1c124414cbe9cfba7ae64388f8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190324"
---
# <a name="defaulthttpcachepolicy-element-network-settings"></a><span data-ttu-id="c79af-102">Elemento \<defaultHttpCachePolicy> (configuración de red)</span><span class="sxs-lookup"><span data-stu-id="c79af-102">\<defaultHttpCachePolicy> Element (Network Settings)</span></span>

<span data-ttu-id="c79af-103">Describe si el almacenamiento en caché de HTTP está activo y describe la Directiva de almacenamiento en caché predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c79af-103">Describes whether HTTP caching is active and describes the default caching policy.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<requestCaching>**](requestcaching-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultHttpCachePolicy>**

## <a name="syntax"></a><span data-ttu-id="c79af-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c79af-104">Syntax</span></span>  
  
```xml  
<defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss|minValue|maxValue"  
  maximumAge="d.hh:mm:ss|minValue|maxValue"  
  maximumStale="d.hh:mm:ss|minValue|maxValue"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c79af-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c79af-105">Attributes and Elements</span></span>  

 <span data-ttu-id="c79af-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c79af-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c79af-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="c79af-107">Attributes</span></span>  
  
|<span data-ttu-id="c79af-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="c79af-108">Attribute</span></span>|<span data-ttu-id="c79af-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="c79af-109">Description</span></span>|  
|---------------|-----------------|  
|`maximumAge`|<span data-ttu-id="c79af-110">Especifica el intervalo de tiempo máximo antes de que un objeto almacenado en memoria caché se marque como expirado.</span><span class="sxs-lookup"><span data-stu-id="c79af-110">Specifies the maximum time interval before a cached object is marked as expired.</span></span>|  
|`maximumStale`|<span data-ttu-id="c79af-111">Especifica el tiempo máximo después del tiempo de actualización calculado antes de que un objeto almacenado en memoria caché se marque como expirado.</span><span class="sxs-lookup"><span data-stu-id="c79af-111">Specifies the maximum time past the computed freshness time before a cached object is marked as expired.</span></span>|  
|`minimumFresh`|<span data-ttu-id="c79af-112">Especifica el tiempo mínimo que un objeto almacenado en memoria caché se debe considerar actualizado.</span><span class="sxs-lookup"><span data-stu-id="c79af-112">Specifies the minimum time for a cached object to be considered fresh.</span></span>|  
|`policyLevel`|<span data-ttu-id="c79af-113">Especifica si la Directiva de almacenamiento en caché es automática o si se omite la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="c79af-113">Specifies whether the caching policy is automatic, or whether the cache is bypassed.</span></span> <span data-ttu-id="c79af-114">El valor predeterminado es `BypassCache`.</span><span class="sxs-lookup"><span data-stu-id="c79af-114">The default value is `BypassCache`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c79af-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c79af-115">Child Elements</span></span>  

 <span data-ttu-id="c79af-116">None</span><span class="sxs-lookup"><span data-stu-id="c79af-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c79af-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c79af-117">Parent Elements</span></span>  
  
|<span data-ttu-id="c79af-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="c79af-118">Element</span></span>|<span data-ttu-id="c79af-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="c79af-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c79af-120">requestCaching</span><span class="sxs-lookup"><span data-stu-id="c79af-120">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="c79af-121">Controla el mecanismo de almacenamiento en caché para las solicitudes de red.</span><span class="sxs-lookup"><span data-stu-id="c79af-121">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c79af-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c79af-122">Remarks</span></span>  

 <span data-ttu-id="c79af-123">El valor del `policyLevel` atributo es `BypassCache` o `Default` .</span><span class="sxs-lookup"><span data-stu-id="c79af-123">The value for the `policyLevel` attribute is either `BypassCache` or `Default`.</span></span>  
  
 <span data-ttu-id="c79af-124">Los valores de `maximumAge` los `maximumStale` elementos, y `minimumFresh` son un intervalo de tiempo explícito con un formato de *d*.\* HH*:*mm*:*SS\* (días, horas, minutos y segundos), o las constantes `minValue` o `maxValue` , según corresponda.</span><span class="sxs-lookup"><span data-stu-id="c79af-124">Values for the `maximumAge`, `maximumStale`, and `minimumFresh` elements are either an explicit time interval with a format of *d*.*hh*:*mm*:*ss* (days, hours, minutes, and seconds), or the constants `minValue` or `maxValue`, as appropriate.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="c79af-125">Archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="c79af-125">Configuration Files</span></span>  

 <span data-ttu-id="c79af-126">Este elemento se puede usar en el archivo de configuración de la aplicación o en el archivo de configuración del equipo (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="c79af-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c79af-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c79af-127">Example</span></span>  

 <span data-ttu-id="c79af-128">En el ejemplo siguiente se muestra cómo especificar una hora de actualización mínima de seis horas, una duración máxima de dos días y un tiempo de expiración máximo de cuatro horas.</span><span class="sxs-lookup"><span data-stu-id="c79af-128">The following example shows how to specify a minimum fresh time of six hours, a maximum age time of two days, and a maximum stale time of four hours.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c79af-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c79af-129">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="c79af-130">Esquema de la configuración de red</span><span class="sxs-lookup"><span data-stu-id="c79af-130">Network Settings Schema</span></span>](index.md)
