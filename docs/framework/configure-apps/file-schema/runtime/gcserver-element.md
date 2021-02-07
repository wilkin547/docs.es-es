---
description: 'Más información acerca de: <gcServer> elemento'
title: Elemento gcServer
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcServer
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcServer
helpviewer_keywords:
- gcServer element
- <gcServer> element
ms.assetid: 8d25b80e-2581-4803-bd87-a59528e3cb03
ms.openlocfilehash: bed347699786682421292392a8d2449b7aac61d0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754542"
---
# <a name="gcserver-element"></a><span data-ttu-id="b7386-103">Elemento \<gcServer></span><span class="sxs-lookup"><span data-stu-id="b7386-103">\<gcServer> element</span></span>

<span data-ttu-id="b7386-104">Especifica si Common Language Runtime ejecuta la recopilación de elementos no utilizados de servidor.</span><span class="sxs-lookup"><span data-stu-id="b7386-104">Specifies whether the common language runtime runs server garbage collection.</span></span>

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<runtime>](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<gcServer>

## <a name="syntax"></a><span data-ttu-id="b7386-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7386-105">Syntax</span></span>

```xml
<gcServer
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b7386-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b7386-106">Attributes and elements</span></span>

<span data-ttu-id="b7386-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b7386-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="b7386-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="b7386-108">Attributes</span></span>

|<span data-ttu-id="b7386-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="b7386-109">Attribute</span></span>|<span data-ttu-id="b7386-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7386-110">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="b7386-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="b7386-111">Required attribute.</span></span><br /><br /><span data-ttu-id="b7386-112">Especifica si Common Language Runtime ejecuta la recolección de elementos no utilizados de servidor.</span><span class="sxs-lookup"><span data-stu-id="b7386-112">Specifies whether the runtime runs server garbage collection.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="b7386-113">atributo Enabled</span><span class="sxs-lookup"><span data-stu-id="b7386-113">enabled attribute</span></span>

|<span data-ttu-id="b7386-114">Value</span><span class="sxs-lookup"><span data-stu-id="b7386-114">Value</span></span>|<span data-ttu-id="b7386-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7386-115">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="b7386-116">No ejecuta la recolección de elementos no utilizados de servidor.</span><span class="sxs-lookup"><span data-stu-id="b7386-116">Does not run server garbage collection.</span></span> <span data-ttu-id="b7386-117">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b7386-117">This is the default.</span></span>|
|`true`|<span data-ttu-id="b7386-118">Ejecuta la recolección de elementos no utilizados de servidor.</span><span class="sxs-lookup"><span data-stu-id="b7386-118">Runs server garbage collection.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="b7386-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b7386-119">Child elements</span></span>

<span data-ttu-id="b7386-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b7386-120">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b7386-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b7386-121">Parent elements</span></span>

|<span data-ttu-id="b7386-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="b7386-122">Element</span></span>|<span data-ttu-id="b7386-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7386-123">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="b7386-124">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b7386-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="b7386-125">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b7386-125">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b7386-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b7386-126">Remarks</span></span>

<span data-ttu-id="b7386-127">Common Language Runtime (CLR) admite dos tipos de recolección de elementos no utilizados: de estación de trabajo, que está disponible en todos los sistemas, y de servidor, que está disponible en sistemas multiprocesador.</span><span class="sxs-lookup"><span data-stu-id="b7386-127">The common language runtime (CLR) supports two types of garbage collection: workstation garbage collection, which is available on all systems, and server garbage collection, which is available on multiprocessor systems.</span></span> <span data-ttu-id="b7386-128">Use el elemento **gcServer** para controlar el tipo de recolección de elementos no utilizados que CLR realiza.</span><span class="sxs-lookup"><span data-stu-id="b7386-128">Use the **gcServer** element to control the type of garbage collection the CLR performs.</span></span> <span data-ttu-id="b7386-129">Use la propiedad <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> para determinar si la recolección de elementos no utilizados de servidor está habilitada.</span><span class="sxs-lookup"><span data-stu-id="b7386-129">Use the <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> property to determine if server garbage collection is enabled.</span></span>

<span data-ttu-id="b7386-130">Para equipos con un solo procesador, la recolección de elementos no utilizados de estación de trabajo predeterminada será la opción más rápida.</span><span class="sxs-lookup"><span data-stu-id="b7386-130">For single-processor computers, the default workstation garbage collection should be the fastest option.</span></span> <span data-ttu-id="b7386-131">En los equipos con dos procesadores se puede usar la opción de estación de trabajo o de servidor.</span><span class="sxs-lookup"><span data-stu-id="b7386-131">Either workstation or server can be used for two-processor computers.</span></span> <span data-ttu-id="b7386-132">La recolección de elementos no utilizados de servidor será la opción más rápida si hay más de dos procesadores.</span><span class="sxs-lookup"><span data-stu-id="b7386-132">Server garbage collection should be the fastest option for more than two processors.</span></span> <span data-ttu-id="b7386-133">Normalmente, los sistemas de servidor multiprocesador deshabilitan el GC del servidor y usan la instancia de GC de la estación de trabajo cuando muchas instancias de una aplicación de servidor se ejecutan en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="b7386-133">Most commonly, multiprocessor server systems disable server GC and use workstation GC instead when many instances of a server app run on the same machine.</span></span>

<span data-ttu-id="b7386-134">Este elemento se puede usar solo en el archivo de configuración de la aplicación; se omite si se encuentra en el archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="b7386-134">This element can be used only in the application configuration file; it is ignored if it is in the machine configuration file.</span></span>

> [!NOTE]
> <span data-ttu-id="b7386-135">En .NET Framework 4 y versiones anteriores, la recolección de elementos no utilizados simultánea no está disponible si la recolección de elementos no utilizados de servidor está habilitada.</span><span class="sxs-lookup"><span data-stu-id="b7386-135">In the .NET Framework 4 and earlier versions, concurrent garbage collection is not available when server garbage collection is enabled.</span></span> <span data-ttu-id="b7386-136">A partir de la .NET Framework 4,5, la recolección de elementos no utilizados de servidor es simultánea.</span><span class="sxs-lookup"><span data-stu-id="b7386-136">Starting with the .NET Framework 4.5, server garbage collection is concurrent.</span></span> <span data-ttu-id="b7386-137">Para usar la recolección de elementos no utilizados de servidor no simultánea, establezca el elemento **gcServer** en `true` y el [elemento gcConcurrent](gcconcurrent-element.md) en `false` .</span><span class="sxs-lookup"><span data-stu-id="b7386-137">To use non-concurrent server garbage collection, set the **gcServer** element to `true` and the [gcConcurrent element](gcconcurrent-element.md) to `false`.</span></span>

<span data-ttu-id="b7386-138">A partir de .NET Framework 4.6.2, también puede usar los siguientes elementos para configurar el GC del servidor:</span><span class="sxs-lookup"><span data-stu-id="b7386-138">Starting with .NET Framework 4.6.2, you can also use the following elements to configure server GC:</span></span>

- <span data-ttu-id="b7386-139">[GCNoAffinitize](gcnoaffinitize-element.md), que especifica si existe una afinidad entre los procesadores y los montones de GC del servidor.</span><span class="sxs-lookup"><span data-stu-id="b7386-139">[GCNoAffinitize](gcnoaffinitize-element.md), which specifies whether there is an affinity between server GC heaps and processors.</span></span> <span data-ttu-id="b7386-140">De forma predeterminada, hay un montón de GC de servidor para cada procesador.</span><span class="sxs-lookup"><span data-stu-id="b7386-140">By default, there is one server GC heap for each processor.</span></span>

- <span data-ttu-id="b7386-141">[GCHeapCount](gcheapcount-element.md), que limita el número de montones utilizados por un proceso.</span><span class="sxs-lookup"><span data-stu-id="b7386-141">[GCHeapCount](gcheapcount-element.md), which limits the number of heaps used by a process.</span></span>

- <span data-ttu-id="b7386-142">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md), que define la afinidad entre los montones de GC del servidor disponibles y los procesadores individuales.</span><span class="sxs-lookup"><span data-stu-id="b7386-142">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md), which defines the affinity between the available server GC heaps and individual processors.</span></span>

## <a name="example"></a><span data-ttu-id="b7386-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b7386-143">Example</span></span>

<span data-ttu-id="b7386-144">En el ejemplo siguiente se habilita la recolección de elementos no utilizados de servidor:</span><span class="sxs-lookup"><span data-stu-id="b7386-144">The following example enables server garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="b7386-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7386-145">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="b7386-146">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="b7386-146">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b7386-147">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="b7386-147">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="b7386-148">Para deshabilitar la recolección de elementos no utilizados simultánea</span><span class="sxs-lookup"><span data-stu-id="b7386-148">To disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
