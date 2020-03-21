---
title: gcConcurrent Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
ms.openlocfilehash: 5957337aa960a0d5f445249b410dbfaddb7b08e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400984"
---
# <a name="gcconcurrent-element"></a><span data-ttu-id="a40eb-102">\<gcConcurrent> elemento</span><span class="sxs-lookup"><span data-stu-id="a40eb-102">\<gcConcurrent> element</span></span>

<span data-ttu-id="a40eb-103">Especifica si Common Language Runtime ejecuta la recolección de elementos no utilizados en un subproceso independiente.</span><span class="sxs-lookup"><span data-stu-id="a40eb-103">Specifies whether the common language runtime runs garbage collection on a separate thread.</span></span>

<span data-ttu-id="a40eb-104">[\<configuración>](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a40eb-104">[\<configuration>](../configuration-element.md)</span></span>\
<span data-ttu-id="a40eb-105">&nbsp;&nbsp;[\<>en tiempo de ejecución](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="a40eb-105">&nbsp;&nbsp;[\<runtime>](runtime-element.md)</span></span>\
<span data-ttu-id="a40eb-106">&nbsp;&nbsp;&nbsp;&nbsp;\<gcConcurrent></span><span class="sxs-lookup"><span data-stu-id="a40eb-106">&nbsp;&nbsp;&nbsp;&nbsp;\<gcConcurrent></span></span>

## <a name="syntax"></a><span data-ttu-id="a40eb-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a40eb-107">Syntax</span></span>

```xml
<gcConcurrent
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a40eb-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a40eb-108">Attributes and elements</span></span>

<span data-ttu-id="a40eb-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a40eb-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="a40eb-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="a40eb-110">Attributes</span></span>

|<span data-ttu-id="a40eb-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="a40eb-111">Attribute</span></span>|<span data-ttu-id="a40eb-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a40eb-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="a40eb-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="a40eb-113">Required attribute.</span></span><br /><br /><span data-ttu-id="a40eb-114">Especifica si CLR ejecuta la recolección de elementos no utilizados simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="a40eb-114">Specifies whether the runtime runs garbage collection concurrently.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="a40eb-115">atributo habilitado</span><span class="sxs-lookup"><span data-stu-id="a40eb-115">enabled attribute</span></span>

|<span data-ttu-id="a40eb-116">Value</span><span class="sxs-lookup"><span data-stu-id="a40eb-116">Value</span></span>|<span data-ttu-id="a40eb-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="a40eb-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="a40eb-118">No ejecuta la recolección de elementos no utilizados simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="a40eb-118">Doesn't run garbage collection concurrently.</span></span>|
|`true`|<span data-ttu-id="a40eb-119">Ejecuta la recolección de elementos no utilizados simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="a40eb-119">Runs garbage collection concurrently.</span></span> <span data-ttu-id="a40eb-120">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a40eb-120">This is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="a40eb-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a40eb-121">Child elements</span></span>

<span data-ttu-id="a40eb-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a40eb-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a40eb-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a40eb-123">Parent elements</span></span>

|<span data-ttu-id="a40eb-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="a40eb-124">Element</span></span>|<span data-ttu-id="a40eb-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="a40eb-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="a40eb-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a40eb-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="a40eb-127">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="a40eb-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a40eb-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a40eb-128">Remarks</span></span>

<span data-ttu-id="a40eb-129">Antes de .NET Framework 4, la recolección de elementos no utilizados de estación de trabajo admitía la recolección simultánea de elementos no utilizados, que realizaba la recolección de elementos no utilizados en segundo plano en un subproceso independiente.</span><span class="sxs-lookup"><span data-stu-id="a40eb-129">Prior to .NET Framework 4, workstation garbage collection supported concurrent garbage collection, which performed garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="a40eb-130">En .NET Framework 4, la recolección de elementos no utilizados simultánea se reemplazapor por GC en segundo plano, que también realiza la recolección de elementos no utilizados en segundo plano en un subproceso independiente.</span><span class="sxs-lookup"><span data-stu-id="a40eb-130">In .NET Framework 4, concurrent garbage collection was replaced by background GC, which also performs garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="a40eb-131">A partir de .NET Framework 4.5, la recopilación en segundo plano pasó a estar disponible en la recolección de elementos no utilizados del servidor.</span><span class="sxs-lookup"><span data-stu-id="a40eb-131">Starting with .NET Framework 4.5, background collection became available in server garbage collection.</span></span> <span data-ttu-id="a40eb-132">El elemento **gcConcurrent** controla si el tiempo de ejecución realiza la recolección de elementos no utilizados simultánea o en segundo plano, si está disponible o si realiza la recolección de elementos no utilizados en primer plano.</span><span class="sxs-lookup"><span data-stu-id="a40eb-132">The **gcConcurrent** element controls whether the runtime performs either concurrent or background garbage collection, if it's available, or whether it performs garbage collection in the foreground.</span></span>

### <a name="to-disable-background-garbage-collection"></a><span data-ttu-id="a40eb-133">Para deshabilitar la recolección de elementos no utilizados en segundo plano</span><span class="sxs-lookup"><span data-stu-id="a40eb-133">To disable background garbage collection</span></span>

> [!WARNING]
> <span data-ttu-id="a40eb-134">A partir de .NET Framework 4, la recolección simultánea de elementos no utilizados se reemplaza por la recolección de elementos no utilizados en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="a40eb-134">Starting with .NET Framework 4, concurrent garbage collection is replaced by background garbage collection.</span></span> <span data-ttu-id="a40eb-135">Los términos *simultáneos* y *en segundo plano* se usan indistintamente en la documentación de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a40eb-135">The terms *concurrent* and *background* are used interchangeably in the .NET Framework documentation.</span></span> <span data-ttu-id="a40eb-136">Para deshabilitar la recolección de elementos no utilizados en segundo plano, use el elemento **gcConcurrent,** como se describe en este artículo.</span><span class="sxs-lookup"><span data-stu-id="a40eb-136">To disable background garbage collection, use the **gcConcurrent** element, as discussed in this article.</span></span>

<span data-ttu-id="a40eb-137">De forma predeterminada, CLR usa la recolección de elementos no utilizados simultánea, que está optimizada para la latencia.</span><span class="sxs-lookup"><span data-stu-id="a40eb-137">By default, the runtime uses concurrent or background garbage collection, which is optimized for latency.</span></span> <span data-ttu-id="a40eb-138">Si la aplicación requiere mucha interacción por parte del usuario, deje habilitada la recolección de elementos no utilizados simultánea para minimizar el tiempo que la aplicación debe parar para realizar la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="a40eb-138">If your application involves heavy user interaction, leave concurrent garbage collection enabled to minimize the application's pause time to perform garbage collection.</span></span> <span data-ttu-id="a40eb-139">Si establece `enabled` el atributo del elemento `false` **gcConcurrent** en , el tiempo de ejecución utiliza la recolección de elementos no utilizados no simultánea, que está optimizada para el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="a40eb-139">If you set the `enabled` attribute of the **gcConcurrent** element to `false`, the runtime uses non-concurrent garbage collection, which is optimized for throughput.</span></span>

<span data-ttu-id="a40eb-140">El siguiente archivo de configuración deshabilita la recolección de elementos no utilizados en segundo plano:</span><span class="sxs-lookup"><span data-stu-id="a40eb-140">The following configuration file disables background garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="false"/>
   </runtime>
</configuration>
```

<span data-ttu-id="a40eb-141">Si hay un valor **gcConcurrentSetting** en el archivo de configuración del equipo, define el valor predeterminado para todas las aplicaciones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a40eb-141">If there's a **gcConcurrentSetting** setting in the machine configuration file, it defines the default value for all .NET Framework applications.</span></span> <span data-ttu-id="a40eb-142">El archivo de configuración del equipo reemplaza el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a40eb-142">The machine configuration file setting overrides the application configuration file setting.</span></span>

<span data-ttu-id="a40eb-143">Para obtener más información sobre la recolección de elementos no utilizados simultánea y en segundo plano, vea las secciones Recolección de [elementos no utilizados simultánea,](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection) [Recolección](../../../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection)de elementos no utilizados de estación de trabajo en segundo plano y [Recolección](../../../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection) de elementos no utilizados del servidor en segundo plano en el artículo Fundamentos de la [recolección de elementos no utilizados.](../../../../standard/garbage-collection/fundamentals.md)</span><span class="sxs-lookup"><span data-stu-id="a40eb-143">For more information on concurrent and background garbage collection, see the [Concurrent garbage collection](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection), [Background workstation garbage collection](../../../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection), and [Background server garbage collection](../../../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection) sections in the [Fundamentals of Garbage Collection](../../../../standard/garbage-collection/fundamentals.md) article.</span></span>

## <a name="example"></a><span data-ttu-id="a40eb-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a40eb-144">Example</span></span>

<span data-ttu-id="a40eb-145">En el ejemplo siguiente se habilita la recolección de elementos no utilizados en segundo plano:</span><span class="sxs-lookup"><span data-stu-id="a40eb-145">The following example enables background garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="a40eb-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a40eb-146">See also</span></span>

- [<span data-ttu-id="a40eb-147">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="a40eb-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a40eb-148">Esquema del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="a40eb-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="a40eb-149">Fundamentos de la recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="a40eb-149">Fundamentals of Garbage Collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
