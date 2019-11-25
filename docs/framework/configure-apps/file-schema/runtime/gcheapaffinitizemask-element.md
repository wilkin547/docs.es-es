---
title: Elemento GCHeapAffinitizeMask
ms.date: 11/08/2019
helpviewer_keywords:
- gcHeapCount element
- <gcHeapCount> element
ms.openlocfilehash: 09d6523fb10692dd3617a3827d5bccf112bc632b
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73978424"
---
# <a name="gcheapaffinitizemask-element"></a><span data-ttu-id="048ff-102">\<elemento > GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="048ff-102">\<GCHeapAffinitizeMask> element</span></span>

<span data-ttu-id="048ff-103">Define la afinidad entre los montones de GC y los procesadores individuales.</span><span class="sxs-lookup"><span data-stu-id="048ff-103">Defines the affinity between GC heaps and individual processors.</span></span>

<span data-ttu-id="048ff-104">\<Configuración > </span><span class="sxs-lookup"><span data-stu-id="048ff-104">\<configuration></span></span>\
<span data-ttu-id="048ff-105">&nbsp;&nbsp;\<Runtime > </span><span class="sxs-lookup"><span data-stu-id="048ff-105">&nbsp;&nbsp;\<runtime></span></span>\
<span data-ttu-id="048ff-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCHeapAffinitizeMask ></span><span class="sxs-lookup"><span data-stu-id="048ff-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCHeapAffinitizeMask></span></span>

## <a name="syntax"></a><span data-ttu-id="048ff-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="048ff-107">Syntax</span></span>

```xml
<GCHeapAffinitizeMask
   enabled="nnnn"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="048ff-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="048ff-108">Attributes and elements</span></span>

<span data-ttu-id="048ff-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="048ff-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="048ff-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="048ff-110">Attributes</span></span>

|<span data-ttu-id="048ff-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="048ff-111">Attribute</span></span>|<span data-ttu-id="048ff-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="048ff-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="048ff-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="048ff-113">Required attribute.</span></span><br /><br /><span data-ttu-id="048ff-114">Especifica la afinidad entre los montones de GC y los procesadores individuales.</span><span class="sxs-lookup"><span data-stu-id="048ff-114">Specifies the affinity between GC heaps and individual processors.</span></span> |

#### <a name="enabled-attribute"></a><span data-ttu-id="048ff-115">atributo Enabled</span><span class="sxs-lookup"><span data-stu-id="048ff-115">enabled attribute</span></span>

|<span data-ttu-id="048ff-116">Valor</span><span class="sxs-lookup"><span data-stu-id="048ff-116">Value</span></span>|<span data-ttu-id="048ff-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="048ff-117">Description</span></span>|
|-----------|-----------------|
|`nnnn`|<span data-ttu-id="048ff-118">Un valor decimal que constituye una máscara de máscara que define la afinidad entre los montones de GC del servidor y los procesadores individuales.</span><span class="sxs-lookup"><span data-stu-id="048ff-118">A decimal value that forms a bitmask defining the affinity between server GC heaps and individual processors.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="048ff-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="048ff-119">Child elements</span></span>

<span data-ttu-id="048ff-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="048ff-120">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="048ff-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="048ff-121">Parent elements</span></span>

|<span data-ttu-id="048ff-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="048ff-122">Element</span></span>|<span data-ttu-id="048ff-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="048ff-123">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="048ff-124">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="048ff-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="048ff-125">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="048ff-125">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="048ff-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="048ff-126">Remarks</span></span>

<span data-ttu-id="048ff-127">De forma predeterminada, los subprocesos de GC de servidor son afinidad cons con su CPU respectiva, de modo que hay un montón de GC, un subproceso de GC de servidor y un subproceso de GC de servidor en segundo plano para cada procesador.</span><span class="sxs-lookup"><span data-stu-id="048ff-127">By default, server GC threads are hard-affinitized with their respective CPU so that there is one GC heap, one server GC thread, and one background server GC thread for each processor.</span></span> <span data-ttu-id="048ff-128">A partir de .NET Framework 4.6.2, puede usar el elemento **GCHeapAffinitizeMask** para controlar la afinidad entre los montones y los procesadores de GC del servidor cuando el número de montones está limitado por el elemento **GCHeapCount** .</span><span class="sxs-lookup"><span data-stu-id="048ff-128">Starting with .NET Framework 4.6.2, you can use the **GCHeapAffinitizeMask** element to control the affinity between server GC heaps and processors when the number of heaps is limited by the **GCHeapCount** element.</span></span>

<span data-ttu-id="048ff-129">**GCHeapAffinitizeMask** se usa normalmente junto con otras dos marcas:</span><span class="sxs-lookup"><span data-stu-id="048ff-129">**GCHeapAffinitizeMask** is typically used along with two other flags:</span></span>

- <span data-ttu-id="048ff-130">[GCNoAffinitize](gcnoaffinitize-element.md), que controla si los subprocesos o montones de GC del servidor se afinidad con con CPU.</span><span class="sxs-lookup"><span data-stu-id="048ff-130">[GCNoAffinitize](gcnoaffinitize-element.md), which controls whether server GC threads/heaps are affinitized with CPUs.</span></span> <span data-ttu-id="048ff-131">El atributo `enabled` del elemento [GCNoAffinitize](gcnoaffinitize-element.md) debe ser `false` (su valor predeterminado) para que se use el valor **GCHeapAffinitizeMask** .</span><span class="sxs-lookup"><span data-stu-id="048ff-131">The `enabled` attribute of the [GCNoAffinitize](gcnoaffinitize-element.md) element must be `false` (its default value) for the **GCHeapAffinitizeMask** setting to be used.</span></span>

- <span data-ttu-id="048ff-132">[GCHeapCount](gcheapcount-element.md), que limita el número de montones utilizados por el proceso para el GC del servidor.</span><span class="sxs-lookup"><span data-stu-id="048ff-132">[GCHeapCount](gcheapcount-element.md), which limits the number of heaps used by the process for server GC.</span></span> <span data-ttu-id="048ff-133">De forma predeterminada, hay un montón para cada procesador.</span><span class="sxs-lookup"><span data-stu-id="048ff-133">By default, there is one heap for each processor.</span></span>

<span data-ttu-id="048ff-134">**nnnn** es una máscara de bits expresada como un valor decimal.</span><span class="sxs-lookup"><span data-stu-id="048ff-134">**nnnn** is a bit mask expressed as a decimal value.</span></span> <span data-ttu-id="048ff-135">El bit 0 de byte 0 representa el procesador 0, bit 1 de byte 0 representa el procesador 1, etc.</span><span class="sxs-lookup"><span data-stu-id="048ff-135">Bit 0 of byte 0 represents processor 0, bit 1 of byte 0 represents processor 1, and so on.</span></span> <span data-ttu-id="048ff-136">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="048ff-136">For example:</span></span>

```xml
<GCHeapAffinitizeMask enabled="1023"/>
```

<span data-ttu-id="048ff-137">Un valor de 1023 es 0x3FF o 0011 1111 1111b.</span><span class="sxs-lookup"><span data-stu-id="048ff-137">A value of 1023 is 0x3FF or 0011 1111 1111b.</span></span> <span data-ttu-id="048ff-138">El proceso utiliza 10 procesadores, desde el procesador 0 hasta el procesador 9.</span><span class="sxs-lookup"><span data-stu-id="048ff-138">The process uses 10 processors, from processor 0 through processor 9.</span></span>

## <a name="example"></a><span data-ttu-id="048ff-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="048ff-139">Example</span></span>

<span data-ttu-id="048ff-140">En el ejemplo siguiente se indica que una aplicación usa un GC de servidor con 10 subprocesos o montones.</span><span class="sxs-lookup"><span data-stu-id="048ff-140">The following example indicates that an application uses server GC with 10 heaps/threads.</span></span> <span data-ttu-id="048ff-141">Dado que no desea que esos montones se superpongan con montones de otras aplicaciones que se ejecutan en el sistema, use **GCHeapAffinitizeMask** para especificar que el proceso debe usar las CPU de 0 a 9.</span><span class="sxs-lookup"><span data-stu-id="048ff-141">Since you don't want those heaps to overlap with heaps from other applications running on the system, use **GCHeapAffinitizeMask** to specify that the process should use CPUs 0 through 9.</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCHeapAffinitizeMask enabled="1023"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="048ff-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="048ff-142">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="048ff-143">Elemento GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="048ff-143">GCNoAffinitize element</span></span>](gcnoaffinitize-element.md)
- [<span data-ttu-id="048ff-144">Elemento GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="048ff-144">GCHeapCount element</span></span>](gcheapcount-element.md)
- [<span data-ttu-id="048ff-145">Fundamentos de la recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="048ff-145">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="048ff-146">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="048ff-146">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="048ff-147">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="048ff-147">Configuration File Schema</span></span>](../index.md)
