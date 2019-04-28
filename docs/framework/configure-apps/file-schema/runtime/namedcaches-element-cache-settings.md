---
title: Elemento <namedCaches> (configuración de caché)
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
ms.openlocfilehash: 36920a5e585c0c7581fbc4f84043d68550fbdac1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704874"
---
# <a name="namedcaches-element-cache-settings"></a><span data-ttu-id="b9124-102">\<namedCaches > elemento (configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="b9124-102">\<namedCaches> Element (Cache Settings)</span></span>
<span data-ttu-id="b9124-103">Especifica una colección de valores de configuración para la instancia con nombre <xref:System.Runtime.Caching.MemoryCache> instancias.</span><span class="sxs-lookup"><span data-stu-id="b9124-103">Specifies a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span> <span data-ttu-id="b9124-104">El <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> propiedad hace referencia a la colección de valores de configuración de uno o varios `namedCaches` elementos del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="b9124-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> property references the collection of configuration settings from one or more `namedCaches` elements of the configuration file.</span></span>  
  
 <span data-ttu-id="b9124-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b9124-105">\<configuration></span></span>  
<span data-ttu-id="b9124-106">\< system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="b9124-106">\< system.runtime.caching></span></span>  
<span data-ttu-id="b9124-107">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="b9124-107">\<memoryCache></span></span>  
<span data-ttu-id="b9124-108">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="b9124-108">\<namedCaches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9124-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b9124-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
  <add name="default"/>   
</namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="b9124-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="b9124-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b9124-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b9124-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b9124-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b9124-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b9124-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="b9124-113">Attributes</span></span>  
  
|<span data-ttu-id="b9124-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="b9124-114">Attribute</span></span>|<span data-ttu-id="b9124-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="b9124-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|<span data-ttu-id="b9124-116">Valor entero que especifica el tamaño máximo permitido, en megabytes, que una instancia de un <xref:System.Runtime.Caching.MemoryCache> pueden crecer hasta.</span><span class="sxs-lookup"><span data-stu-id="b9124-116">An integer value that specifies the maximum allowable size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="b9124-117">El valor predeterminado es 0, lo que significa que la heurística de ajuste automático de tamaño de la <xref:System.Runtime.Caching.MemoryCache> la clase se utilizan de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b9124-117">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`name`|<span data-ttu-id="b9124-118">Nombre de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="b9124-118">The name of the cache.</span></span>|  
|`physicalMemoryLimitPercentage`|<span data-ttu-id="b9124-119">Un valor de número entero entre 0 y 100 que especifica el porcentaje máximo de memoria instalada físicamente del equipo que puede consumir la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="b9124-119">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="b9124-120">El valor predeterminado es 0, lo que significa que la heurística de ajuste automático de tamaño de la <xref:System.Runtime.Caching.MemoryCache> la clase se utilizan de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b9124-120">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`pollingInterval`|<span data-ttu-id="b9124-121">Valor que indica el intervalo de tiempo después del cual la implementación de caché compara la carga de memoria actual con los límites de memoria absoluto y de porcentaje que están establecidos para la instancia de caché.</span><span class="sxs-lookup"><span data-stu-id="b9124-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="b9124-122">Este valor se escribe en formato "Hh".</span><span class="sxs-lookup"><span data-stu-id="b9124-122">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b9124-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b9124-123">Child Elements</span></span>  
  
|<span data-ttu-id="b9124-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="b9124-124">Element</span></span>|<span data-ttu-id="b9124-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="b9124-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b9124-126">\<add></span><span class="sxs-lookup"><span data-stu-id="b9124-126">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/add-element-for-namedcaches.md)|<span data-ttu-id="b9124-127">Agrega una caché con nombre a la colección `namedCaches` de una caché en memoria.</span><span class="sxs-lookup"><span data-stu-id="b9124-127">Adds a named cache to the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="b9124-128">\<clear></span><span class="sxs-lookup"><span data-stu-id="b9124-128">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md)|<span data-ttu-id="b9124-129">Borra la colección `namedCaches` de una caché en memoria.</span><span class="sxs-lookup"><span data-stu-id="b9124-129">Clears the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="b9124-130">\<remove></span><span class="sxs-lookup"><span data-stu-id="b9124-130">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/remove-element-for-namedcaches.md)|<span data-ttu-id="b9124-131">Quita una entrada de caché con nombre de la colección `namedCaches` de una caché en memoria.</span><span class="sxs-lookup"><span data-stu-id="b9124-131">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b9124-132">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b9124-132">Parent Elements</span></span>  
  
|<span data-ttu-id="b9124-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="b9124-133">Element</span></span>|<span data-ttu-id="b9124-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="b9124-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b9124-135">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="b9124-135">\<memoryCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)|<span data-ttu-id="b9124-136">Define un elemento que se usa para configurar una memoria caché basada en la clase <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="b9124-136">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9124-137">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b9124-137">Remarks</span></span>  
 <span data-ttu-id="b9124-138">La sección de configuración de memoria caché del archivo Web.config puede contener `add`, `remove`, y `clear` atributos para el `namedCaches` colección.</span><span class="sxs-lookup"><span data-stu-id="b9124-138">The memory cache configuration section of the Web.config file can contain `add`, `remove`, and `clear` attributes for the `namedCaches` collection.</span></span> <span data-ttu-id="b9124-139">Cada `namedCaches` entrada se identifica mediante el `name` atributo.</span><span class="sxs-lookup"><span data-stu-id="b9124-139">Each `namedCaches` entry is uniquely identified by the `name` attribute.</span></span>  
  
 <span data-ttu-id="b9124-140">Puede recuperar las instancias de entradas de la memoria caché haciendo referencia a la información de los archivos de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b9124-140">You can retrieve instances of memory cache entries by referencing the information in the application configuration files.</span></span> <span data-ttu-id="b9124-141">De forma predeterminada, solo la instancia de caché predeterminada tiene una entrada en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="b9124-141">By default, only the default cache instance has an entry in the configuration file.</span></span> <span data-ttu-id="b9124-142">La instancia de caché predeterminada es la instancia que se devuelve desde el <xref:System.Runtime.Caching.MemoryCache.Default%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="b9124-142">The default cache instance is the instance that is returned from the <xref:System.Runtime.Caching.MemoryCache.Default%2A> property.</span></span>  
  
 <span data-ttu-id="b9124-143">Si establece el atributo name en "default", el elemento utiliza la instancia predeterminada de la memoria caché de memoria.</span><span class="sxs-lookup"><span data-stu-id="b9124-143">If you set the name attribute to "default", the element uses the default memory cache instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9124-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b9124-144">Example</span></span>  
 <span data-ttu-id="b9124-145">El ejemplo siguiente muestra cómo establecer el nombre de la memoria caché en el nombre de entrada de caché predeterminado estableciendo la `name` atributo en "default".</span><span class="sxs-lookup"><span data-stu-id="b9124-145">The following example shows how to set the name of the cache to the default cache entry name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="b9124-146">Los atributos `cacheMemoryLimitMegabytes` y `physicalMemoryPercentage` se establecen en cero.</span><span class="sxs-lookup"><span data-stu-id="b9124-146">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="b9124-147">Establecer estos atributos en cero significa que la heurística de ajuste automático de tamaño de la <xref:System.Runtime.Caching.MemoryCache> la clase se utilizan.</span><span class="sxs-lookup"><span data-stu-id="b9124-147">Setting these attributes to zero means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used.</span></span> <span data-ttu-id="b9124-148">La implementación de caché compara la carga de memoria actual con los límites de memoria absoluto y de porcentaje de cada dos minutos.</span><span class="sxs-lookup"><span data-stu-id="b9124-148">The cache implementation compares the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b9124-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9124-149">See also</span></span>

- [<span data-ttu-id="b9124-150">\<memoryCache > elemento (configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="b9124-150">\<memoryCache> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)
