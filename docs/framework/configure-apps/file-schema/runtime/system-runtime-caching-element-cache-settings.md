---
title: Elemento <system.runtime.caching> (configuración de caché)
ms.date: 03/30/2017
helpviewer_keywords:
- <system.runtime.caching> element
- caching [.NET Framework], configuration
- system.runtime.caching element
ms.assetid: 9b44daee-874a-4bd1-954e-83bf53565590
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e36e2ed96a0748a69f2bd9ee32432901f0bf0898
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252287"
---
# <a name="systemruntimecaching-element-cache-settings"></a><span data-ttu-id="bf68e-102">\<Elemento > de System. Runtime. Caching (configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="bf68e-102">\<system.runtime.caching> Element (Cache Settings)</span></span>

<span data-ttu-id="bf68e-103">Proporciona la configuración para la implementación predeterminada en memoria de la clase <xref:System.Runtime.Caching.ObjectCache> mediante la entrada `memoryCache` en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="bf68e-103">Provides configuration for the default in-memory <xref:System.Runtime.Caching.ObjectCache> implementation through the `memoryCache` entry in the configuration file.</span></span>  
  
<span data-ttu-id="bf68e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bf68e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bf68e-105">&nbsp;&nbsp; **\<System. Runtime. Caching >**</span><span class="sxs-lookup"><span data-stu-id="bf68e-105">&nbsp;&nbsp;**\<system.runtime.caching>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf68e-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf68e-106">Syntax</span></span>  
  
```xml  
<system.runtime.caching >  
   <!-- child elements -->  
</system.runtime.caching >  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bf68e-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bf68e-107">Attributes and Elements</span></span>

<span data-ttu-id="bf68e-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bf68e-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bf68e-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="bf68e-109">Attributes</span></span>

`None`  

### <a name="child-elements"></a><span data-ttu-id="bf68e-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bf68e-110">Child Elements</span></span>

|<span data-ttu-id="bf68e-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="bf68e-111">Element</span></span>|<span data-ttu-id="bf68e-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="bf68e-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bf68e-113">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="bf68e-113">\<memoryCache></span></span>](memorycache-element-cache-settings.md)|<span data-ttu-id="bf68e-114">Define un elemento que se usa para configurar una memoria caché basada en la clase <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="bf68e-114">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bf68e-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bf68e-115">Parent Elements</span></span>  
  
|<span data-ttu-id="bf68e-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="bf68e-116">Element</span></span>|<span data-ttu-id="bf68e-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="bf68e-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bf68e-118">\<configuration></span><span class="sxs-lookup"><span data-stu-id="bf68e-118">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="bf68e-119">Especifica el elemento raíz de cada archivo de configuración usado por las aplicaciones Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bf68e-119">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf68e-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bf68e-120">Remarks</span></span>

<span data-ttu-id="bf68e-121">Las clases de este espacio de nombres proporcionan una manera de usar las funciones de almacenamiento en caché, como las de ASP.NET, pero sin una dependencia en el ensamblado `System.Web` .</span><span class="sxs-lookup"><span data-stu-id="bf68e-121">The classes in this namespace provide a way to use caching facilities like those in ASP.NET, but without a dependency on the `System.Web` assembly.</span></span> <span data-ttu-id="bf68e-122">Para obtener más información, consulta [Caching in .NET Framework Applications](../../../performance/caching-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="bf68e-122">For more information, see [Caching in .NET Framework Applications](../../../performance/caching-in-net-framework-applications.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bf68e-123">La funcionalidad de almacenamiento en caché de resultados <xref:System.Runtime.Caching> y los tipos del espacio de nombres son nuevos en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="bf68e-123">The output caching functionality and types in the <xref:System.Runtime.Caching> namespace are new in .NET Framework 4.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf68e-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bf68e-124">Example</span></span>

<span data-ttu-id="bf68e-125">En el ejemplo siguiente se muestra cómo configurar una memoria caché basada en la clase <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="bf68e-125">The following example shows how to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span> <span data-ttu-id="bf68e-126">En el ejemplo se muestra cómo configurar una instancia de la entrada `namedCaches` de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="bf68e-126">The example shows how to configure an instance of the `namedCaches` entry for memory cache.</span></span> <span data-ttu-id="bf68e-127">El nombre de la memoria caché se establece en el nombre de la entrada de caché `name` predeterminado estableciendo el atributo en "default".</span><span class="sxs-lookup"><span data-stu-id="bf68e-127">The name of the cache is set to the default cache entry name by setting the `name` attribute to "Default".</span></span>  
  
<span data-ttu-id="bf68e-128">Los atributos `cacheMemoryLimitMegabytes` y `physicalMemoryPercentage` se establecen en cero.</span><span class="sxs-lookup"><span data-stu-id="bf68e-128">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="bf68e-129">El hecho de establecer estos atributos en cero implica que la heurística de ajuste automático de tamaño de <xref:System.Runtime.Caching.MemoryCache> se usa de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="bf68e-129">Setting these attributes to zero means that the <xref:System.Runtime.Caching.MemoryCache> autosizing heuristics are used by default.</span></span> <span data-ttu-id="bf68e-130">La implementación de la memoria caché debe comparar cada dos minutos la carga de memoria actual con los límites de memoria absoluto y de porcentaje.</span><span class="sxs-lookup"><span data-stu-id="bf68e-130">The cache implementation should compare the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bf68e-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf68e-131">See also</span></span>

- [<span data-ttu-id="bf68e-132">\<memoryCache > elemento (configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="bf68e-132">\<memoryCache> Element (Cache Settings)</span></span>](memorycache-element-cache-settings.md)
