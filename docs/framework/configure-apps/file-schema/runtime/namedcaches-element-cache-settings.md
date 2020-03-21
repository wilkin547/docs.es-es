---
title: Elemento <namedCaches> (configuración de caché)
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
ms.openlocfilehash: e0640ca18d386141f3c03135019eb4fe959b5bf8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153963"
---
# <a name="namedcaches-element-cache-settings"></a><span data-ttu-id="22f9c-102">\<NamedCaches> Element (Configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="22f9c-102">\<namedCaches> Element (Cache Settings)</span></span>
<span data-ttu-id="22f9c-103">Especifica una colección de valores <xref:System.Runtime.Caching.MemoryCache> de configuración para las instancias con nombre.</span><span class="sxs-lookup"><span data-stu-id="22f9c-103">Specifies a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span> <span data-ttu-id="22f9c-104">La <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> propiedad hace referencia a la `namedCaches` colección de valores de configuración de uno o varios elementos del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="22f9c-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> property references the collection of configuration settings from one or more `namedCaches` elements of the configuration file.</span></span>  
  
<span data-ttu-id="22f9c-105">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="22f9c-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="22f9c-106">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="22f9c-106">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="22f9c-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="22f9c-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span></span>\
<span data-ttu-id="22f9c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namedCaches>**</span><span class="sxs-lookup"><span data-stu-id="22f9c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namedCaches>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22f9c-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="22f9c-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
  <add name="default"/>
</namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="22f9c-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="22f9c-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22f9c-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="22f9c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="22f9c-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="22f9c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22f9c-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="22f9c-113">Attributes</span></span>  
  
|<span data-ttu-id="22f9c-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="22f9c-114">Attribute</span></span>|<span data-ttu-id="22f9c-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="22f9c-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|<span data-ttu-id="22f9c-116">Un valor entero que especifica el tamaño máximo permitido, en <xref:System.Runtime.Caching.MemoryCache> megabytes, al que puede crecer una instancia de a.</span><span class="sxs-lookup"><span data-stu-id="22f9c-116">An integer value that specifies the maximum allowable size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="22f9c-117">El valor predeterminado es 0, lo que significa que <xref:System.Runtime.Caching.MemoryCache> la heurística de autodimensionamiento de la clase se utiliza de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="22f9c-117">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`name`|<span data-ttu-id="22f9c-118">Nombre de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="22f9c-118">The name of the cache.</span></span>|  
|`physicalMemoryLimitPercentage`|<span data-ttu-id="22f9c-119">Un valor entero entre 0 y 100 que especifica el porcentaje máximo de memoria del equipo instalada físicamente que puede consumir la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="22f9c-119">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="22f9c-120">El valor predeterminado es 0, lo que significa que <xref:System.Runtime.Caching.MemoryCache> la heurística de autodimensionamiento de la clase se utiliza de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="22f9c-120">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`pollingInterval`|<span data-ttu-id="22f9c-121">Valor que indica el intervalo de tiempo después del cual la implementación de caché compara la carga de memoria actual con los límites de memoria absoluto y de porcentaje que están establecidos para la instancia de caché.</span><span class="sxs-lookup"><span data-stu-id="22f9c-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="22f9c-122">Este valor se introduce en formato "HH:MM:SS".</span><span class="sxs-lookup"><span data-stu-id="22f9c-122">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="22f9c-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="22f9c-123">Child Elements</span></span>  
  
|<span data-ttu-id="22f9c-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="22f9c-124">Element</span></span>|<span data-ttu-id="22f9c-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="22f9c-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="22f9c-126">\<añadir></span><span class="sxs-lookup"><span data-stu-id="22f9c-126">\<add></span></span>](add-element-for-namedcaches.md)|<span data-ttu-id="22f9c-127">Agrega una caché con nombre a la colección `namedCaches` de una caché en memoria.</span><span class="sxs-lookup"><span data-stu-id="22f9c-127">Adds a named cache to the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="22f9c-128">\<>claro</span><span class="sxs-lookup"><span data-stu-id="22f9c-128">\<clear></span></span>](clear-element-for-namedcaches.md)|<span data-ttu-id="22f9c-129">Borra la colección `namedCaches` de una caché en memoria.</span><span class="sxs-lookup"><span data-stu-id="22f9c-129">Clears the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="22f9c-130">\<eliminar></span><span class="sxs-lookup"><span data-stu-id="22f9c-130">\<remove></span></span>](remove-element-for-namedcaches.md)|<span data-ttu-id="22f9c-131">Quita una entrada de caché con nombre de la colección `namedCaches` de una caché en memoria.</span><span class="sxs-lookup"><span data-stu-id="22f9c-131">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="22f9c-132">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="22f9c-132">Parent Elements</span></span>  
  
|<span data-ttu-id="22f9c-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="22f9c-133">Element</span></span>|<span data-ttu-id="22f9c-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="22f9c-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="22f9c-135">\<configuración></span><span class="sxs-lookup"><span data-stu-id="22f9c-135">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="22f9c-136">Especifica el elemento raíz en cada archivo de configuración que usan las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="22f9c-136">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="22f9c-137">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="22f9c-137">\<memoryCache></span></span>](memorycache-element-cache-settings.md)|<span data-ttu-id="22f9c-138">Define un elemento que se usa para configurar una memoria caché basada en la clase <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="22f9c-138">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
|[<span data-ttu-id="22f9c-139">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="22f9c-139">\<system.runtime.caching></span></span>](system-runtime-caching-element-cache-settings.md)|<span data-ttu-id="22f9c-140">Contiene tipos que permiten implementar el almacenamiento en caché de resultados en aplicaciones integradas en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="22f9c-140">Contains types that let you implement output caching in applications that are built into the .NET Framework.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22f9c-141">Observaciones</span><span class="sxs-lookup"><span data-stu-id="22f9c-141">Remarks</span></span>  
 <span data-ttu-id="22f9c-142">La sección de configuración de memoria caché `add` `remove`del `clear` archivo Web.config puede contener , y atributos de la `namedCaches` colección.</span><span class="sxs-lookup"><span data-stu-id="22f9c-142">The memory cache configuration section of the Web.config file can contain `add`, `remove`, and `clear` attributes for the `namedCaches` collection.</span></span> <span data-ttu-id="22f9c-143">Cada `namedCaches` entrada se identifica `name` de forma única por el atributo.</span><span class="sxs-lookup"><span data-stu-id="22f9c-143">Each `namedCaches` entry is uniquely identified by the `name` attribute.</span></span>  
  
 <span data-ttu-id="22f9c-144">Puede recuperar instancias de entradas de memoria caché haciendo referencia a la información de los archivos de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="22f9c-144">You can retrieve instances of memory cache entries by referencing the information in the application configuration files.</span></span> <span data-ttu-id="22f9c-145">De forma predeterminada, solo la instancia de caché predeterminada tiene una entrada en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="22f9c-145">By default, only the default cache instance has an entry in the configuration file.</span></span> <span data-ttu-id="22f9c-146">La instancia de caché predeterminada es <xref:System.Runtime.Caching.MemoryCache.Default%2A> la instancia que se devuelve desde la propiedad.</span><span class="sxs-lookup"><span data-stu-id="22f9c-146">The default cache instance is the instance that is returned from the <xref:System.Runtime.Caching.MemoryCache.Default%2A> property.</span></span>  
  
 <span data-ttu-id="22f9c-147">Si establece el atributo name en "default", el elemento utiliza la instancia de memoria caché predeterminada.</span><span class="sxs-lookup"><span data-stu-id="22f9c-147">If you set the name attribute to "default", the element uses the default memory cache instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22f9c-148">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="22f9c-148">Example</span></span>  
 <span data-ttu-id="22f9c-149">En el ejemplo siguiente se muestra cómo establecer el nombre de `name` la memoria caché en el nombre de entrada de caché predeterminado estableciendo el atributo en "default".</span><span class="sxs-lookup"><span data-stu-id="22f9c-149">The following example shows how to set the name of the cache to the default cache entry name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="22f9c-150">Los atributos `cacheMemoryLimitMegabytes` y `physicalMemoryPercentage` se establecen en cero.</span><span class="sxs-lookup"><span data-stu-id="22f9c-150">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="22f9c-151">Establecer estos atributos en cero significa que se <xref:System.Runtime.Caching.MemoryCache> utilizan las heurísticas de autodimensionamiento de la clase.</span><span class="sxs-lookup"><span data-stu-id="22f9c-151">Setting these attributes to zero means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used.</span></span> <span data-ttu-id="22f9c-152">La implementación de la memoria caché compara la carga de memoria actual con los límites de memoria absolutos y basados en porcentajes cada dos minutos.</span><span class="sxs-lookup"><span data-stu-id="22f9c-152">The cache implementation compares the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="default"
               cacheMemoryLimitMegabytes="0"
               physicalMemoryLimitPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="22f9c-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="22f9c-153">See also</span></span>

- [<span data-ttu-id="22f9c-154">\<MemoryCache> Element (Configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="22f9c-154">\<memoryCache> Element (Cache Settings)</span></span>](memorycache-element-cache-settings.md)
