---
description: 'Más información acerca de: <gcConcurrent> elemento'
title: Elemento gcConcurrent
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
ms.openlocfilehash: dff8b073977c007a132cfbd685724a02ba37684b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787011"
---
# <a name="gcconcurrent-element"></a><span data-ttu-id="a2b37-103">Elemento \<gcConcurrent></span><span class="sxs-lookup"><span data-stu-id="a2b37-103">\<gcConcurrent> element</span></span>

<span data-ttu-id="a2b37-104">Especifica si Common Language Runtime ejecuta la recolección de elementos no utilizados en un subproceso independiente.</span><span class="sxs-lookup"><span data-stu-id="a2b37-104">Specifies whether the common language runtime runs garbage collection on a separate thread.</span></span>

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<runtime>](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<gcConcurrent>

## <a name="syntax"></a><span data-ttu-id="a2b37-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a2b37-105">Syntax</span></span>

```xml
<gcConcurrent
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a2b37-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a2b37-106">Attributes and elements</span></span>

<span data-ttu-id="a2b37-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a2b37-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="a2b37-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="a2b37-108">Attributes</span></span>

|<span data-ttu-id="a2b37-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="a2b37-109">Attribute</span></span>|<span data-ttu-id="a2b37-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="a2b37-110">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="a2b37-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="a2b37-111">Required attribute.</span></span><br /><br /><span data-ttu-id="a2b37-112">Especifica si CLR ejecuta la recolección de elementos no utilizados simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="a2b37-112">Specifies whether the runtime runs garbage collection concurrently.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="a2b37-113">atributo Enabled</span><span class="sxs-lookup"><span data-stu-id="a2b37-113">enabled attribute</span></span>

|<span data-ttu-id="a2b37-114">Value</span><span class="sxs-lookup"><span data-stu-id="a2b37-114">Value</span></span>|<span data-ttu-id="a2b37-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="a2b37-115">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="a2b37-116">No ejecuta la recolección de elementos no utilizados simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="a2b37-116">Doesn't run garbage collection concurrently.</span></span>|
|`true`|<span data-ttu-id="a2b37-117">Ejecuta la recolección de elementos no utilizados simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="a2b37-117">Runs garbage collection concurrently.</span></span> <span data-ttu-id="a2b37-118">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a2b37-118">This is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="a2b37-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a2b37-119">Child elements</span></span>

<span data-ttu-id="a2b37-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a2b37-120">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a2b37-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a2b37-121">Parent elements</span></span>

|<span data-ttu-id="a2b37-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="a2b37-122">Element</span></span>|<span data-ttu-id="a2b37-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="a2b37-123">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="a2b37-124">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a2b37-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="a2b37-125">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="a2b37-125">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a2b37-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a2b37-126">Remarks</span></span>

<span data-ttu-id="a2b37-127">Antes de .NET Framework 4, la recolección de elementos no utilizados de estación de trabajo admitía la recolección de elementos no utilizados simultánea, que realizaba la recolección de elementos no utilizados en segundo plano en otro subproceso.</span><span class="sxs-lookup"><span data-stu-id="a2b37-127">Prior to .NET Framework 4, workstation garbage collection supported concurrent garbage collection, which performed garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="a2b37-128">En .NET Framework 4, la recolección de elementos no utilizados simultánea se ha reemplazado por GC de fondo, que también realiza la recolección de elementos no utilizados en segundo plano en un subproceso independiente.</span><span class="sxs-lookup"><span data-stu-id="a2b37-128">In .NET Framework 4, concurrent garbage collection was replaced by background GC, which also performs garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="a2b37-129">A partir de .NET Framework 4,5, la recolección en segundo plano estuvo disponible en la recolección de elementos no utilizados de servidor.</span><span class="sxs-lookup"><span data-stu-id="a2b37-129">Starting with .NET Framework 4.5, background collection became available in server garbage collection.</span></span> <span data-ttu-id="a2b37-130">El elemento **gcConcurrent** controla si el motor en tiempo de ejecución realiza la recolección de elementos no utilizados simultánea o en segundo plano, si está disponible, o si realiza la recolección de elementos no utilizados en primer plano.</span><span class="sxs-lookup"><span data-stu-id="a2b37-130">The **gcConcurrent** element controls whether the runtime performs either concurrent or background garbage collection, if it's available, or whether it performs garbage collection in the foreground.</span></span>

### <a name="to-disable-background-garbage-collection"></a><span data-ttu-id="a2b37-131">Para deshabilitar la recolección de elementos no utilizados en segundo plano</span><span class="sxs-lookup"><span data-stu-id="a2b37-131">To disable background garbage collection</span></span>

> [!WARNING]
> <span data-ttu-id="a2b37-132">A partir de .NET Framework 4, la recolección de elementos no utilizados en segundo plano reemplaza la recolección simultánea de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="a2b37-132">Starting with .NET Framework 4, concurrent garbage collection is replaced by background garbage collection.</span></span> <span data-ttu-id="a2b37-133">Los términos *simultáneos* y de *fondo* se usan indistintamente en la documentación de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a2b37-133">The terms *concurrent* and *background* are used interchangeably in the .NET Framework documentation.</span></span> <span data-ttu-id="a2b37-134">Para deshabilitar la recolección de elementos no utilizados en segundo plano, use el elemento **gcConcurrent** , como se describe en este artículo.</span><span class="sxs-lookup"><span data-stu-id="a2b37-134">To disable background garbage collection, use the **gcConcurrent** element, as discussed in this article.</span></span>

<span data-ttu-id="a2b37-135">De forma predeterminada, CLR usa la recolección de elementos no utilizados simultánea, que está optimizada para la latencia.</span><span class="sxs-lookup"><span data-stu-id="a2b37-135">By default, the runtime uses concurrent or background garbage collection, which is optimized for latency.</span></span> <span data-ttu-id="a2b37-136">Si la aplicación requiere mucha interacción por parte del usuario, deje habilitada la recolección de elementos no utilizados simultánea para minimizar el tiempo que la aplicación debe parar para realizar la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="a2b37-136">If your application involves heavy user interaction, leave concurrent garbage collection enabled to minimize the application's pause time to perform garbage collection.</span></span> <span data-ttu-id="a2b37-137">Si establece el `enabled` atributo del elemento **gcConcurrent** en `false` , el Runtime usa la recolección de elementos no utilizados no simultánea, que está optimizada para el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="a2b37-137">If you set the `enabled` attribute of the **gcConcurrent** element to `false`, the runtime uses non-concurrent garbage collection, which is optimized for throughput.</span></span>

<span data-ttu-id="a2b37-138">El siguiente archivo de configuración deshabilita la recolección de elementos no utilizados en segundo plano:</span><span class="sxs-lookup"><span data-stu-id="a2b37-138">The following configuration file disables background garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="false"/>
   </runtime>
</configuration>
```

<span data-ttu-id="a2b37-139">Si hay un valor de **gcConcurrentSetting** en el archivo de configuración del equipo, define el valor predeterminado para todas las aplicaciones .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a2b37-139">If there's a **gcConcurrentSetting** setting in the machine configuration file, it defines the default value for all .NET Framework applications.</span></span> <span data-ttu-id="a2b37-140">El archivo de configuración del equipo reemplaza el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a2b37-140">The machine configuration file setting overrides the application configuration file setting.</span></span>

<span data-ttu-id="a2b37-141">Para obtener más información sobre la recolección de elementos no utilizados simultánea y en segundo plano, consulte recolección de [elementos no utilizados en segundo plano](../../../../standard/garbage-collection/background-gc.md).</span><span class="sxs-lookup"><span data-stu-id="a2b37-141">For more information on concurrent and background garbage collection, see [Background garbage collection](../../../../standard/garbage-collection/background-gc.md).</span></span>

## <a name="example"></a><span data-ttu-id="a2b37-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a2b37-142">Example</span></span>

<span data-ttu-id="a2b37-143">En el ejemplo siguiente se habilita la recolección de elementos no utilizados en segundo plano:</span><span class="sxs-lookup"><span data-stu-id="a2b37-143">The following example enables background garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="a2b37-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2b37-144">See also</span></span>

- [<span data-ttu-id="a2b37-145">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="a2b37-145">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a2b37-146">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="a2b37-146">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="a2b37-147">Fundamentos de la recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="a2b37-147">Fundamentals of Garbage Collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
