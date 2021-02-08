---
description: 'Más información sobre: <namedCaches> elemento (configuración de caché)'
title: Elemento <namedCaches> (configuración de caché)
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
ms.openlocfilehash: 543650513270c0cee24d965b8efe98a75d7b8f9a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782330"
---
# <a name="namedcaches-element-cache-settings"></a><span data-ttu-id="e629b-103">Elemento \<namedCaches> (configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="e629b-103">\<namedCaches> Element (Cache Settings)</span></span>

<span data-ttu-id="e629b-104">Especifica una colección de valores de configuración para las <xref:System.Runtime.Caching.MemoryCache> instancias con nombre.</span><span class="sxs-lookup"><span data-stu-id="e629b-104">Specifies a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span> <span data-ttu-id="e629b-105">La <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> propiedad hace referencia a la colección de valores de configuración de uno o más `namedCaches` elementos del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="e629b-105">The <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> property references the collection of configuration settings from one or more `namedCaches` elements of the configuration file.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namedCaches>**  
  
## <a name="syntax"></a><span data-ttu-id="e629b-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e629b-106">Syntax</span></span>  
  
```xml  
<namedCaches>  
  <add name="default"/>
</namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="e629b-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="e629b-107">Type</span></span>  

 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e629b-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e629b-108">Attributes and Elements</span></span>  

 <span data-ttu-id="e629b-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e629b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e629b-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="e629b-110">Attributes</span></span>  
  
|<span data-ttu-id="e629b-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="e629b-111">Attribute</span></span>|<span data-ttu-id="e629b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="e629b-112">Description</span></span>|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|<span data-ttu-id="e629b-113">Valor entero que especifica el tamaño máximo permitido, en megabytes, que puede alcanzar una instancia de un <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="e629b-113">An integer value that specifies the maximum allowable size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="e629b-114">El valor predeterminado es 0, lo que significa que se utiliza de forma predeterminada la heurística de ajuste automático de tamaño de la <xref:System.Runtime.Caching.MemoryCache> clase.</span><span class="sxs-lookup"><span data-stu-id="e629b-114">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`name`|<span data-ttu-id="e629b-115">Nombre de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="e629b-115">The name of the cache.</span></span>|  
|`physicalMemoryLimitPercentage`|<span data-ttu-id="e629b-116">Un valor entero comprendido entre 0 y 100 que especifica el porcentaje máximo de memoria del equipo instalado físicamente que la memoria caché puede consumir.</span><span class="sxs-lookup"><span data-stu-id="e629b-116">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="e629b-117">El valor predeterminado es 0, lo que significa que se utiliza de forma predeterminada la heurística de ajuste automático de tamaño de la <xref:System.Runtime.Caching.MemoryCache> clase.</span><span class="sxs-lookup"><span data-stu-id="e629b-117">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`pollingInterval`|<span data-ttu-id="e629b-118">Valor que indica el intervalo de tiempo después del cual la implementación de caché compara la carga de memoria actual con los límites de memoria absoluto y de porcentaje que están establecidos para la instancia de caché.</span><span class="sxs-lookup"><span data-stu-id="e629b-118">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="e629b-119">Este valor se especifica en formato "HH: MM: SS".</span><span class="sxs-lookup"><span data-stu-id="e629b-119">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e629b-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e629b-120">Child Elements</span></span>  
  
|<span data-ttu-id="e629b-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="e629b-121">Element</span></span>|<span data-ttu-id="e629b-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="e629b-122">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-element-for-namedcaches.md)|<span data-ttu-id="e629b-123">Agrega una caché con nombre a la colección `namedCaches` de una caché en memoria.</span><span class="sxs-lookup"><span data-stu-id="e629b-123">Adds a named cache to the `namedCaches` collection for a memory cache.</span></span>|  
|[\<clear>](clear-element-for-namedcaches.md)|<span data-ttu-id="e629b-124">Borra la colección `namedCaches` de una caché en memoria.</span><span class="sxs-lookup"><span data-stu-id="e629b-124">Clears the `namedCaches` collection for a memory cache.</span></span>|  
|[\<remove>](remove-element-for-namedcaches.md)|<span data-ttu-id="e629b-125">Quita una entrada de caché con nombre de la colección `namedCaches` de una caché en memoria.</span><span class="sxs-lookup"><span data-stu-id="e629b-125">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e629b-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e629b-126">Parent Elements</span></span>  
  
|<span data-ttu-id="e629b-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="e629b-127">Element</span></span>|<span data-ttu-id="e629b-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="e629b-128">Description</span></span>|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|<span data-ttu-id="e629b-129">Especifica el elemento raíz de cada archivo de configuración usado por las aplicaciones Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e629b-129">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[\<memoryCache>](memorycache-element-cache-settings.md)|<span data-ttu-id="e629b-130">Define un elemento que se usa para configurar una memoria caché basada en la clase <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="e629b-130">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
|[\<system.runtime.caching>](system-runtime-caching-element-cache-settings.md)|<span data-ttu-id="e629b-131">Contiene tipos que permiten implementar el almacenamiento en caché de resultados en las aplicaciones integradas en el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e629b-131">Contains types that let you implement output caching in applications that are built into the .NET Framework.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e629b-132">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e629b-132">Remarks</span></span>  

 <span data-ttu-id="e629b-133">La sección de configuración de la memoria caché del archivo Web.config puede contener los `add` `remove` atributos, y `clear` para la `namedCaches` colección.</span><span class="sxs-lookup"><span data-stu-id="e629b-133">The memory cache configuration section of the Web.config file can contain `add`, `remove`, and `clear` attributes for the `namedCaches` collection.</span></span> <span data-ttu-id="e629b-134">Cada `namedCaches` entrada se identifica de forma única mediante el `name` atributo.</span><span class="sxs-lookup"><span data-stu-id="e629b-134">Each `namedCaches` entry is uniquely identified by the `name` attribute.</span></span>  
  
 <span data-ttu-id="e629b-135">Puede recuperar instancias de entradas de la memoria caché haciendo referencia a la información de los archivos de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e629b-135">You can retrieve instances of memory cache entries by referencing the information in the application configuration files.</span></span> <span data-ttu-id="e629b-136">De forma predeterminada, solo la instancia de caché predeterminada tiene una entrada en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="e629b-136">By default, only the default cache instance has an entry in the configuration file.</span></span> <span data-ttu-id="e629b-137">La instancia de caché predeterminada es la instancia de que se devuelve desde la <xref:System.Runtime.Caching.MemoryCache.Default%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="e629b-137">The default cache instance is the instance that is returned from the <xref:System.Runtime.Caching.MemoryCache.Default%2A> property.</span></span>  
  
 <span data-ttu-id="e629b-138">Si establece el atributo name en "default", el elemento utiliza la instancia de la memoria caché predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e629b-138">If you set the name attribute to "default", the element uses the default memory cache instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e629b-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e629b-139">Example</span></span>  

 <span data-ttu-id="e629b-140">En el ejemplo siguiente se muestra cómo establecer el nombre de la memoria caché en el nombre de la entrada de caché predeterminado estableciendo el `name` atributo en "default".</span><span class="sxs-lookup"><span data-stu-id="e629b-140">The following example shows how to set the name of the cache to the default cache entry name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="e629b-141">Los atributos `cacheMemoryLimitMegabytes` y `physicalMemoryPercentage` se establecen en cero.</span><span class="sxs-lookup"><span data-stu-id="e629b-141">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="e629b-142">Establecer estos atributos en cero significa que se utiliza la heurística de ajuste automático de tamaño de la <xref:System.Runtime.Caching.MemoryCache> clase.</span><span class="sxs-lookup"><span data-stu-id="e629b-142">Setting these attributes to zero means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used.</span></span> <span data-ttu-id="e629b-143">La implementación de caché compara la carga de memoria actual con los límites de memoria absoluta y basada en porcentajes cada dos minutos.</span><span class="sxs-lookup"><span data-stu-id="e629b-143">The cache implementation compares the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e629b-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="e629b-144">See also</span></span>

- [<span data-ttu-id="e629b-145">\<memoryCache> (Elemento, configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="e629b-145">\<memoryCache> Element (Cache Settings)</span></span>](memorycache-element-cache-settings.md)
