---
description: 'Más información sobre: <add> elemento para <namedCaches>'
title: Elemento <add> para <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: 1485b80fa84268f68759bfb50744133744142d72
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802429"
---
# <a name="add-element-for-namedcaches"></a><span data-ttu-id="237e6-103">Elemento \<add> para \<namedCaches></span><span class="sxs-lookup"><span data-stu-id="237e6-103">\<add> Element for \<namedCaches></span></span>

<span data-ttu-id="237e6-104">Agrega una `namedCache` entrada a la `namedCaches` colección de una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="237e6-104">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="237e6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="237e6-105">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="Default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="237e6-106">Tipo</span><span class="sxs-lookup"><span data-stu-id="237e6-106">Type</span></span>  

 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="237e6-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="237e6-107">Attributes and Elements</span></span>  

 <span data-ttu-id="237e6-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="237e6-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="237e6-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="237e6-109">Attributes</span></span>  
  
|<span data-ttu-id="237e6-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="237e6-110">Attribute</span></span>|<span data-ttu-id="237e6-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="237e6-111">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="237e6-112">Valor entero que especifica el tamaño máximo permitido (en megabytes) que puede alcanzar una instancia de un <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="237e6-112">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="237e6-113">El valor predeterminado es 0, lo que significa que <xref:System.Runtime.Caching.MemoryCache> se utiliza de forma predeterminada la heurística de ajuste automático de tamaño de la clase.</span><span class="sxs-lookup"><span data-stu-id="237e6-113">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="237e6-114">Nombre de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="237e6-114">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="237e6-115">Un valor entero comprendido entre 0 y 100 que especifica el porcentaje máximo de memoria del equipo instalado físicamente que la memoria caché puede consumir.</span><span class="sxs-lookup"><span data-stu-id="237e6-115">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="237e6-116">El valor predeterminado es 0, lo que significa que <xref:System.Runtime.Caching.MemoryCache> se utiliza de forma predeterminada la heurística de ajuste automático de tamaño de la clase.</span><span class="sxs-lookup"><span data-stu-id="237e6-116">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="237e6-117">Valor que indica el intervalo de tiempo después del cual la implementación de caché compara la carga de memoria actual con los límites de memoria absoluto y de porcentaje que están establecidos para la instancia de caché.</span><span class="sxs-lookup"><span data-stu-id="237e6-117">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="237e6-118">Este valor se especifica en formato "HH: MM: SS".</span><span class="sxs-lookup"><span data-stu-id="237e6-118">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="237e6-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="237e6-119">Child Elements</span></span>  

 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="237e6-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="237e6-120">Parent Elements</span></span>  
  
|<span data-ttu-id="237e6-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="237e6-121">Element</span></span>|<span data-ttu-id="237e6-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="237e6-122">Description</span></span>|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|<span data-ttu-id="237e6-123">Contiene una colección de valores de configuración para las <xref:System.Runtime.Caching.MemoryCache> instancias con nombre.</span><span class="sxs-lookup"><span data-stu-id="237e6-123">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="237e6-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="237e6-124">Remarks</span></span>  

 <span data-ttu-id="237e6-125">El `add` elemento agrega una entrada a la `namedCaches` colección para una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="237e6-125">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="237e6-126">Puede usar el elemento [Clear](clear-element-for-namedcaches.md) antes de usar el `add` elemento para asegurarse de que no hay otras memorias caché con nombre en la colección.</span><span class="sxs-lookup"><span data-stu-id="237e6-126">You can use the [clear](clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="237e6-127">Este elemento se puede utilizar en el archivo de machine.config y en el archivo de Web.config.</span><span class="sxs-lookup"><span data-stu-id="237e6-127">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="237e6-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="237e6-128">Example</span></span>  

 <span data-ttu-id="237e6-129">En el ejemplo siguiente se muestra cómo definir la configuración de la `namedCache` entrada predeterminada en la `namedCaches` colección para una memoria caché.</span><span class="sxs-lookup"><span data-stu-id="237e6-129">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="237e6-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="237e6-130">See also</span></span>

- [<span data-ttu-id="237e6-131">\<namedCaches> (Elemento, configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="237e6-131">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
