---
title: Elemento <add> para <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: fd6668a551663470a97b07ff131710dbe92a91f5
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659024"
---
# <a name="add-element-for-namedcaches"></a><span data-ttu-id="e14e0-102">\<Agregue > elemento para \<namedCaches ></span><span class="sxs-lookup"><span data-stu-id="e14e0-102">\<add> Element for \<namedCaches></span></span>
<span data-ttu-id="e14e0-103">Agrega una `namedCache` entrada a la `namedCaches` colección de una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="e14e0-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="e14e0-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="e14e0-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="e14e0-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="e14e0-105">\<memoryCache></span></span>  
<span data-ttu-id="e14e0-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="e14e0-106">\<namedCaches></span></span>  
<span data-ttu-id="e14e0-107">\<add></span><span class="sxs-lookup"><span data-stu-id="e14e0-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e14e0-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e14e0-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="Default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="e14e0-109">Type</span><span class="sxs-lookup"><span data-stu-id="e14e0-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e14e0-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e14e0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e14e0-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e14e0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e14e0-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="e14e0-112">Attributes</span></span>  
  
|<span data-ttu-id="e14e0-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="e14e0-113">Attribute</span></span>|<span data-ttu-id="e14e0-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e14e0-114">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="e14e0-115">Valor entero que especifica el tamaño máximo permitido (en megabytes) que puede alcanzar una instancia de un <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="e14e0-115">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="e14e0-116">El valor predeterminado es 0, lo que significa que <xref:System.Runtime.Caching.MemoryCache> se utiliza de forma predeterminada la heurística de ajuste automático de tamaño de la clase.</span><span class="sxs-lookup"><span data-stu-id="e14e0-116">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="e14e0-117">Nombre de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="e14e0-117">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="e14e0-118">Un valor entero comprendido entre 0 y 100 que especifica el porcentaje máximo de memoria del equipo instalado físicamente que la memoria caché puede consumir.</span><span class="sxs-lookup"><span data-stu-id="e14e0-118">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="e14e0-119">El valor predeterminado es 0, lo que significa que <xref:System.Runtime.Caching.MemoryCache> se utiliza de forma predeterminada la heurística de ajuste automático de tamaño de la clase.</span><span class="sxs-lookup"><span data-stu-id="e14e0-119">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="e14e0-120">Valor que indica el intervalo de tiempo después del cual la implementación de caché compara la carga de memoria actual con los límites de memoria absoluto y de porcentaje que están establecidos para la instancia de caché.</span><span class="sxs-lookup"><span data-stu-id="e14e0-120">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="e14e0-121">Este valor se especifica en formato "HH: MM: SS".</span><span class="sxs-lookup"><span data-stu-id="e14e0-121">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e14e0-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e14e0-122">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="e14e0-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e14e0-123">Parent Elements</span></span>  
  
|<span data-ttu-id="e14e0-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="e14e0-124">Element</span></span>|<span data-ttu-id="e14e0-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e14e0-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e14e0-126">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="e14e0-126">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="e14e0-127">Contiene una colección de valores de configuración para las <xref:System.Runtime.Caching.MemoryCache> instancias con nombre.</span><span class="sxs-lookup"><span data-stu-id="e14e0-127">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e14e0-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e14e0-128">Remarks</span></span>  
 <span data-ttu-id="e14e0-129">El `add` elemento agrega una entrada a la `namedCaches` colección para una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="e14e0-129">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="e14e0-130">Puede usar el elemento [Clear](clear-element-for-namedcaches.md) antes de usar el `add` elemento para asegurarse de que no hay otras memorias caché con nombre en la colección.</span><span class="sxs-lookup"><span data-stu-id="e14e0-130">You can use the [clear](clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="e14e0-131">Este elemento se puede utilizar en el archivo Machine. config y en el archivo Web. config.</span><span class="sxs-lookup"><span data-stu-id="e14e0-131">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e14e0-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e14e0-132">Example</span></span>  
 <span data-ttu-id="e14e0-133">En el ejemplo siguiente se muestra cómo definir la configuración de `namedCache` la entrada predeterminada `namedCaches` en la colección para una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="e14e0-133">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e14e0-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="e14e0-134">See also</span></span>

- [<span data-ttu-id="e14e0-135">\<namedCaches (elemento > (configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="e14e0-135">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
