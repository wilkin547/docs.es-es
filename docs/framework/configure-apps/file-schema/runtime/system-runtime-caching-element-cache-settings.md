---
description: 'Más información acerca de: <el elemento System. Runtime. Caching> (configuración de caché)'
title: Elemento <system.runtime.caching> (configuración de caché)
ms.date: 03/30/2017
helpviewer_keywords:
- <system.runtime.caching> element
- caching [.NET Framework], configuration
- system.runtime.caching element
ms.assetid: 9b44daee-874a-4bd1-954e-83bf53565590
ms.openlocfilehash: 602d863caedef5c1334948b25b0caa2b0e35f685
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652736"
---
# <a name="systemruntimecaching-element-cache-settings"></a><span data-ttu-id="3adb6-103">Elemento \<system.runtime.caching> (configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="3adb6-103">\<system.runtime.caching> Element (Cache Settings)</span></span>

<span data-ttu-id="3adb6-104">Proporciona la configuración para la implementación predeterminada en memoria de la clase <xref:System.Runtime.Caching.ObjectCache> mediante la entrada `memoryCache` en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="3adb6-104">Provides configuration for the default in-memory <xref:System.Runtime.Caching.ObjectCache> implementation through the `memoryCache` entry in the configuration file.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.runtime.caching>**  
  
## <a name="syntax"></a><span data-ttu-id="3adb6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3adb6-105">Syntax</span></span>  
  
```xml  
<system.runtime.caching >  
   <!-- child elements -->  
</system.runtime.caching >  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3adb6-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3adb6-106">Attributes and Elements</span></span>

<span data-ttu-id="3adb6-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3adb6-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3adb6-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="3adb6-108">Attributes</span></span>

`None`  

### <a name="child-elements"></a><span data-ttu-id="3adb6-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3adb6-109">Child Elements</span></span>

|<span data-ttu-id="3adb6-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="3adb6-110">Element</span></span>|<span data-ttu-id="3adb6-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="3adb6-111">Description</span></span>|  
|-------------|-----------------|  
|[\<memoryCache>](memorycache-element-cache-settings.md)|<span data-ttu-id="3adb6-112">Define un elemento que se usa para configurar una memoria caché basada en la clase <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="3adb6-112">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3adb6-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3adb6-113">Parent Elements</span></span>  
  
|<span data-ttu-id="3adb6-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="3adb6-114">Element</span></span>|<span data-ttu-id="3adb6-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="3adb6-115">Description</span></span>|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|<span data-ttu-id="3adb6-116">Especifica el elemento raíz de cada archivo de configuración usado por las aplicaciones Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3adb6-116">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3adb6-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3adb6-117">Remarks</span></span>

<span data-ttu-id="3adb6-118">Las clases de este espacio de nombres proporcionan una manera de usar las funciones de almacenamiento en caché, como las de ASP.NET, pero sin una dependencia en el ensamblado `System.Web` .</span><span class="sxs-lookup"><span data-stu-id="3adb6-118">The classes in this namespace provide a way to use caching facilities like those in ASP.NET, but without a dependency on the `System.Web` assembly.</span></span> <span data-ttu-id="3adb6-119">Para obtener más información, consulta [Caching in .NET Framework Applications](../../../performance/caching-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="3adb6-119">For more information, see [Caching in .NET Framework Applications](../../../performance/caching-in-net-framework-applications.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3adb6-120">La funcionalidad de almacenamiento en caché de resultados y los tipos del <xref:System.Runtime.Caching> espacio de nombres son nuevos en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="3adb6-120">The output caching functionality and types in the <xref:System.Runtime.Caching> namespace are new in .NET Framework 4.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3adb6-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3adb6-121">Example</span></span>

<span data-ttu-id="3adb6-122">En el ejemplo siguiente se muestra cómo configurar una memoria caché basada en la clase <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="3adb6-122">The following example shows how to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span> <span data-ttu-id="3adb6-123">En el ejemplo se muestra cómo configurar una instancia de la entrada `namedCaches` de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="3adb6-123">The example shows how to configure an instance of the `namedCaches` entry for memory cache.</span></span> <span data-ttu-id="3adb6-124">El nombre de la memoria caché se establece en el nombre de la entrada de caché predeterminado estableciendo el `name` atributo en "default".</span><span class="sxs-lookup"><span data-stu-id="3adb6-124">The name of the cache is set to the default cache entry name by setting the `name` attribute to "Default".</span></span>  
  
<span data-ttu-id="3adb6-125">Los atributos `cacheMemoryLimitMegabytes` y `physicalMemoryPercentage` se establecen en cero.</span><span class="sxs-lookup"><span data-stu-id="3adb6-125">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="3adb6-126">El hecho de establecer estos atributos en cero implica que la heurística de ajuste automático de tamaño de <xref:System.Runtime.Caching.MemoryCache> se usa de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3adb6-126">Setting these attributes to zero means that the <xref:System.Runtime.Caching.MemoryCache> autosizing heuristics are used by default.</span></span> <span data-ttu-id="3adb6-127">La implementación de la memoria caché debe comparar cada dos minutos la carga de memoria actual con los límites de memoria absoluto y de porcentaje.</span><span class="sxs-lookup"><span data-stu-id="3adb6-127">The cache implementation should compare the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3adb6-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="3adb6-128">See also</span></span>

- [<span data-ttu-id="3adb6-129">\<memoryCache> (Elemento, configuración de caché)</span><span class="sxs-lookup"><span data-stu-id="3adb6-129">\<memoryCache> Element (Cache Settings)</span></span>](memorycache-element-cache-settings.md)
