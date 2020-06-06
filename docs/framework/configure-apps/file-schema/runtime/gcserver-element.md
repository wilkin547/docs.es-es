---
title: Elemento gcServer
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcServer
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcServer
helpviewer_keywords:
- gcServer element
- <gcServer> element
ms.assetid: 8d25b80e-2581-4803-bd87-a59528e3cb03
ms.openlocfilehash: 8eab5e36bab90510aff4f1a3e15328197ac59ed7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73968947"
---
# <a name="gcserver-element"></a><span data-ttu-id="58240-102">Elemento \<gcServer></span><span class="sxs-lookup"><span data-stu-id="58240-102">\<gcServer> element</span></span>

<span data-ttu-id="58240-103">Especifica si Common Language Runtime ejecuta la recopilación de elementos no utilizados de servidor.</span><span class="sxs-lookup"><span data-stu-id="58240-103">Specifies whether the common language runtime runs server garbage collection.</span></span>

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<runtime>](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<gcServer>

## <a name="syntax"></a><span data-ttu-id="58240-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="58240-104">Syntax</span></span>

```xml
<gcServer
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="58240-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="58240-105">Attributes and elements</span></span>

<span data-ttu-id="58240-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="58240-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="58240-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="58240-107">Attributes</span></span>

|<span data-ttu-id="58240-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="58240-108">Attribute</span></span>|<span data-ttu-id="58240-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="58240-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="58240-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="58240-110">Required attribute.</span></span><br /><br /><span data-ttu-id="58240-111">Especifica si Common Language Runtime ejecuta la recolección de elementos no utilizados de servidor.</span><span class="sxs-lookup"><span data-stu-id="58240-111">Specifies whether the runtime runs server garbage collection.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="58240-112">atributo Enabled</span><span class="sxs-lookup"><span data-stu-id="58240-112">enabled attribute</span></span>

|<span data-ttu-id="58240-113">Value</span><span class="sxs-lookup"><span data-stu-id="58240-113">Value</span></span>|<span data-ttu-id="58240-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="58240-114">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="58240-115">No ejecuta la recolección de elementos no utilizados de servidor.</span><span class="sxs-lookup"><span data-stu-id="58240-115">Does not run server garbage collection.</span></span> <span data-ttu-id="58240-116">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="58240-116">This is the default.</span></span>|
|`true`|<span data-ttu-id="58240-117">Ejecuta la recolección de elementos no utilizados de servidor.</span><span class="sxs-lookup"><span data-stu-id="58240-117">Runs server garbage collection.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="58240-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="58240-118">Child elements</span></span>

<span data-ttu-id="58240-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="58240-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="58240-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="58240-120">Parent elements</span></span>

|<span data-ttu-id="58240-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="58240-121">Element</span></span>|<span data-ttu-id="58240-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="58240-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="58240-123">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="58240-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="58240-124">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="58240-124">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="58240-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="58240-125">Remarks</span></span>

<span data-ttu-id="58240-126">Common Language Runtime (CLR) admite dos tipos de recolección de elementos no utilizados: de estación de trabajo, que está disponible en todos los sistemas, y de servidor, que está disponible en sistemas multiprocesador.</span><span class="sxs-lookup"><span data-stu-id="58240-126">The common language runtime (CLR) supports two types of garbage collection: workstation garbage collection, which is available on all systems, and server garbage collection, which is available on multiprocessor systems.</span></span> <span data-ttu-id="58240-127">Use el elemento **gcServer** para controlar el tipo de recolección de elementos no utilizados que CLR realiza.</span><span class="sxs-lookup"><span data-stu-id="58240-127">Use the **gcServer** element to control the type of garbage collection the CLR performs.</span></span> <span data-ttu-id="58240-128">Use la propiedad <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> para determinar si la recolección de elementos no utilizados de servidor está habilitada.</span><span class="sxs-lookup"><span data-stu-id="58240-128">Use the <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> property to determine if server garbage collection is enabled.</span></span>

<span data-ttu-id="58240-129">Para equipos con un solo procesador, la recolección de elementos no utilizados de estación de trabajo predeterminada será la opción más rápida.</span><span class="sxs-lookup"><span data-stu-id="58240-129">For single-processor computers, the default workstation garbage collection should be the fastest option.</span></span> <span data-ttu-id="58240-130">En los equipos con dos procesadores se puede usar la opción de estación de trabajo o de servidor.</span><span class="sxs-lookup"><span data-stu-id="58240-130">Either workstation or server can be used for two-processor computers.</span></span> <span data-ttu-id="58240-131">La recolección de elementos no utilizados de servidor será la opción más rápida si hay más de dos procesadores.</span><span class="sxs-lookup"><span data-stu-id="58240-131">Server garbage collection should be the fastest option for more than two processors.</span></span> <span data-ttu-id="58240-132">Normalmente, los sistemas de servidor multiprocesador deshabilitan el GC del servidor y usan la instancia de GC de la estación de trabajo cuando muchas instancias de una aplicación de servidor se ejecutan en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="58240-132">Most commonly, multiprocessor server systems disable server GC and use workstation GC instead when many instances of a server app run on the same machine.</span></span>

<span data-ttu-id="58240-133">Este elemento se puede usar solo en el archivo de configuración de la aplicación; se omite si se encuentra en el archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="58240-133">This element can be used only in the application configuration file; it is ignored if it is in the machine configuration file.</span></span>

> [!NOTE]
> <span data-ttu-id="58240-134">En .NET Framework 4 y versiones anteriores, la recolección de elementos no utilizados simultánea no está disponible si la recolección de elementos no utilizados de servidor está habilitada.</span><span class="sxs-lookup"><span data-stu-id="58240-134">In the .NET Framework 4 and earlier versions, concurrent garbage collection is not available when server garbage collection is enabled.</span></span> <span data-ttu-id="58240-135">A partir de la .NET Framework 4,5, la recolección de elementos no utilizados de servidor es simultánea.</span><span class="sxs-lookup"><span data-stu-id="58240-135">Starting with the .NET Framework 4.5, server garbage collection is concurrent.</span></span> <span data-ttu-id="58240-136">Para usar la recolección de elementos no utilizados de servidor no simultánea, establezca el elemento **gcServer** en `true` y el [elemento gcConcurrent](gcconcurrent-element.md) en `false` .</span><span class="sxs-lookup"><span data-stu-id="58240-136">To use non-concurrent server garbage collection, set the **gcServer** element to `true` and the [gcConcurrent element](gcconcurrent-element.md) to `false`.</span></span>

<span data-ttu-id="58240-137">A partir de .NET Framework 4.6.2, también puede usar los siguientes elementos para configurar el GC del servidor:</span><span class="sxs-lookup"><span data-stu-id="58240-137">Starting with .NET Framework 4.6.2, you can also use the following elements to configure server GC:</span></span>

- <span data-ttu-id="58240-138">[GCNoAffinitize](gcnoaffinitize-element.md), que especifica si existe una afinidad entre los procesadores y los montones de GC del servidor.</span><span class="sxs-lookup"><span data-stu-id="58240-138">[GCNoAffinitize](gcnoaffinitize-element.md), which specifies whether there is an affinity between server GC heaps and processors.</span></span> <span data-ttu-id="58240-139">De forma predeterminada, hay un montón de GC de servidor para cada procesador.</span><span class="sxs-lookup"><span data-stu-id="58240-139">By default, there is one server GC heap for each processor.</span></span>

- <span data-ttu-id="58240-140">[GCHeapCount](gcheapcount-element.md), que limita el número de montones utilizados por un proceso.</span><span class="sxs-lookup"><span data-stu-id="58240-140">[GCHeapCount](gcheapcount-element.md), which limits the number of heaps used by a process.</span></span>

- <span data-ttu-id="58240-141">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md), que define la afinidad entre los montones de GC del servidor disponibles y los procesadores individuales.</span><span class="sxs-lookup"><span data-stu-id="58240-141">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md), which defines the affinity between the available server GC heaps and individual processors.</span></span>

## <a name="example"></a><span data-ttu-id="58240-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="58240-142">Example</span></span>

<span data-ttu-id="58240-143">En el ejemplo siguiente se habilita la recolección de elementos no utilizados de servidor:</span><span class="sxs-lookup"><span data-stu-id="58240-143">The following example enables server garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="58240-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="58240-144">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="58240-145">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="58240-145">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="58240-146">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="58240-146">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="58240-147">Para deshabilitar la recolección de elementos no utilizados simultánea</span><span class="sxs-lookup"><span data-stu-id="58240-147">To disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
