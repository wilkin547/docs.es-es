---
title: '&lt;gcConcurrent&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ee00c3a307523d2cae831274630ad6828cd9daf6
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltgcconcurrentgt-element"></a><span data-ttu-id="44df7-102">&lt;gcConcurrent&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="44df7-102">&lt;gcConcurrent&gt; Element</span></span>
<span data-ttu-id="44df7-103">Especifica si Common Language Runtime ejecuta la recolección de elementos no utilizados en un subproceso independiente.</span><span class="sxs-lookup"><span data-stu-id="44df7-103">Specifies whether the common language runtime runs garbage collection on a separate thread.</span></span>  
  
 <span data-ttu-id="44df7-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="44df7-104">\<configuration></span></span>  
<span data-ttu-id="44df7-105">\<en tiempo de ejecución ></span><span class="sxs-lookup"><span data-stu-id="44df7-105">\<runtime></span></span>  
<span data-ttu-id="44df7-106">\<gcConcurrent ></span><span class="sxs-lookup"><span data-stu-id="44df7-106">\<gcConcurrent></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44df7-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="44df7-107">Syntax</span></span>  
  
```xml  
<gcConcurrent    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44df7-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="44df7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="44df7-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="44df7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44df7-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="44df7-110">Attributes</span></span>  
  
|<span data-ttu-id="44df7-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="44df7-111">Attribute</span></span>|<span data-ttu-id="44df7-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="44df7-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="44df7-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="44df7-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="44df7-114">Especifica si CLR ejecuta la recolección de elementos no utilizados simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="44df7-114">Specifies whether the runtime runs garbage collection concurrently.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="44df7-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="44df7-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="44df7-116">Valor</span><span class="sxs-lookup"><span data-stu-id="44df7-116">Value</span></span>|<span data-ttu-id="44df7-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="44df7-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="44df7-118">No ejecuta la recolección de elementos no utilizados simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="44df7-118">Does not run garbage collection concurrently.</span></span>|  
|`true`|<span data-ttu-id="44df7-119">Ejecuta la recolección de elementos no utilizados simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="44df7-119">Runs garbage collection concurrently.</span></span> <span data-ttu-id="44df7-120">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="44df7-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="44df7-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="44df7-121">Child Elements</span></span>  
 <span data-ttu-id="44df7-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="44df7-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="44df7-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="44df7-123">Parent Elements</span></span>  
  
|<span data-ttu-id="44df7-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="44df7-124">Element</span></span>|<span data-ttu-id="44df7-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="44df7-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="44df7-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="44df7-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="44df7-127">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="44df7-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44df7-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="44df7-128">Remarks</span></span>  
 <span data-ttu-id="44df7-129">Antes de .NET Framework 4, la recolección de elementos no utilizados de estación de trabajo permitía la recolección de elementos no utilizados  simultánea, que se realizaba en segundo plano en un subproceso independiente.</span><span class="sxs-lookup"><span data-stu-id="44df7-129">Prior to the .NET Framework 4, workstation garbage collection supported concurrent garbage collection, which performed garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="44df7-130">En .NET Framework 4, la recolección de elementos no utilizados simultánea se reemplazó por GC, que también realiza la recolección de elementos no utilizados en segundo plano en un subproceso independiente.</span><span class="sxs-lookup"><span data-stu-id="44df7-130">In the .NET Framework 4, concurrent garbage collection was replaced by background GC, which also performs garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="44df7-131">A partir de .NET Framework 4.5, la recolección de elementos no utilizados de servidor se puede realizar en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="44df7-131">Starting with the .NET Framework 4.5, background collection became available in server garbage collection.</span></span> <span data-ttu-id="44df7-132">El elemento `<gcConcurrent>` controla si CLR realiza la recolección de elementos no utilizados simultáneamente o en segundo plano, si está disponible o si realiza la recolección de elementos no utilizados en primer plano.</span><span class="sxs-lookup"><span data-stu-id="44df7-132">The `<gcConcurrent>` element controls whether the runtime performs either concurrent or background garbage collection, if it is available, or whether it performs garbage collection in the foreground.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="44df7-133">A partir de .NET Framework 4, la recolección de elementos no utilizados en segundo plano reemplaza a la recolección de elementos no utilizados simultánea.</span><span class="sxs-lookup"><span data-stu-id="44df7-133">Starting with the .NET Framework 4, concurrent garbage collection is replaced by background garbage collection.</span></span> <span data-ttu-id="44df7-134">Los términos *simultáneas* y *fondo* se usan indistintamente en la documentación de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="44df7-134">The terms *concurrent* and *background* are used interchangeably in the .NET Framework documentation.</span></span> <span data-ttu-id="44df7-135">Para deshabilitar la recolección de elementos no utilizados en segundo plano, use el elemento `<gcConcurrent>` tal y como se describe en este artículo.</span><span class="sxs-lookup"><span data-stu-id="44df7-135">To disable background garbage collection, use the `<gcConcurrent>` element, as discussed in this article.</span></span>  
  
 <span data-ttu-id="44df7-136">De forma predeterminada, CLR usa la recolección de elementos no utilizados simultánea, que está optimizada para la latencia.</span><span class="sxs-lookup"><span data-stu-id="44df7-136">By default, the runtime uses concurrent or background garbage collection, which is optimized for latency.</span></span> <span data-ttu-id="44df7-137">Si la aplicación requiere mucha interacción por parte del usuario, deje habilitada la recolección de elementos no utilizados simultánea para minimizar el tiempo que la aplicación debe parar para realizar la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="44df7-137">If your application involves heavy user interaction, leave concurrent garbage collection enabled to minimize the application's pause time to perform garbage collection.</span></span> <span data-ttu-id="44df7-138">Si establece el atributo `enabled` del elemento `<gcConcurrent>` en `false`, CLR usa la recolección de elementos no utilizados no simultánea, que está optimizada para el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="44df7-138">If you set the `enabled` attribute of the `<gcConcurrent>` element to `false`, the runtime uses non-concurrent garbage collection, which is optimized for throughput.</span></span> <span data-ttu-id="44df7-139">El archivo de configuración siguiente deshabilita la recolección de elementos no utilizados en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="44df7-139">The following configuration file disables background garbage collection.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <gcConcurrent enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="44df7-140">Si hay una opción de configuración `<gcConcurrentSetting>` en el archivo de configuración del equipo, define el valor predeterminado para todas las aplicaciones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="44df7-140">If there is a `<gcConcurrentSetting>` setting in the machine configuration file, it defines the default value for all .NET Framework applications.</span></span> <span data-ttu-id="44df7-141">El archivo de configuración del equipo reemplaza el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="44df7-141">The machine configuration file setting overrides the application configuration file setting.</span></span>  
  
 <span data-ttu-id="44df7-142">Para obtener más información sobre simultáneas y recolección en segundo plano, consulte la sección "recopilación de elementos no utilizados simultánea" en la [aspectos básicos de la recopilación de elementos no utilizados](../../../../../docs/standard/garbage-collection/fundamentals.md) tema.</span><span class="sxs-lookup"><span data-stu-id="44df7-142">For more information on concurrent and background garbage collection, see the "Concurrent garbage collection" section in the [Fundamentals of Garbage Collection](../../../../../docs/standard/garbage-collection/fundamentals.md) topic.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44df7-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="44df7-143">Example</span></span>  
 <span data-ttu-id="44df7-144">En el ejemplo siguiente se habilita la recolección de elementos no utilizados simultánea.</span><span class="sxs-lookup"><span data-stu-id="44df7-144">The following example enables concurrent garbage collection.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <gcConcurrent enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="44df7-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="44df7-145">See Also</span></span>  
 [<span data-ttu-id="44df7-146">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="44df7-146">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="44df7-147">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="44df7-147">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="44df7-148">Fundamentos de la recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="44df7-148">Fundamentals of Garbage Collection</span></span>](../../../../../docs/standard/garbage-collection/fundamentals.md)
