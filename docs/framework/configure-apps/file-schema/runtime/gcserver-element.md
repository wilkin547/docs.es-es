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
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968947"
---
# <a name="gcserver-element"></a><span data-ttu-id="7c543-102">\<elemento > gcServer</span><span class="sxs-lookup"><span data-stu-id="7c543-102">\<gcServer> element</span></span>

<span data-ttu-id="7c543-103">Especifica si Common Language Runtime ejecuta la recopilación de elementos no utilizados de servidor.</span><span class="sxs-lookup"><span data-stu-id="7c543-103">Specifies whether the common language runtime runs server garbage collection.</span></span>

<span data-ttu-id="7c543-104">[\<configuration>](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7c543-104">[\<configuration>](../configuration-element.md)</span></span>\
<span data-ttu-id="7c543-105">&nbsp;&nbsp;[\<en tiempo de ejecución >](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="7c543-105">&nbsp;&nbsp;[\<runtime>](runtime-element.md)</span></span>\
<span data-ttu-id="7c543-106">&nbsp;&nbsp;&nbsp;&nbsp;\<gcServer ></span><span class="sxs-lookup"><span data-stu-id="7c543-106">&nbsp;&nbsp;&nbsp;&nbsp;\<gcServer></span></span>

## <a name="syntax"></a><span data-ttu-id="7c543-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7c543-107">Syntax</span></span>

```xml
<gcServer
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7c543-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7c543-108">Attributes and elements</span></span>

<span data-ttu-id="7c543-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7c543-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="7c543-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="7c543-110">Attributes</span></span>

|<span data-ttu-id="7c543-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="7c543-111">Attribute</span></span>|<span data-ttu-id="7c543-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="7c543-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="7c543-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="7c543-113">Required attribute.</span></span><br /><br /><span data-ttu-id="7c543-114">Especifica si Common Language Runtime ejecuta la recolección de elementos no utilizados de servidor.</span><span class="sxs-lookup"><span data-stu-id="7c543-114">Specifies whether the runtime runs server garbage collection.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="7c543-115">atributo Enabled</span><span class="sxs-lookup"><span data-stu-id="7c543-115">enabled attribute</span></span>

|<span data-ttu-id="7c543-116">Valor</span><span class="sxs-lookup"><span data-stu-id="7c543-116">Value</span></span>|<span data-ttu-id="7c543-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="7c543-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="7c543-118">No ejecuta la recolección de elementos no utilizados de servidor.</span><span class="sxs-lookup"><span data-stu-id="7c543-118">Does not run server garbage collection.</span></span> <span data-ttu-id="7c543-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="7c543-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="7c543-120">Ejecuta la recolección de elementos no utilizados de servidor.</span><span class="sxs-lookup"><span data-stu-id="7c543-120">Runs server garbage collection.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="7c543-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7c543-121">Child elements</span></span>

<span data-ttu-id="7c543-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7c543-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7c543-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7c543-123">Parent elements</span></span>

|<span data-ttu-id="7c543-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="7c543-124">Element</span></span>|<span data-ttu-id="7c543-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="7c543-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="7c543-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7c543-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="7c543-127">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="7c543-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7c543-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7c543-128">Remarks</span></span>

<span data-ttu-id="7c543-129">Common Language Runtime (CLR) admite dos tipos de recolección de elementos no utilizados: de estación de trabajo, que está disponible en todos los sistemas, y de servidor, que está disponible en sistemas multiprocesador.</span><span class="sxs-lookup"><span data-stu-id="7c543-129">The common language runtime (CLR) supports two types of garbage collection: workstation garbage collection, which is available on all systems, and server garbage collection, which is available on multiprocessor systems.</span></span> <span data-ttu-id="7c543-130">Use el elemento **gcServer** para controlar el tipo de recolección de elementos no utilizados que CLR realiza.</span><span class="sxs-lookup"><span data-stu-id="7c543-130">Use the **gcServer** element to control the type of garbage collection the CLR performs.</span></span> <span data-ttu-id="7c543-131">Use la propiedad <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> para determinar si la recolección de elementos no utilizados de servidor está habilitada.</span><span class="sxs-lookup"><span data-stu-id="7c543-131">Use the <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> property to determine if server garbage collection is enabled.</span></span>

<span data-ttu-id="7c543-132">Para equipos con un solo procesador, la recolección de elementos no utilizados de estación de trabajo predeterminada será la opción más rápida.</span><span class="sxs-lookup"><span data-stu-id="7c543-132">For single-processor computers, the default workstation garbage collection should be the fastest option.</span></span> <span data-ttu-id="7c543-133">En los equipos con dos procesadores se puede usar la opción de estación de trabajo o de servidor.</span><span class="sxs-lookup"><span data-stu-id="7c543-133">Either workstation or server can be used for two-processor computers.</span></span> <span data-ttu-id="7c543-134">La recolección de elementos no utilizados de servidor será la opción más rápida si hay más de dos procesadores.</span><span class="sxs-lookup"><span data-stu-id="7c543-134">Server garbage collection should be the fastest option for more than two processors.</span></span> <span data-ttu-id="7c543-135">Normalmente, los sistemas de servidor multiprocesador deshabilitan el GC del servidor y usan la instancia de GC de la estación de trabajo cuando muchas instancias de una aplicación de servidor se ejecutan en el mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="7c543-135">Most commonly, multiprocessor server systems disable server GC and use workstation GC instead when many instances of a server app run on the same machine.</span></span>

<span data-ttu-id="7c543-136">Este elemento se puede usar solo en el archivo de configuración de la aplicación; se omite si se encuentra en el archivo de configuración del equipo.</span><span class="sxs-lookup"><span data-stu-id="7c543-136">This element can be used only in the application configuration file; it is ignored if it is in the machine configuration file.</span></span>

> [!NOTE]
> <span data-ttu-id="7c543-137">En .NET Framework 4 y versiones anteriores, la recolección de elementos no utilizados simultánea no está disponible si la recolección de elementos no utilizados de servidor está habilitada.</span><span class="sxs-lookup"><span data-stu-id="7c543-137">In the .NET Framework 4 and earlier versions, concurrent garbage collection is not available when server garbage collection is enabled.</span></span> <span data-ttu-id="7c543-138">A partir de la .NET Framework 4,5, la recolección de elementos no utilizados de servidor es simultánea.</span><span class="sxs-lookup"><span data-stu-id="7c543-138">Starting with the .NET Framework 4.5, server garbage collection is concurrent.</span></span> <span data-ttu-id="7c543-139">Para usar la recolección de elementos no utilizados de servidor no simultánea, establezca el elemento **gcServer** en `true` y el [elemento gcConcurrent](gcconcurrent-element.md) en `false`.</span><span class="sxs-lookup"><span data-stu-id="7c543-139">To use non-concurrent server garbage collection, set the **gcServer** element to `true` and the [gcConcurrent element](gcconcurrent-element.md) to `false`.</span></span>

<span data-ttu-id="7c543-140">A partir de .NET Framework 4.6.2, también puede usar los siguientes elementos para configurar el GC del servidor:</span><span class="sxs-lookup"><span data-stu-id="7c543-140">Starting with .NET Framework 4.6.2, you can also use the following elements to configure server GC:</span></span>

- <span data-ttu-id="7c543-141">[GCNoAffinitize](gcnoaffinitize-element.md), que especifica si existe una afinidad entre los procesadores y los montones de GC del servidor.</span><span class="sxs-lookup"><span data-stu-id="7c543-141">[GCNoAffinitize](gcnoaffinitize-element.md), which specifies whether there is an affinity between server GC heaps and processors.</span></span> <span data-ttu-id="7c543-142">De forma predeterminada, hay un montón de GC de servidor para cada procesador.</span><span class="sxs-lookup"><span data-stu-id="7c543-142">By default, there is one server GC heap for each processor.</span></span>

- <span data-ttu-id="7c543-143">[GCHeapCount](gcheapcount-element.md), que limita el número de montones utilizados por un proceso.</span><span class="sxs-lookup"><span data-stu-id="7c543-143">[GCHeapCount](gcheapcount-element.md), which limits the number of heaps used by a process.</span></span>

- <span data-ttu-id="7c543-144">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md), que define la afinidad entre los montones de GC del servidor disponibles y los procesadores individuales.</span><span class="sxs-lookup"><span data-stu-id="7c543-144">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md), which defines the affinity between the available server GC heaps and individual processors.</span></span>

## <a name="example"></a><span data-ttu-id="7c543-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7c543-145">Example</span></span>

<span data-ttu-id="7c543-146">En el ejemplo siguiente se habilita la recolección de elementos no utilizados de servidor:</span><span class="sxs-lookup"><span data-stu-id="7c543-146">The following example enables server garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="7c543-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c543-147">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="7c543-148">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="7c543-148">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="7c543-149">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="7c543-149">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="7c543-150">Para deshabilitar la recolección de elementos no utilizados simultánea</span><span class="sxs-lookup"><span data-stu-id="7c543-150">To disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
