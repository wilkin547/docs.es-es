---
title: Elemento GCNoAffinitize
ms.date: 11/08/2019
helpviewer_keywords:
- gcNoAffinitize element
- <gcNoAffinitize> element
ms.openlocfilehash: 4031ff19131c905072696837d1622dbb6e54ae61
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73978418"
---
# <a name="gcnoaffinitize-element"></a><span data-ttu-id="14d7f-102">\<elemento > GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="14d7f-102">\<GCNoAffinitize> element</span></span>

<span data-ttu-id="14d7f-103">Especifica si establecer afinidad entre o no los subprocesos de GC del servidor con CPU.</span><span class="sxs-lookup"><span data-stu-id="14d7f-103">Specifies whether or not to affinitize server GC threads with CPUs.</span></span>

<span data-ttu-id="14d7f-104">\<Configuración > </span><span class="sxs-lookup"><span data-stu-id="14d7f-104">\<configuration></span></span>\
<span data-ttu-id="14d7f-105">&nbsp;&nbsp;\<Runtime > </span><span class="sxs-lookup"><span data-stu-id="14d7f-105">&nbsp;&nbsp;\<runtime></span></span>\
<span data-ttu-id="14d7f-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCNoAffinitize ></span><span class="sxs-lookup"><span data-stu-id="14d7f-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCNoAffinitize></span></span>

## <a name="syntax"></a><span data-ttu-id="14d7f-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="14d7f-107">Syntax</span></span>

```xml
<GCNoAffinitize
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="14d7f-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="14d7f-108">Attributes and elements</span></span>

<span data-ttu-id="14d7f-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="14d7f-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="14d7f-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="14d7f-110">Attributes</span></span>

|<span data-ttu-id="14d7f-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="14d7f-111">Attribute</span></span>|<span data-ttu-id="14d7f-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="14d7f-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="14d7f-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="14d7f-113">Required attribute.</span></span><br /><br /><span data-ttu-id="14d7f-114">Especifica si los subprocesos o montones de GC del servidor se afinidad con con los procesadores disponibles en la máquina.</span><span class="sxs-lookup"><span data-stu-id="14d7f-114">Specifies whether server GC threads/heaps are affinitized with the processors available on the machine.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="14d7f-115">atributo Enabled</span><span class="sxs-lookup"><span data-stu-id="14d7f-115">enabled attribute</span></span>

|<span data-ttu-id="14d7f-116">Valor</span><span class="sxs-lookup"><span data-stu-id="14d7f-116">Value</span></span>|<span data-ttu-id="14d7f-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="14d7f-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="14d7f-118">Subprocesos de GC del servidor establece con CPU.</span><span class="sxs-lookup"><span data-stu-id="14d7f-118">Affinitizes server GC threads with CPUs.</span></span> <span data-ttu-id="14d7f-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="14d7f-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="14d7f-120">No establecer afinidad entre los subprocesos de GC de servidor con CPU.</span><span class="sxs-lookup"><span data-stu-id="14d7f-120">Does not affinitize server GC threads with CPUs.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="14d7f-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="14d7f-121">Child elements</span></span>

<span data-ttu-id="14d7f-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="14d7f-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="14d7f-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="14d7f-123">Parent elements</span></span>

|<span data-ttu-id="14d7f-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="14d7f-124">Element</span></span>|<span data-ttu-id="14d7f-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="14d7f-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="14d7f-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="14d7f-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="14d7f-127">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="14d7f-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="14d7f-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="14d7f-128">Remarks</span></span>

<span data-ttu-id="14d7f-129">De forma predeterminada, los subprocesos de GC de servidor son afinidad cons con sus respectivas CPU.</span><span class="sxs-lookup"><span data-stu-id="14d7f-129">By default, server GC threads are hard-affinitized with their respective CPUs.</span></span> <span data-ttu-id="14d7f-130">Cada uno de los procesadores disponibles del sistema tiene su propio subproceso y montón de GC.</span><span class="sxs-lookup"><span data-stu-id="14d7f-130">Each of the system's available processors has its own GC heap and thread.</span></span> <span data-ttu-id="14d7f-131">Esta suele ser la configuración preferida, ya que optimiza el uso de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="14d7f-131">This is typically the preferred setting since it optimizes cache usage.</span></span> <span data-ttu-id="14d7f-132">A partir de .NET Framework 4.6.2, al establecer el atributo de `enabled` del elemento **GCNoAffinitize** en `false`, puede especificar que los subprocesos de GC del servidor y las CPU no estén estrechamente acoplados.</span><span class="sxs-lookup"><span data-stu-id="14d7f-132">Starting with .NET Framework 4.6.2, by setting the **GCNoAffinitize** element's `enabled` attribute to `false`, you can specify that server GC threads and CPUs should not be tightly coupled.</span></span>

<span data-ttu-id="14d7f-133">Puede especificar el elemento de configuración **GCNoAffinitize** solo para los subprocesos de GC del servidor de establecer afinidad entre con CPU.</span><span class="sxs-lookup"><span data-stu-id="14d7f-133">You can specify the **GCNoAffinitize** configuration element alone to not affinitize server GC threads with CPUs.</span></span> <span data-ttu-id="14d7f-134">También puede utilizarlo junto con el elemento [GCHeapCount](gcheapcount-element.md) para controlar el número de subprocesos y montones de GC utilizados por una aplicación.</span><span class="sxs-lookup"><span data-stu-id="14d7f-134">You can also use it along with the [GCHeapCount](gcheapcount-element.md) element to control the number of GC heaps and threads used by an application.</span></span>

<span data-ttu-id="14d7f-135">Si el `enabled` atributo del elemento **GCNoAffinitize** es `false` (su valor predeterminado), también puede usar el elemento [GCHeapCount](gcheapcount-element.md) para especificar el número de subprocesos y montones de GC, junto con el elemento [GCHeapAffinitizeMask](gcheapaffinitizemask-element.md) para especificar los procesadores en los que se afinidad con los montones y subprocesos de GC.</span><span class="sxs-lookup"><span data-stu-id="14d7f-135">If the `enabled` attribute of the **GCNoAffinitize** element is `false` (its default value), you can also use the [GCHeapCount](gcheapcount-element.md) element to specify the number of GC threads and heaps, along with the [GCHeapAffinitizeMask](gcheapaffinitizemask-element.md) element to specify the processors to which the GC threads and heaps are affinitized.</span></span>

## <a name="example"></a><span data-ttu-id="14d7f-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="14d7f-136">Example</span></span>

<span data-ttu-id="14d7f-137">En el ejemplo siguiente no se establecer afinidad entre los subprocesos de GC del servidor:</span><span class="sxs-lookup"><span data-stu-id="14d7f-137">The following example does not hard-affinitize server GC threads:</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

<span data-ttu-id="14d7f-138">En el ejemplo siguiente no se establecer afinidad entre los subprocesos de GC del servidor y se limita el número de subprocesos o montones de GC a 10:</span><span class="sxs-lookup"><span data-stu-id="14d7f-138">The following example does not affinitize server GC threads and limits the number of GC heaps/threads to 10:</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="14d7f-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="14d7f-139">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="14d7f-140">Elemento GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="14d7f-140">GCHeapAffinitizeMask element</span></span>](gcheapaffinitizemask-element.md)
- [<span data-ttu-id="14d7f-141">Elemento GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="14d7f-141">GCHeapCount element</span></span>](gcheapcount-element.md)
- [<span data-ttu-id="14d7f-142">Fundamentos de la recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="14d7f-142">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="14d7f-143">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="14d7f-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="14d7f-144">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="14d7f-144">Configuration File Schema</span></span>](../index.md)
