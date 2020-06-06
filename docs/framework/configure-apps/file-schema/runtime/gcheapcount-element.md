---
title: Elemento GCHeapCount
ms.date: 11/08/2019
helpviewer_keywords:
- gcHeapCount element
- <gcHeapCount> element
ms.openlocfilehash: 3d6cac4185af182758cb82e6bfd9d96ed24869b4
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74283068"
---
# <a name="gcheapcount-element"></a><span data-ttu-id="f405a-102">Elemento \<GCHeapCount></span><span class="sxs-lookup"><span data-stu-id="f405a-102">\<GCHeapCount> element</span></span>

<span data-ttu-id="f405a-103">Especifica el número de montones o subprocesos que se usarán para la recolección de elementos no utilizados de servidor.</span><span class="sxs-lookup"><span data-stu-id="f405a-103">Specifies the number of heaps/threads to use for server garbage collection.</span></span>

\<configuration>\
&nbsp;&nbsp;\<runtime>\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCHeapCount>

## <a name="syntax"></a><span data-ttu-id="f405a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f405a-104">Syntax</span></span>

```xml
<GCHeapCount
   enabled="nn"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f405a-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f405a-105">Attributes and elements</span></span>

<span data-ttu-id="f405a-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f405a-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="f405a-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="f405a-107">Attributes</span></span>

|<span data-ttu-id="f405a-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="f405a-108">Attribute</span></span>|<span data-ttu-id="f405a-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="f405a-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="f405a-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="f405a-110">Required attribute.</span></span><br /><br /><span data-ttu-id="f405a-111">Especifica el número de montones que se usarán para la recolección de elementos no utilizados de servidor.</span><span class="sxs-lookup"><span data-stu-id="f405a-111">Specifies the number of heaps to use for server garbage collection.</span></span> <span data-ttu-id="f405a-112">El número real de montones es el mínimo del número de montones que especifique y el número de procesadores que puede usar el proceso.</span><span class="sxs-lookup"><span data-stu-id="f405a-112">The actual number of heaps is the minimum of the number of heaps you specify and the number of processors your process is allowed to use.</span></span> |

#### <a name="enabled-attribute"></a><span data-ttu-id="f405a-113">atributo Enabled</span><span class="sxs-lookup"><span data-stu-id="f405a-113">enabled attribute</span></span>

|<span data-ttu-id="f405a-114">Value</span><span class="sxs-lookup"><span data-stu-id="f405a-114">Value</span></span>|<span data-ttu-id="f405a-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="f405a-115">Description</span></span>|
|-----------|-----------------|
|`nn`|<span data-ttu-id="f405a-116">El número de montones que se usarán para el GC del servidor.</span><span class="sxs-lookup"><span data-stu-id="f405a-116">The number of heaps to use for server GC.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="f405a-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f405a-117">Child elements</span></span>

<span data-ttu-id="f405a-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f405a-118">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f405a-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f405a-119">Parent elements</span></span>

|<span data-ttu-id="f405a-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="f405a-120">Element</span></span>|<span data-ttu-id="f405a-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="f405a-121">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="f405a-122">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f405a-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="f405a-123">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="f405a-123">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f405a-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f405a-124">Remarks</span></span>

<span data-ttu-id="f405a-125">De forma predeterminada, los subprocesos de GC de servidor son afinidad cons con su CPU respectiva, de modo que hay un montón de GC, un subproceso de GC de servidor y un subproceso de GC de servidor en segundo plano para cada procesador.</span><span class="sxs-lookup"><span data-stu-id="f405a-125">By default, server GC threads are hard-affinitized with their respective CPU so that there is one GC heap, one server GC thread, and one background server GC thread for each processor.</span></span> <span data-ttu-id="f405a-126">A partir de .NET Framework 4.6.2, puede usar el elemento **GCHeapCount** para limitar el número de montones usados por la aplicación para el GC del servidor.</span><span class="sxs-lookup"><span data-stu-id="f405a-126">Starting with .NET Framework 4.6.2, you can use the **GCHeapCount** element to limit the number of heaps used by your application for server GC.</span></span> <span data-ttu-id="f405a-127">Limitar el número de montones usados para el GC del servidor es especialmente útil para los sistemas que ejecutan varias instancias de una aplicación de servidor.</span><span class="sxs-lookup"><span data-stu-id="f405a-127">Limiting the number of heaps used for server GC is particularly useful for systems that run multiple instances of a server application.</span></span>

<span data-ttu-id="f405a-128">**GCHeapCount** se usa normalmente junto con otras dos marcas:</span><span class="sxs-lookup"><span data-stu-id="f405a-128">**GCHeapCount** is typically used along with two other flags:</span></span>

- <span data-ttu-id="f405a-129">[GCNoAffinitize](gcnoaffinitize-element.md), que controla si los subprocesos o montones de GC del servidor se afinidad con con CPU.</span><span class="sxs-lookup"><span data-stu-id="f405a-129">[GCNoAffinitize](gcnoaffinitize-element.md), which controls whether server GC threads/heaps are affinitized with CPUs.</span></span>

- <span data-ttu-id="f405a-130">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md), que controla la afinidad de los subprocesos o montones de GC con las CPU.</span><span class="sxs-lookup"><span data-stu-id="f405a-130">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md), which controls the affinity of GC threads/heaps with CPUs.</span></span>

<span data-ttu-id="f405a-131">Si se establece **GCHeapCount** y **GCNoAffinitize** está deshabilitado (su configuración predeterminada), existe una afinidad entre los montones o subprocesos de GC de *nn* y *los primeros.*</span><span class="sxs-lookup"><span data-stu-id="f405a-131">If **GCHeapCount** is set and **GCNoAffinitize** is disabled (its default setting), there is an affinity between the *nn* GC threads/heaps and the first *nn* processors.</span></span> <span data-ttu-id="f405a-132">Puede usar el elemento **GCHeapAffinitizeMask** para especificar qué procesadores usan los montones de GC del servidor del proceso.</span><span class="sxs-lookup"><span data-stu-id="f405a-132">You can use the **GCHeapAffinitizeMask** element to specify which processors are used by the process's server GC heaps.</span></span> <span data-ttu-id="f405a-133">De lo contrario, si se ejecutan varios procesos de servidor en un sistema, el uso del procesador se superpondrá.</span><span class="sxs-lookup"><span data-stu-id="f405a-133">Otherwise, if multiple server processes are running on a system, their processor usage will overlap.</span></span>

<span data-ttu-id="f405a-134">Si se establece **GCHeapCount** y **GCNoAffinitize** está habilitado, el recolector de elementos no utilizados limita el número de procesadores que se usan para el GC del servidor, pero no establecer afinidad entre los montones y procesadores de GC.</span><span class="sxs-lookup"><span data-stu-id="f405a-134">If **GCHeapCount** is set and **GCNoAffinitize** is enabled, the garbage collector limits the number of processors used for server GC but does not affinitize GC heaps and processors.</span></span>

## <a name="example"></a><span data-ttu-id="f405a-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f405a-135">Example</span></span>

<span data-ttu-id="f405a-136">En el ejemplo siguiente se indica que una aplicación usa un GC de servidor con 10 subprocesos o montones.</span><span class="sxs-lookup"><span data-stu-id="f405a-136">The following example indicates that an application uses server GC with 10 heaps/threads.</span></span> <span data-ttu-id="f405a-137">Dado que no desea que esos montones se superpongan con montones de otras aplicaciones que se ejecutan en el sistema, use **GCHeapAffinitizeMask** para especificar que el proceso debe utilizar las CPU de 0 a 9.</span><span class="sxs-lookup"><span data-stu-id="f405a-137">Since you don't want those heaps to overlap with heaps from other applications running on the system, you use the **GCHeapAffinitizeMask** to specify that the process should use CPUs 0 through 9.</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCHeapAffinitizeMask enabled="1023"/>
   </runtime>
</configuration>
```

<span data-ttu-id="f405a-138">En el ejemplo siguiente no se establecer afinidad entre los subprocesos de GC del servidor y se limita el número de subprocesos o montones de GC a 10.</span><span class="sxs-lookup"><span data-stu-id="f405a-138">The following example does not affinitize server GC threads and limits the number of GC heaps/threads to 10.</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="f405a-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f405a-139">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f405a-140">Elemento GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="f405a-140">GCNoAffinitize element</span></span>](gcnoaffinitize-element.md)
- [<span data-ttu-id="f405a-141">Elemento GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="f405a-141">GCHeapAffinitizeMask element</span></span>](gcheapaffinitizemask-element.md)
- [<span data-ttu-id="f405a-142">Fundamentos de la recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="f405a-142">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="f405a-143">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="f405a-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f405a-144">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="f405a-144">Configuration File Schema</span></span>](../index.md)
