---
title: '&lt;agregar&gt; (elemento) para &lt;namedCaches&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 695ee744bdf2226f0647c4cdf142a2dca4e97a4a
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47085819"
---
# <a name="ltaddgt-element-for-ltnamedcachesgt"></a><span data-ttu-id="b1af7-102">&lt;agregar&gt; (elemento) para &lt;namedCaches&gt;</span><span class="sxs-lookup"><span data-stu-id="b1af7-102">&lt;add&gt; Element for &lt;namedCaches&gt;</span></span>
<span data-ttu-id="b1af7-103">Agrega un `namedCache` entrada para el `namedCaches` colección de una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="b1af7-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="b1af7-104">\<System.Runtime.Caching ></span><span class="sxs-lookup"><span data-stu-id="b1af7-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="b1af7-105">\<memoryCache ></span><span class="sxs-lookup"><span data-stu-id="b1af7-105">\<memoryCache></span></span>  
<span data-ttu-id="b1af7-106">\<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="b1af7-106">\<namedCaches></span></span>  
<span data-ttu-id="b1af7-107">\<add></span><span class="sxs-lookup"><span data-stu-id="b1af7-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1af7-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b1af7-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="b1af7-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="b1af7-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b1af7-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b1af7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b1af7-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b1af7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b1af7-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="b1af7-112">Attributes</span></span>  
  
|<span data-ttu-id="b1af7-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="b1af7-113">Attribute</span></span>|<span data-ttu-id="b1af7-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="b1af7-114">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="b1af7-115">Un valor entero que especifica el tamaño máximo permitido (en megabytes) que una instancia de un <xref:System.Runtime.Caching.MemoryCache> pueden crecer hasta.</span><span class="sxs-lookup"><span data-stu-id="b1af7-115">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="b1af7-116">El valor predeterminado es 0, lo que significa que el <xref:System.Runtime.Caching.MemoryCache> heurística de ajuste automático de tamaño de la clase se utiliza de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b1af7-116">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="b1af7-117">Nombre de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="b1af7-117">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="b1af7-118">Un valor de número entero entre 0 y 100 que especifica el porcentaje máximo de memoria instalada físicamente del equipo que puede consumir la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="b1af7-118">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="b1af7-119">El valor predeterminado es 0, lo que significa que el <xref:System.Runtime.Caching.MemoryCache> heurística de ajuste automático de tamaño de la clase se utiliza de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b1af7-119">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="b1af7-120">Valor que indica el intervalo de tiempo después del cual la implementación de caché compara la carga de memoria actual con los límites de memoria absoluto y de porcentaje que están establecidos para la instancia de caché.</span><span class="sxs-lookup"><span data-stu-id="b1af7-120">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="b1af7-121">Este valor se escribe en formato "Hh".</span><span class="sxs-lookup"><span data-stu-id="b1af7-121">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b1af7-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b1af7-122">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="b1af7-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b1af7-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b1af7-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="b1af7-124">Element</span></span>|<span data-ttu-id="b1af7-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="b1af7-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b1af7-126">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="b1af7-126">\<namedCaches></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|<span data-ttu-id="b1af7-127">Contiene una colección de valores de configuración para la instancia con nombre <xref:System.Runtime.Caching.MemoryCache> instancias.</span><span class="sxs-lookup"><span data-stu-id="b1af7-127">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1af7-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b1af7-128">Remarks</span></span>  
 <span data-ttu-id="b1af7-129">El `add` elemento agrega una entrada a la `namedCaches` colección de una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="b1af7-129">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="b1af7-130">Puede usar el [borrar](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md) elemento antes de usar el `add` elemento que esté seguro de que no hay ninguna otra denominada caché en la colección.</span><span class="sxs-lookup"><span data-stu-id="b1af7-130">You can use the [clear](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="b1af7-131">Este elemento se puede usar en el archivo machine.config y en el archivo Web.config.</span><span class="sxs-lookup"><span data-stu-id="b1af7-131">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1af7-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b1af7-132">Example</span></span>  
 <span data-ttu-id="b1af7-133">El ejemplo siguiente muestra cómo definir la configuración para el valor predeterminado `namedCache` entrada para el `namedCaches` colección de una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="b1af7-133">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b1af7-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1af7-134">See Also</span></span>  
 [<span data-ttu-id="b1af7-135">\<namedCaches > elemento (configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="b1af7-135">\<namedCaches> Element (Cache Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
