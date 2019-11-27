---
title: Elemento GCHeapCount
ms.date: 11/08/2019
helpviewer_keywords:
- gcHeapCount element
- <gcHeapCount> element
ms.openlocfilehash: 3d6cac4185af182758cb82e6bfd9d96ed24869b4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283068"
---
# <a name="gcheapcount-element"></a><span data-ttu-id="40de6-102">\<elemento > GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="40de6-102">\<GCHeapCount> element</span></span>

<span data-ttu-id="40de6-103">Especifica el número de montones o subprocesos que se usarán para la recolección de elementos no utilizados de servidor.</span><span class="sxs-lookup"><span data-stu-id="40de6-103">Specifies the number of heaps/threads to use for server garbage collection.</span></span>

<span data-ttu-id="40de6-104">\<Configuración > </span><span class="sxs-lookup"><span data-stu-id="40de6-104">\<configuration></span></span>\
<span data-ttu-id="40de6-105">&nbsp;&nbsp;\<Runtime > </span><span class="sxs-lookup"><span data-stu-id="40de6-105">&nbsp;&nbsp;\<runtime></span></span>\
<span data-ttu-id="40de6-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCHeapCount ></span><span class="sxs-lookup"><span data-stu-id="40de6-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCHeapCount></span></span>

## <a name="syntax"></a><span data-ttu-id="40de6-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="40de6-107">Syntax</span></span>

```xml
<GCHeapCount
   enabled="nn"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="40de6-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="40de6-108">Attributes and elements</span></span>

<span data-ttu-id="40de6-109">En las secciones siguientes se describen atributos, elementos secundarios y elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="40de6-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="40de6-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="40de6-110">Attributes</span></span>

|<span data-ttu-id="40de6-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="40de6-111">Attribute</span></span>|<span data-ttu-id="40de6-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="40de6-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="40de6-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="40de6-113">Required attribute.</span></span><br /><br /><span data-ttu-id="40de6-114">Especifica el número de montones que se usarán para la recolección de elementos no utilizados de servidor.</span><span class="sxs-lookup"><span data-stu-id="40de6-114">Specifies the number of heaps to use for server garbage collection.</span></span> <span data-ttu-id="40de6-115">El número real de montones es el mínimo del número de montones que especifique y el número de procesadores que puede usar el proceso.</span><span class="sxs-lookup"><span data-stu-id="40de6-115">The actual number of heaps is the minimum of the number of heaps you specify and the number of processors your process is allowed to use.</span></span> |

#### <a name="enabled-attribute"></a><span data-ttu-id="40de6-116">atributo Enabled</span><span class="sxs-lookup"><span data-stu-id="40de6-116">enabled attribute</span></span>

|<span data-ttu-id="40de6-117">Valor</span><span class="sxs-lookup"><span data-stu-id="40de6-117">Value</span></span>|<span data-ttu-id="40de6-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="40de6-118">Description</span></span>|
|-----------|-----------------|
|`nn`|<span data-ttu-id="40de6-119">El número de montones que se usarán para el GC del servidor.</span><span class="sxs-lookup"><span data-stu-id="40de6-119">The number of heaps to use for server GC.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="40de6-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="40de6-120">Child elements</span></span>

<span data-ttu-id="40de6-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="40de6-121">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="40de6-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="40de6-122">Parent elements</span></span>

|<span data-ttu-id="40de6-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="40de6-123">Element</span></span>|<span data-ttu-id="40de6-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="40de6-124">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="40de6-125">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="40de6-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="40de6-126">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="40de6-126">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="40de6-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="40de6-127">Remarks</span></span>

<span data-ttu-id="40de6-128">De forma predeterminada, los subprocesos de GC de servidor son afinidad cons con su CPU respectiva, de modo que hay un montón de GC, un subproceso de GC de servidor y un subproceso de GC de servidor en segundo plano para cada procesador.</span><span class="sxs-lookup"><span data-stu-id="40de6-128">By default, server GC threads are hard-affinitized with their respective CPU so that there is one GC heap, one server GC thread, and one background server GC thread for each processor.</span></span> <span data-ttu-id="40de6-129">A partir de .NET Framework 4.6.2, puede usar el elemento **GCHeapCount** para limitar el número de montones usados por la aplicación para el GC del servidor.</span><span class="sxs-lookup"><span data-stu-id="40de6-129">Starting with .NET Framework 4.6.2, you can use the **GCHeapCount** element to limit the number of heaps used by your application for server GC.</span></span> <span data-ttu-id="40de6-130">Limitar el número de montones usados para el GC del servidor es especialmente útil para los sistemas que ejecutan varias instancias de una aplicación de servidor.</span><span class="sxs-lookup"><span data-stu-id="40de6-130">Limiting the number of heaps used for server GC is particularly useful for systems that run multiple instances of a server application.</span></span>

<span data-ttu-id="40de6-131">**GCHeapCount** se usa normalmente junto con otras dos marcas:</span><span class="sxs-lookup"><span data-stu-id="40de6-131">**GCHeapCount** is typically used along with two other flags:</span></span>

- <span data-ttu-id="40de6-132">[GCNoAffinitize](gcnoaffinitize-element.md), que controla si los subprocesos o montones de GC del servidor se afinidad con con CPU.</span><span class="sxs-lookup"><span data-stu-id="40de6-132">[GCNoAffinitize](gcnoaffinitize-element.md), which controls whether server GC threads/heaps are affinitized with CPUs.</span></span>

- <span data-ttu-id="40de6-133">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md), que controla la afinidad de los subprocesos o montones de GC con las CPU.</span><span class="sxs-lookup"><span data-stu-id="40de6-133">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md), which controls the affinity of GC threads/heaps with CPUs.</span></span>

<span data-ttu-id="40de6-134">Si se establece **GCHeapCount** y **GCNoAffinitize** está deshabilitado (su configuración predeterminada), existe una afinidad entre los montones o subprocesos de GC de *nn* y *los primeros.*</span><span class="sxs-lookup"><span data-stu-id="40de6-134">If **GCHeapCount** is set and **GCNoAffinitize** is disabled (its default setting), there is an affinity between the *nn* GC threads/heaps and the first *nn* processors.</span></span> <span data-ttu-id="40de6-135">Puede usar el elemento **GCHeapAffinitizeMask** para especificar qué procesadores usan los montones de GC del servidor del proceso.</span><span class="sxs-lookup"><span data-stu-id="40de6-135">You can use the **GCHeapAffinitizeMask** element to specify which processors are used by the process's server GC heaps.</span></span> <span data-ttu-id="40de6-136">De lo contrario, si se ejecutan varios procesos de servidor en un sistema, el uso del procesador se superpondrá.</span><span class="sxs-lookup"><span data-stu-id="40de6-136">Otherwise, if multiple server processes are running on a system, their processor usage will overlap.</span></span>

<span data-ttu-id="40de6-137">Si se establece **GCHeapCount** y **GCNoAffinitize** está habilitado, el recolector de elementos no utilizados limita el número de procesadores que se usan para el GC del servidor, pero no establecer afinidad entre los montones y procesadores de GC.</span><span class="sxs-lookup"><span data-stu-id="40de6-137">If **GCHeapCount** is set and **GCNoAffinitize** is enabled, the garbage collector limits the number of processors used for server GC but does not affinitize GC heaps and processors.</span></span>

## <a name="example"></a><span data-ttu-id="40de6-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="40de6-138">Example</span></span>

<span data-ttu-id="40de6-139">En el ejemplo siguiente se indica que una aplicación usa un GC de servidor con 10 subprocesos o montones.</span><span class="sxs-lookup"><span data-stu-id="40de6-139">The following example indicates that an application uses server GC with 10 heaps/threads.</span></span> <span data-ttu-id="40de6-140">Dado que no desea que esos montones se superpongan con montones de otras aplicaciones que se ejecutan en el sistema, use **GCHeapAffinitizeMask** para especificar que el proceso debe utilizar las CPU de 0 a 9.</span><span class="sxs-lookup"><span data-stu-id="40de6-140">Since you don't want those heaps to overlap with heaps from other applications running on the system, you use the **GCHeapAffinitizeMask** to specify that the process should use CPUs 0 through 9.</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCHeapAffinitizeMask enabled="1023"/>
   </runtime>
</configuration>
```

<span data-ttu-id="40de6-141">En el ejemplo siguiente no se establecer afinidad entre los subprocesos de GC del servidor y se limita el número de subprocesos o montones de GC a 10.</span><span class="sxs-lookup"><span data-stu-id="40de6-141">The following example does not affinitize server GC threads and limits the number of GC heaps/threads to 10.</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="40de6-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="40de6-142">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="40de6-143">Elemento GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="40de6-143">GCNoAffinitize element</span></span>](gcnoaffinitize-element.md)
- [<span data-ttu-id="40de6-144">Elemento GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="40de6-144">GCHeapAffinitizeMask element</span></span>](gcheapaffinitizemask-element.md)
- [<span data-ttu-id="40de6-145">Fundamentos de la recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="40de6-145">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="40de6-146">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="40de6-146">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="40de6-147">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="40de6-147">Configuration File Schema</span></span>](../index.md)
