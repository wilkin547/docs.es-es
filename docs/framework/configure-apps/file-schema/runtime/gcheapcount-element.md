---
description: 'Más información acerca de: <GCHeapCount> elemento'
title: Elemento GCHeapCount
ms.date: 11/08/2019
helpviewer_keywords:
- gcHeapCount element
- <gcHeapCount> element
ms.openlocfilehash: 9e1e000d647435fe7a8c4b1a8f7549f06c2a3b38
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786972"
---
# <a name="gcheapcount-element"></a><span data-ttu-id="61ad3-103">Elemento \<GCHeapCount></span><span class="sxs-lookup"><span data-stu-id="61ad3-103">\<GCHeapCount> element</span></span>

<span data-ttu-id="61ad3-104">Especifica el número de montones o subprocesos que se usarán para la recolección de elementos no utilizados de servidor.</span><span class="sxs-lookup"><span data-stu-id="61ad3-104">Specifies the number of heaps/threads to use for server garbage collection.</span></span>

\<configuration>\
&nbsp;&nbsp;\<runtime>\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCHeapCount>

## <a name="syntax"></a><span data-ttu-id="61ad3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="61ad3-105">Syntax</span></span>

```xml
<GCHeapCount
   enabled="nn"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="61ad3-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="61ad3-106">Attributes and elements</span></span>

<span data-ttu-id="61ad3-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="61ad3-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="61ad3-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="61ad3-108">Attributes</span></span>

|<span data-ttu-id="61ad3-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="61ad3-109">Attribute</span></span>|<span data-ttu-id="61ad3-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="61ad3-110">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="61ad3-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="61ad3-111">Required attribute.</span></span><br /><br /><span data-ttu-id="61ad3-112">Especifica el número de montones que se usarán para la recolección de elementos no utilizados de servidor.</span><span class="sxs-lookup"><span data-stu-id="61ad3-112">Specifies the number of heaps to use for server garbage collection.</span></span> <span data-ttu-id="61ad3-113">El número real de montones es el mínimo del número de montones que especifique y el número de procesadores que puede usar el proceso.</span><span class="sxs-lookup"><span data-stu-id="61ad3-113">The actual number of heaps is the minimum of the number of heaps you specify and the number of processors your process is allowed to use.</span></span> |

#### <a name="enabled-attribute"></a><span data-ttu-id="61ad3-114">atributo Enabled</span><span class="sxs-lookup"><span data-stu-id="61ad3-114">enabled attribute</span></span>

|<span data-ttu-id="61ad3-115">Value</span><span class="sxs-lookup"><span data-stu-id="61ad3-115">Value</span></span>|<span data-ttu-id="61ad3-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="61ad3-116">Description</span></span>|
|-----------|-----------------|
|`nn`|<span data-ttu-id="61ad3-117">El número de montones que se usarán para el GC del servidor.</span><span class="sxs-lookup"><span data-stu-id="61ad3-117">The number of heaps to use for server GC.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="61ad3-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="61ad3-118">Child elements</span></span>

<span data-ttu-id="61ad3-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="61ad3-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="61ad3-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="61ad3-120">Parent elements</span></span>

|<span data-ttu-id="61ad3-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="61ad3-121">Element</span></span>|<span data-ttu-id="61ad3-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="61ad3-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="61ad3-123">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="61ad3-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="61ad3-124">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="61ad3-124">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="61ad3-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="61ad3-125">Remarks</span></span>

<span data-ttu-id="61ad3-126">De forma predeterminada, los subprocesos de GC de servidor son afinidad cons con su CPU respectiva, de modo que hay un montón de GC, un subproceso de GC de servidor y un subproceso de GC de servidor en segundo plano para cada procesador.</span><span class="sxs-lookup"><span data-stu-id="61ad3-126">By default, server GC threads are hard-affinitized with their respective CPU so that there is one GC heap, one server GC thread, and one background server GC thread for each processor.</span></span> <span data-ttu-id="61ad3-127">A partir de .NET Framework 4.6.2, puede usar el elemento **GCHeapCount** para limitar el número de montones usados por la aplicación para el GC del servidor.</span><span class="sxs-lookup"><span data-stu-id="61ad3-127">Starting with .NET Framework 4.6.2, you can use the **GCHeapCount** element to limit the number of heaps used by your application for server GC.</span></span> <span data-ttu-id="61ad3-128">Limitar el número de montones usados para el GC del servidor es especialmente útil para los sistemas que ejecutan varias instancias de una aplicación de servidor.</span><span class="sxs-lookup"><span data-stu-id="61ad3-128">Limiting the number of heaps used for server GC is particularly useful for systems that run multiple instances of a server application.</span></span>

<span data-ttu-id="61ad3-129">**GCHeapCount** se usa normalmente junto con otras dos marcas:</span><span class="sxs-lookup"><span data-stu-id="61ad3-129">**GCHeapCount** is typically used along with two other flags:</span></span>

- <span data-ttu-id="61ad3-130">[GCNoAffinitize](gcnoaffinitize-element.md), que controla si los subprocesos o montones de GC del servidor se afinidad con con CPU.</span><span class="sxs-lookup"><span data-stu-id="61ad3-130">[GCNoAffinitize](gcnoaffinitize-element.md), which controls whether server GC threads/heaps are affinitized with CPUs.</span></span>

- <span data-ttu-id="61ad3-131">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md), que controla la afinidad de los subprocesos o montones de GC con las CPU.</span><span class="sxs-lookup"><span data-stu-id="61ad3-131">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md), which controls the affinity of GC threads/heaps with CPUs.</span></span>

<span data-ttu-id="61ad3-132">Si se establece **GCHeapCount** y **GCNoAffinitize** está deshabilitado (su configuración predeterminada), existe una afinidad entre los montones o subprocesos de GC de *nn* y *los primeros.*</span><span class="sxs-lookup"><span data-stu-id="61ad3-132">If **GCHeapCount** is set and **GCNoAffinitize** is disabled (its default setting), there is an affinity between the *nn* GC threads/heaps and the first *nn* processors.</span></span> <span data-ttu-id="61ad3-133">Puede usar el elemento **GCHeapAffinitizeMask** para especificar qué procesadores usan los montones de GC del servidor del proceso.</span><span class="sxs-lookup"><span data-stu-id="61ad3-133">You can use the **GCHeapAffinitizeMask** element to specify which processors are used by the process's server GC heaps.</span></span> <span data-ttu-id="61ad3-134">De lo contrario, si se ejecutan varios procesos de servidor en un sistema, el uso del procesador se superpondrá.</span><span class="sxs-lookup"><span data-stu-id="61ad3-134">Otherwise, if multiple server processes are running on a system, their processor usage will overlap.</span></span>

<span data-ttu-id="61ad3-135">Si se establece **GCHeapCount** y **GCNoAffinitize** está habilitado, el recolector de elementos no utilizados limita el número de procesadores que se usan para el GC del servidor, pero no establecer afinidad entre los montones y procesadores de GC.</span><span class="sxs-lookup"><span data-stu-id="61ad3-135">If **GCHeapCount** is set and **GCNoAffinitize** is enabled, the garbage collector limits the number of processors used for server GC but does not affinitize GC heaps and processors.</span></span>

## <a name="example"></a><span data-ttu-id="61ad3-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="61ad3-136">Example</span></span>

<span data-ttu-id="61ad3-137">En el ejemplo siguiente se indica que una aplicación usa un GC de servidor con 10 subprocesos o montones.</span><span class="sxs-lookup"><span data-stu-id="61ad3-137">The following example indicates that an application uses server GC with 10 heaps/threads.</span></span> <span data-ttu-id="61ad3-138">Dado que no desea que esos montones se superpongan con montones de otras aplicaciones que se ejecutan en el sistema, use **GCHeapAffinitizeMask** para especificar que el proceso debe utilizar las CPU de 0 a 9.</span><span class="sxs-lookup"><span data-stu-id="61ad3-138">Since you don't want those heaps to overlap with heaps from other applications running on the system, you use the **GCHeapAffinitizeMask** to specify that the process should use CPUs 0 through 9.</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCHeapAffinitizeMask enabled="1023"/>
   </runtime>
</configuration>
```

<span data-ttu-id="61ad3-139">En el ejemplo siguiente no se establecer afinidad entre los subprocesos de GC del servidor y se limita el número de subprocesos o montones de GC a 10.</span><span class="sxs-lookup"><span data-stu-id="61ad3-139">The following example does not affinitize server GC threads and limits the number of GC heaps/threads to 10.</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="61ad3-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="61ad3-140">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="61ad3-141">Elemento GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="61ad3-141">GCNoAffinitize element</span></span>](gcnoaffinitize-element.md)
- [<span data-ttu-id="61ad3-142">Elemento GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="61ad3-142">GCHeapAffinitizeMask element</span></span>](gcheapaffinitizemask-element.md)
- [<span data-ttu-id="61ad3-143">Fundamentos de la recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="61ad3-143">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="61ad3-144">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="61ad3-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="61ad3-145">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="61ad3-145">Configuration File Schema</span></span>](../index.md)
