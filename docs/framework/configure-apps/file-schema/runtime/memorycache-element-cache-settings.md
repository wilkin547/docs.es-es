---
description: 'Más información sobre: <memoryCache> elemento (configuración de caché)'
title: Elemento <memoryCache> (configuración de caché)
ms.date: 03/30/2017
helpviewer_keywords:
- <memoryCache> element
- caching [.NET Framework], configuration
- memoryCache element
ms.assetid: 182a622f-f7cf-472d-9d0b-451d2fd94525
ms.openlocfilehash: 1d46a156a222a0dc54e27cf56a5eb06cb1a908be
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782343"
---
# <a name="memorycache-element-cache-settings"></a><span data-ttu-id="3dc14-103">Elemento \<memoryCache> (configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="3dc14-103">\<memoryCache> Element (Cache Settings)</span></span>

<span data-ttu-id="3dc14-104">Define un elemento que se usa para configurar una memoria caché basada en la clase <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="3dc14-104">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span> <span data-ttu-id="3dc14-105">La clase <xref:System.Runtime.Caching.Configuration.MemoryCacheElement> define un elemento [memoryCache](memorycache-element-cache-settings.md) que se puede usar para configurar la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="3dc14-105">The <xref:System.Runtime.Caching.Configuration.MemoryCacheElement> class defines a [memoryCache](memorycache-element-cache-settings.md) element that you can use to configure the cache.</span></span> <span data-ttu-id="3dc14-106">Se pueden usar varias instancias de la clase <xref:System.Runtime.Caching.MemoryCache> en una sola aplicación.</span><span class="sxs-lookup"><span data-stu-id="3dc14-106">Multiple instances of the <xref:System.Runtime.Caching.MemoryCache> class can be used in a single application.</span></span> <span data-ttu-id="3dc14-107">Cada elemento `memoryCache` del archivo de configuración puede contener valores de configuración para una instancia de <xref:System.Runtime.Caching.MemoryCache> con nombre.</span><span class="sxs-lookup"><span data-stu-id="3dc14-107">Each `memoryCache` element in the configuration file can contain settings for a named <xref:System.Runtime.Caching.MemoryCache> instance.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<memoryCache>**  
  
## <a name="syntax"></a><span data-ttu-id="3dc14-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3dc14-108">Syntax</span></span>  
  
```xml  
<memoryCache>
    <namedCaches>  
        <!-- child elements -->  
    </namedCaches>
</memoryCache>  
```  
  
## <a name="type"></a><span data-ttu-id="3dc14-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="3dc14-109">Type</span></span>  

 <span data-ttu-id="3dc14-110">Clase<xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="3dc14-110"><xref:System.Runtime.Caching.MemoryCache> class.</span></span>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3dc14-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3dc14-111">Attributes and Elements</span></span>  

 <span data-ttu-id="3dc14-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3dc14-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3dc14-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="3dc14-113">Attributes</span></span>  
  
|<span data-ttu-id="3dc14-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="3dc14-114">Attribute</span></span>|<span data-ttu-id="3dc14-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="3dc14-115">Description</span></span>|  
|---------------|-----------------|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="3dc14-116">Tamaño máximo de memoria (en megabytes) que puede alcanzar una instancia de un objeto <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="3dc14-116">The maximum memory size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> object can grow to.</span></span> <span data-ttu-id="3dc14-117">El valor predeterminado es 0, lo que significa que se usa de forma predeterminada la heurística de ajuste automático de tamaño de la clase <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="3dc14-117">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosize heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="3dc14-118">Nombre de la configuración de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="3dc14-118">The name of the cache configuration.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="3dc14-119">Porcentaje de memoria física que la memoria caché puede usar.</span><span class="sxs-lookup"><span data-stu-id="3dc14-119">The percentage of physical memory that can be used by the cache.</span></span> <span data-ttu-id="3dc14-120">El valor predeterminado es 0, lo que significa que se usa de forma predeterminada la heurística de ajuste automático de tamaño de la clase <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="3dc14-120">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosize heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="3dc14-121">Valor que indica el intervalo de tiempo después del cual la implementación de caché compara la carga de memoria actual con los límites de memoria absoluto y de porcentaje que están establecidos para la instancia de caché.</span><span class="sxs-lookup"><span data-stu-id="3dc14-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="3dc14-122">El valor se especifica en formato "HH:MM:SS".</span><span class="sxs-lookup"><span data-stu-id="3dc14-122">The value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3dc14-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3dc14-123">Child Elements</span></span>  
  
|<span data-ttu-id="3dc14-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="3dc14-124">Element</span></span>|<span data-ttu-id="3dc14-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="3dc14-125">Description</span></span>|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|<span data-ttu-id="3dc14-126">Contiene una colección de valores de configuración para la instancia de `namedCache` .</span><span class="sxs-lookup"><span data-stu-id="3dc14-126">Contains a collection of configuration settings for the `namedCache` instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3dc14-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3dc14-127">Parent Elements</span></span>  
  
|<span data-ttu-id="3dc14-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="3dc14-128">Element</span></span>|<span data-ttu-id="3dc14-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="3dc14-129">Description</span></span>|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|<span data-ttu-id="3dc14-130">Especifica el elemento raíz de cada archivo de configuración usado por las aplicaciones Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3dc14-130">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[\<system.runtime.caching>](system-runtime-caching-element-cache-settings.md)|<span data-ttu-id="3dc14-131">Contiene tipos que permiten implementar el almacenamiento en caché de resultados en las aplicaciones integradas en el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3dc14-131">Contains types that let you implement output caching in applications that are built into the .NET Framework.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3dc14-132">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3dc14-132">Remarks</span></span>  

 <span data-ttu-id="3dc14-133">La clase <xref:System.Runtime.Caching.MemoryCache> es una implementación concreta de la clase abstracta <xref:System.Runtime.Caching.ObjectCache> .</span><span class="sxs-lookup"><span data-stu-id="3dc14-133">The <xref:System.Runtime.Caching.MemoryCache> class is a concrete implementation of the abstract <xref:System.Runtime.Caching.ObjectCache> class.</span></span> <span data-ttu-id="3dc14-134">Se puede proporcionar información de configuración a las instancias de la clase <xref:System.Runtime.Caching.MemoryCache> a partir de archivos de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3dc14-134">Instances of the <xref:System.Runtime.Caching.MemoryCache> class can be supplied with configuration information from application configuration files.</span></span> <span data-ttu-id="3dc14-135">La sección de configuración [memoryCache](memorycache-element-cache-settings.md) contiene una colección de configuración `namedCaches` .</span><span class="sxs-lookup"><span data-stu-id="3dc14-135">The [memoryCache](memorycache-element-cache-settings.md) configuration section contains a `namedCaches` configuration collection.</span></span>  
  
 <span data-ttu-id="3dc14-136">Cuando se inicializa un objeto de la caché basada en memoria, primero intenta encontrar una entrada `namedCaches` que coincida con el nombre del parámetro que se pasa al constructor de memoria caché.</span><span class="sxs-lookup"><span data-stu-id="3dc14-136">When a memory-based cache object is initialized, it first tries to find a `namedCaches` entry that matches the name in the parameter that is passed to the memory cache constructor.</span></span> <span data-ttu-id="3dc14-137">Si se encuentra una entrada `namedCaches` , se recupera la información de sondeo y administración de memoria del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="3dc14-137">If a `namedCaches` entry is found, the polling and memory-management information are retrieved from the configuration file.</span></span>  
  
 <span data-ttu-id="3dc14-138">Después, el proceso de inicialización determina si se ha reemplazado alguna entrada de configuración. Para ello, usa la colección opcional de pares nombre-valor de la información de configuración del constructor.</span><span class="sxs-lookup"><span data-stu-id="3dc14-138">The initialization process then determines whether any configuration entries were overridden, by using the optional collection of name/value pairs of configuration information in the constructor.</span></span> <span data-ttu-id="3dc14-139">Si pasa alguno de los valores siguientes en la colección de pares nombre-valor, estos valores reemplazarán la información obtenida del archivo de configuración:</span><span class="sxs-lookup"><span data-stu-id="3dc14-139">If you pass any one of the following values in the name/value pair collection, these values override information obtained from the configuration file:</span></span>  
  
- <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.CacheMemoryLimitMegabytes%2A>  
  
- <xref:System.Runtime.Caching.Configuration.MemoryCacheElement.PhysicalMemoryLimitPercentage%2A>  
  
- <xref:System.Runtime.Caching.MemoryCache.PollingInterval%2A>  
  
## <a name="example"></a><span data-ttu-id="3dc14-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3dc14-140">Example</span></span>  

 <span data-ttu-id="3dc14-141">En el ejemplo siguiente se muestra cómo establecer el nombre del <xref:System.Runtime.Caching.MemoryCache> objeto en el nombre del objeto de caché predeterminado estableciendo el `name` atributo en "default".</span><span class="sxs-lookup"><span data-stu-id="3dc14-141">The following example shows how to set the name of the <xref:System.Runtime.Caching.MemoryCache> object to the default cache object name by setting the `name` attribute to "Default".</span></span>  
  
 <span data-ttu-id="3dc14-142">Los atributos `cacheMemoryLimitMegabytes` y `physicalMemoryLimitPercentage` se establecen en cero.</span><span class="sxs-lookup"><span data-stu-id="3dc14-142">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryLimitPercentage` attribute are set to zero.</span></span> <span data-ttu-id="3dc14-143">El hecho de establecer estos atributos en cero implica que la heurística de ajuste automático de tamaño de <xref:System.Runtime.Caching.MemoryCache> se usa de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3dc14-143">Setting these attributes to zero means that the <xref:System.Runtime.Caching.MemoryCache> autosizing heuristics are used by default.</span></span> <span data-ttu-id="3dc14-144">La implementación de la memoria caché debe comparar cada dos minutos la carga de memoria actual con los límites de memoria absoluto y de porcentaje.</span><span class="sxs-lookup"><span data-stu-id="3dc14-144">The cache implementation should compare the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
```xml  
<configuration>  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="Default"
               cacheMemoryLimitMegabytes="0"
               physicalMemoryLimitPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3dc14-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="3dc14-145">See also</span></span>

- <xref:System.Runtime.Caching.MemoryCache>
- [<span data-ttu-id="3dc14-146">\<system.runtime.caching> (Elemento, configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="3dc14-146">\<system.runtime.caching> Element (Cache Settings)</span></span>](system-runtime-caching-element-cache-settings.md)
- [<span data-ttu-id="3dc14-147">\<namedCaches> (Elemento, configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="3dc14-147">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
