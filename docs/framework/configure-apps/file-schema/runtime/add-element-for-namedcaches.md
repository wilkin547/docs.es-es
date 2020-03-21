---
title: Elemento <add> para <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: c1345022b79df371ad9c89a39a0a8b625e26608c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154510"
---
# <a name="add-element-for-namedcaches"></a><span data-ttu-id="a593e-102">\<agregue> \<Element para namedCaches></span><span class="sxs-lookup"><span data-stu-id="a593e-102">\<add> Element for \<namedCaches></span></span>
<span data-ttu-id="a593e-103">Agrega una `namedCache` entrada `namedCaches` a la colección para una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="a593e-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
<span data-ttu-id="a593e-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a593e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a593e-105">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="a593e-105">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="a593e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="a593e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span></span>\
<span data-ttu-id="a593e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="a593e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)</span></span>\
<span data-ttu-id="a593e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<añadir>**</span><span class="sxs-lookup"><span data-stu-id="a593e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a593e-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a593e-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="Default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="a593e-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="a593e-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a593e-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a593e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a593e-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a593e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a593e-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="a593e-113">Attributes</span></span>  
  
|<span data-ttu-id="a593e-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="a593e-114">Attribute</span></span>|<span data-ttu-id="a593e-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="a593e-115">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="a593e-116">Un valor entero que especifica el tamaño máximo permitido (en <xref:System.Runtime.Caching.MemoryCache> megabytes) al que puede crecer una instancia de a.</span><span class="sxs-lookup"><span data-stu-id="a593e-116">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="a593e-117">El valor predeterminado es 0, <xref:System.Runtime.Caching.MemoryCache> lo que significa que la heurística de autodimensionamiento de la clase se usa de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a593e-117">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="a593e-118">Nombre de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="a593e-118">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="a593e-119">Un valor entero entre 0 y 100 que especifica el porcentaje máximo de memoria del equipo instalada físicamente que puede consumir la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="a593e-119">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="a593e-120">El valor predeterminado es 0, <xref:System.Runtime.Caching.MemoryCache> lo que significa que la heurística de autodimensionamiento de la clase se usa de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a593e-120">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="a593e-121">Valor que indica el intervalo de tiempo después del cual la implementación de caché compara la carga de memoria actual con los límites de memoria absoluto y de porcentaje que están establecidos para la instancia de caché.</span><span class="sxs-lookup"><span data-stu-id="a593e-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="a593e-122">Este valor se introduce en formato "HH:MM:SS".</span><span class="sxs-lookup"><span data-stu-id="a593e-122">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a593e-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a593e-123">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="a593e-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a593e-124">Parent Elements</span></span>  
  
|<span data-ttu-id="a593e-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="a593e-125">Element</span></span>|<span data-ttu-id="a593e-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="a593e-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a593e-127">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="a593e-127">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="a593e-128">Contiene una colección de <xref:System.Runtime.Caching.MemoryCache> valores de configuración para las instancias con nombre.</span><span class="sxs-lookup"><span data-stu-id="a593e-128">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a593e-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a593e-129">Remarks</span></span>  
 <span data-ttu-id="a593e-130">El `add` elemento agrega una `namedCaches` entrada a la colección para una memoria caché de memoria.</span><span class="sxs-lookup"><span data-stu-id="a593e-130">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="a593e-131">Puede usar el elemento [clear](clear-element-for-namedcaches.md) `add` antes de usar el elemento para estar seguro de que no hay otras cachés con nombre en la colección.</span><span class="sxs-lookup"><span data-stu-id="a593e-131">You can use the [clear](clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="a593e-132">Este elemento se puede utilizar en el archivo machine.config y en el archivo Web.config.</span><span class="sxs-lookup"><span data-stu-id="a593e-132">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a593e-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a593e-133">Example</span></span>  
 <span data-ttu-id="a593e-134">En el ejemplo siguiente se muestra `namedCache` cómo `namedCaches` definir la configuración de la entrada predeterminada a la colección para una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="a593e-134">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="Default"
               cacheMemoryLimitMegabytes="0"
               physicalMemoryPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a593e-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a593e-135">See also</span></span>

- [<span data-ttu-id="a593e-136">\<NamedCaches> Element (Configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="a593e-136">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
