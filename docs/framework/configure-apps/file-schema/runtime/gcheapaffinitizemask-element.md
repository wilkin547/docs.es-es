---
description: 'Más información acerca de: <GCHeapAffinitizeMask> elemento'
title: Elemento GCHeapAffinitizeMask
ms.date: 11/08/2019
helpviewer_keywords:
- gcHeapCount element
- <gcHeapCount> element
ms.openlocfilehash: ea6be3fa3d973f228576db69d0700b1f7ddba585
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786985"
---
# <a name="gcheapaffinitizemask-element"></a><span data-ttu-id="becb0-103">Elemento \<GCHeapAffinitizeMask></span><span class="sxs-lookup"><span data-stu-id="becb0-103">\<GCHeapAffinitizeMask> element</span></span>

<span data-ttu-id="becb0-104">Define la afinidad entre los montones de GC y los procesadores individuales.</span><span class="sxs-lookup"><span data-stu-id="becb0-104">Defines the affinity between GC heaps and individual processors.</span></span>

\<configuration>\
&nbsp;&nbsp;\<runtime>\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCHeapAffinitizeMask>

## <a name="syntax"></a><span data-ttu-id="becb0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="becb0-105">Syntax</span></span>

```xml
<GCHeapAffinitizeMask
   enabled="nnnn"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="becb0-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="becb0-106">Attributes and elements</span></span>

<span data-ttu-id="becb0-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="becb0-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="becb0-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="becb0-108">Attributes</span></span>

|<span data-ttu-id="becb0-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="becb0-109">Attribute</span></span>|<span data-ttu-id="becb0-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="becb0-110">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="becb0-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="becb0-111">Required attribute.</span></span><br /><br /><span data-ttu-id="becb0-112">Especifica la afinidad entre los montones de GC y los procesadores individuales.</span><span class="sxs-lookup"><span data-stu-id="becb0-112">Specifies the affinity between GC heaps and individual processors.</span></span> |

#### <a name="enabled-attribute"></a><span data-ttu-id="becb0-113">atributo Enabled</span><span class="sxs-lookup"><span data-stu-id="becb0-113">enabled attribute</span></span>

|<span data-ttu-id="becb0-114">Value</span><span class="sxs-lookup"><span data-stu-id="becb0-114">Value</span></span>|<span data-ttu-id="becb0-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="becb0-115">Description</span></span>|
|-----------|-----------------|
|`nnnn`|<span data-ttu-id="becb0-116">Un valor decimal que constituye una máscara de máscara que define la afinidad entre los montones de GC del servidor y los procesadores individuales.</span><span class="sxs-lookup"><span data-stu-id="becb0-116">A decimal value that forms a bitmask defining the affinity between server GC heaps and individual processors.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="becb0-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="becb0-117">Child elements</span></span>

<span data-ttu-id="becb0-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="becb0-118">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="becb0-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="becb0-119">Parent elements</span></span>

|<span data-ttu-id="becb0-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="becb0-120">Element</span></span>|<span data-ttu-id="becb0-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="becb0-121">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="becb0-122">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="becb0-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="becb0-123">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="becb0-123">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="becb0-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="becb0-124">Remarks</span></span>

<span data-ttu-id="becb0-125">De forma predeterminada, los subprocesos de GC de servidor son afinidad cons con su CPU respectiva, de modo que hay un montón de GC, un subproceso de GC de servidor y un subproceso de GC de servidor en segundo plano para cada procesador.</span><span class="sxs-lookup"><span data-stu-id="becb0-125">By default, server GC threads are hard-affinitized with their respective CPU so that there is one GC heap, one server GC thread, and one background server GC thread for each processor.</span></span> <span data-ttu-id="becb0-126">A partir de .NET Framework 4.6.2, puede usar el elemento **GCHeapAffinitizeMask** para controlar la afinidad entre los montones y los procesadores de GC del servidor cuando el número de montones está limitado por el elemento **GCHeapCount** .</span><span class="sxs-lookup"><span data-stu-id="becb0-126">Starting with .NET Framework 4.6.2, you can use the **GCHeapAffinitizeMask** element to control the affinity between server GC heaps and processors when the number of heaps is limited by the **GCHeapCount** element.</span></span>

<span data-ttu-id="becb0-127">**GCHeapAffinitizeMask** se usa normalmente junto con otras dos marcas:</span><span class="sxs-lookup"><span data-stu-id="becb0-127">**GCHeapAffinitizeMask** is typically used along with two other flags:</span></span>

- <span data-ttu-id="becb0-128">[GCNoAffinitize](gcnoaffinitize-element.md), que controla si los subprocesos o montones de GC del servidor se afinidad con con CPU.</span><span class="sxs-lookup"><span data-stu-id="becb0-128">[GCNoAffinitize](gcnoaffinitize-element.md), which controls whether server GC threads/heaps are affinitized with CPUs.</span></span> <span data-ttu-id="becb0-129">El `enabled` atributo del elemento [GCNoAffinitize](gcnoaffinitize-element.md) debe ser `false` (su valor predeterminado) para que se use el valor **GCHeapAffinitizeMask** .</span><span class="sxs-lookup"><span data-stu-id="becb0-129">The `enabled` attribute of the [GCNoAffinitize](gcnoaffinitize-element.md) element must be `false` (its default value) for the **GCHeapAffinitizeMask** setting to be used.</span></span>

- <span data-ttu-id="becb0-130">[GCHeapCount](gcheapcount-element.md), que limita el número de montones utilizados por el proceso para el GC del servidor.</span><span class="sxs-lookup"><span data-stu-id="becb0-130">[GCHeapCount](gcheapcount-element.md), which limits the number of heaps used by the process for server GC.</span></span> <span data-ttu-id="becb0-131">De forma predeterminada, hay un montón para cada procesador.</span><span class="sxs-lookup"><span data-stu-id="becb0-131">By default, there is one heap for each processor.</span></span>

<span data-ttu-id="becb0-132">**nnnn** es una máscara de bits expresada como un valor decimal.</span><span class="sxs-lookup"><span data-stu-id="becb0-132">**nnnn** is a bit mask expressed as a decimal value.</span></span> <span data-ttu-id="becb0-133">El bit 0 de byte 0 representa el procesador 0, bit 1 de byte 0 representa el procesador 1, etc.</span><span class="sxs-lookup"><span data-stu-id="becb0-133">Bit 0 of byte 0 represents processor 0, bit 1 of byte 0 represents processor 1, and so on.</span></span> <span data-ttu-id="becb0-134">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="becb0-134">For example:</span></span>

```xml
<GCHeapAffinitizeMask enabled="1023"/>
```

<span data-ttu-id="becb0-135">Un valor de 1023 es 0x3FF o 0011 1111 1111b.</span><span class="sxs-lookup"><span data-stu-id="becb0-135">A value of 1023 is 0x3FF or 0011 1111 1111b.</span></span> <span data-ttu-id="becb0-136">El proceso utiliza 10 procesadores, desde el procesador 0 hasta el procesador 9.</span><span class="sxs-lookup"><span data-stu-id="becb0-136">The process uses 10 processors, from processor 0 through processor 9.</span></span>

## <a name="example"></a><span data-ttu-id="becb0-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="becb0-137">Example</span></span>

<span data-ttu-id="becb0-138">En el ejemplo siguiente se indica que una aplicación usa un GC de servidor con 10 subprocesos o montones.</span><span class="sxs-lookup"><span data-stu-id="becb0-138">The following example indicates that an application uses server GC with 10 heaps/threads.</span></span> <span data-ttu-id="becb0-139">Dado que no desea que esos montones se superpongan con montones de otras aplicaciones que se ejecutan en el sistema, use **GCHeapAffinitizeMask** para especificar que el proceso debe usar las CPU de 0 a 9.</span><span class="sxs-lookup"><span data-stu-id="becb0-139">Since you don't want those heaps to overlap with heaps from other applications running on the system, use **GCHeapAffinitizeMask** to specify that the process should use CPUs 0 through 9.</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCHeapAffinitizeMask enabled="1023"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="becb0-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="becb0-140">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="becb0-141">Elemento GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="becb0-141">GCNoAffinitize element</span></span>](gcnoaffinitize-element.md)
- [<span data-ttu-id="becb0-142">Elemento GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="becb0-142">GCHeapCount element</span></span>](gcheapcount-element.md)
- [<span data-ttu-id="becb0-143">Fundamentos de la recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="becb0-143">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="becb0-144">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="becb0-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="becb0-145">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="becb0-145">Configuration File Schema</span></span>](../index.md)
