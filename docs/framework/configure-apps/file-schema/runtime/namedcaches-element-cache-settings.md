---
title: Elemento <namedCaches> (configuración de caché)
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
ms.openlocfilehash: 4587234ad91fa3b1abbb376bd7ae517d5abea6c3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252463"
---
# <a name="namedcaches-element-cache-settings"></a><span data-ttu-id="3b73d-102">\<namedCaches (elemento > (configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="3b73d-102">\<namedCaches> Element (Cache Settings)</span></span>
<span data-ttu-id="3b73d-103">Especifica una colección de valores de configuración para las <xref:System.Runtime.Caching.MemoryCache> instancias con nombre.</span><span class="sxs-lookup"><span data-stu-id="3b73d-103">Specifies a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span> <span data-ttu-id="3b73d-104">La <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> propiedad hace referencia a la colección de valores de configuración de `namedCaches` uno o más elementos del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="3b73d-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> property references the collection of configuration settings from one or more `namedCaches` elements of the configuration file.</span></span>  
  
<span data-ttu-id="3b73d-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3b73d-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3b73d-106">&nbsp;&nbsp;[ **\<System. Runtime. Caching >** ](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="3b73d-106">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="3b73d-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<memoryCache >** ](memorycache-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="3b73d-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span></span>\
<span data-ttu-id="3b73d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<namedCaches >**</span><span class="sxs-lookup"><span data-stu-id="3b73d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namedCaches>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b73d-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3b73d-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
  <add name="default"/>   
</namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="3b73d-110">Type</span><span class="sxs-lookup"><span data-stu-id="3b73d-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3b73d-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3b73d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="3b73d-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3b73d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3b73d-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="3b73d-113">Attributes</span></span>  
  
|<span data-ttu-id="3b73d-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="3b73d-114">Attribute</span></span>|<span data-ttu-id="3b73d-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3b73d-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|<span data-ttu-id="3b73d-116">Valor entero que especifica el tamaño máximo permitido, en megabytes, que puede alcanzar una instancia de un <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="3b73d-116">An integer value that specifies the maximum allowable size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="3b73d-117">El valor predeterminado es 0, lo que significa que se utiliza de forma predeterminada la <xref:System.Runtime.Caching.MemoryCache> heurística de ajuste automático de tamaño de la clase.</span><span class="sxs-lookup"><span data-stu-id="3b73d-117">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`name`|<span data-ttu-id="3b73d-118">Nombre de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="3b73d-118">The name of the cache.</span></span>|  
|`physicalMemoryLimitPercentage`|<span data-ttu-id="3b73d-119">Un valor entero comprendido entre 0 y 100 que especifica el porcentaje máximo de memoria del equipo instalado físicamente que la memoria caché puede consumir.</span><span class="sxs-lookup"><span data-stu-id="3b73d-119">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="3b73d-120">El valor predeterminado es 0, lo que significa que se utiliza de forma predeterminada la <xref:System.Runtime.Caching.MemoryCache> heurística de ajuste automático de tamaño de la clase.</span><span class="sxs-lookup"><span data-stu-id="3b73d-120">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`pollingInterval`|<span data-ttu-id="3b73d-121">Valor que indica el intervalo de tiempo después del cual la implementación de caché compara la carga de memoria actual con los límites de memoria absoluto y de porcentaje que están establecidos para la instancia de caché.</span><span class="sxs-lookup"><span data-stu-id="3b73d-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="3b73d-122">Este valor se especifica en formato "HH: MM: SS".</span><span class="sxs-lookup"><span data-stu-id="3b73d-122">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3b73d-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3b73d-123">Child Elements</span></span>  
  
|<span data-ttu-id="3b73d-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="3b73d-124">Element</span></span>|<span data-ttu-id="3b73d-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3b73d-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3b73d-126">\<add></span><span class="sxs-lookup"><span data-stu-id="3b73d-126">\<add></span></span>](add-element-for-namedcaches.md)|<span data-ttu-id="3b73d-127">Agrega una caché con nombre a la colección `namedCaches` de una caché en memoria.</span><span class="sxs-lookup"><span data-stu-id="3b73d-127">Adds a named cache to the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="3b73d-128">\<clear></span><span class="sxs-lookup"><span data-stu-id="3b73d-128">\<clear></span></span>](clear-element-for-namedcaches.md)|<span data-ttu-id="3b73d-129">Borra la colección `namedCaches` de una caché en memoria.</span><span class="sxs-lookup"><span data-stu-id="3b73d-129">Clears the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="3b73d-130">\<remove></span><span class="sxs-lookup"><span data-stu-id="3b73d-130">\<remove></span></span>](remove-element-for-namedcaches.md)|<span data-ttu-id="3b73d-131">Quita una entrada de caché con nombre de la colección `namedCaches` de una caché en memoria.</span><span class="sxs-lookup"><span data-stu-id="3b73d-131">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3b73d-132">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3b73d-132">Parent Elements</span></span>  
  
|<span data-ttu-id="3b73d-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="3b73d-133">Element</span></span>|<span data-ttu-id="3b73d-134">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3b73d-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3b73d-135">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3b73d-135">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="3b73d-136">Especifica el elemento raíz de cada archivo de configuración usado por las aplicaciones Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3b73d-136">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="3b73d-137">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="3b73d-137">\<memoryCache></span></span>](memorycache-element-cache-settings.md)|<span data-ttu-id="3b73d-138">Define un elemento que se usa para configurar una memoria caché basada en la clase <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="3b73d-138">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
|[<span data-ttu-id="3b73d-139">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="3b73d-139">\<system.runtime.caching></span></span>](system-runtime-caching-element-cache-settings.md)|<span data-ttu-id="3b73d-140">Contiene tipos que permiten implementar el almacenamiento en caché de resultados en las aplicaciones integradas en el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3b73d-140">Contains types that let you implement output caching in applications that are built into the .NET Framework.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b73d-141">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3b73d-141">Remarks</span></span>  
 <span data-ttu-id="3b73d-142">La sección de configuración de la memoria caché del archivo Web. config `add`puede `remove`contener los `clear` atributos, y `namedCaches` para la colección.</span><span class="sxs-lookup"><span data-stu-id="3b73d-142">The memory cache configuration section of the Web.config file can contain `add`, `remove`, and `clear` attributes for the `namedCaches` collection.</span></span> <span data-ttu-id="3b73d-143">Cada `namedCaches` entrada se identifica de forma única mediante `name` el atributo.</span><span class="sxs-lookup"><span data-stu-id="3b73d-143">Each `namedCaches` entry is uniquely identified by the `name` attribute.</span></span>  
  
 <span data-ttu-id="3b73d-144">Puede recuperar instancias de entradas de la memoria caché haciendo referencia a la información de los archivos de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3b73d-144">You can retrieve instances of memory cache entries by referencing the information in the application configuration files.</span></span> <span data-ttu-id="3b73d-145">De forma predeterminada, solo la instancia de caché predeterminada tiene una entrada en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="3b73d-145">By default, only the default cache instance has an entry in the configuration file.</span></span> <span data-ttu-id="3b73d-146">La instancia de caché predeterminada es la instancia de que se devuelve <xref:System.Runtime.Caching.MemoryCache.Default%2A> desde la propiedad.</span><span class="sxs-lookup"><span data-stu-id="3b73d-146">The default cache instance is the instance that is returned from the <xref:System.Runtime.Caching.MemoryCache.Default%2A> property.</span></span>  
  
 <span data-ttu-id="3b73d-147">Si establece el atributo name en "default", el elemento utiliza la instancia de la memoria caché predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3b73d-147">If you set the name attribute to "default", the element uses the default memory cache instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b73d-148">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3b73d-148">Example</span></span>  
 <span data-ttu-id="3b73d-149">En el ejemplo siguiente se muestra cómo establecer el nombre de la memoria caché en el nombre de la entrada de `name` caché predeterminado estableciendo el atributo en "default".</span><span class="sxs-lookup"><span data-stu-id="3b73d-149">The following example shows how to set the name of the cache to the default cache entry name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="3b73d-150">Los atributos `cacheMemoryLimitMegabytes` y `physicalMemoryPercentage` se establecen en cero.</span><span class="sxs-lookup"><span data-stu-id="3b73d-150">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="3b73d-151">Establecer estos atributos en cero significa que se utiliza la heurística de ajuste automático <xref:System.Runtime.Caching.MemoryCache> de tamaño de la clase.</span><span class="sxs-lookup"><span data-stu-id="3b73d-151">Setting these attributes to zero means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used.</span></span> <span data-ttu-id="3b73d-152">La implementación de caché compara la carga de memoria actual con los límites de memoria absoluta y basada en porcentajes cada dos minutos.</span><span class="sxs-lookup"><span data-stu-id="3b73d-152">The cache implementation compares the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3b73d-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b73d-153">See also</span></span>

- [<span data-ttu-id="3b73d-154">\<memoryCache > elemento (configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="3b73d-154">\<memoryCache> Element (Cache Settings)</span></span>](memorycache-element-cache-settings.md)
