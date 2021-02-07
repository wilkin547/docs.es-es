---
description: 'Más información acerca de: <GCNoAffinitize> elemento'
title: Elemento GCNoAffinitize
ms.date: 11/08/2019
helpviewer_keywords:
- gcNoAffinitize element
- <gcNoAffinitize> element
ms.openlocfilehash: 139c0fd9e1ec829a3569b77a85e6526bec765e21
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754555"
---
# <a name="gcnoaffinitize-element"></a><span data-ttu-id="7b663-103">Elemento \<GCNoAffinitize></span><span class="sxs-lookup"><span data-stu-id="7b663-103">\<GCNoAffinitize> element</span></span>

<span data-ttu-id="7b663-104">Especifica si establecer afinidad entre o no los subprocesos de GC del servidor con CPU.</span><span class="sxs-lookup"><span data-stu-id="7b663-104">Specifies whether or not to affinitize server GC threads with CPUs.</span></span>

\<configuration>\
&nbsp;&nbsp;\<runtime>\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCNoAffinitize>

## <a name="syntax"></a><span data-ttu-id="7b663-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b663-105">Syntax</span></span>

```xml
<GCNoAffinitize
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7b663-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7b663-106">Attributes and elements</span></span>

<span data-ttu-id="7b663-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7b663-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="7b663-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="7b663-108">Attributes</span></span>

|<span data-ttu-id="7b663-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="7b663-109">Attribute</span></span>|<span data-ttu-id="7b663-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="7b663-110">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="7b663-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="7b663-111">Required attribute.</span></span><br /><br /><span data-ttu-id="7b663-112">Especifica si los subprocesos o montones de GC del servidor se afinidad con con los procesadores disponibles en la máquina.</span><span class="sxs-lookup"><span data-stu-id="7b663-112">Specifies whether server GC threads/heaps are affinitized with the processors available on the machine.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="7b663-113">atributo Enabled</span><span class="sxs-lookup"><span data-stu-id="7b663-113">enabled attribute</span></span>

|<span data-ttu-id="7b663-114">Value</span><span class="sxs-lookup"><span data-stu-id="7b663-114">Value</span></span>|<span data-ttu-id="7b663-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="7b663-115">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="7b663-116">Subprocesos de GC del servidor establece con CPU.</span><span class="sxs-lookup"><span data-stu-id="7b663-116">Affinitizes server GC threads with CPUs.</span></span> <span data-ttu-id="7b663-117">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="7b663-117">This is the default.</span></span>|
|`true`|<span data-ttu-id="7b663-118">No establecer afinidad entre los subprocesos de GC de servidor con CPU.</span><span class="sxs-lookup"><span data-stu-id="7b663-118">Does not affinitize server GC threads with CPUs.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="7b663-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7b663-119">Child elements</span></span>

<span data-ttu-id="7b663-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7b663-120">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7b663-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7b663-121">Parent elements</span></span>

|<span data-ttu-id="7b663-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="7b663-122">Element</span></span>|<span data-ttu-id="7b663-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="7b663-123">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="7b663-124">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7b663-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="7b663-125">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="7b663-125">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7b663-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7b663-126">Remarks</span></span>

<span data-ttu-id="7b663-127">De forma predeterminada, los subprocesos de GC de servidor son afinidad cons con sus respectivas CPU.</span><span class="sxs-lookup"><span data-stu-id="7b663-127">By default, server GC threads are hard-affinitized with their respective CPUs.</span></span> <span data-ttu-id="7b663-128">Cada uno de los procesadores disponibles del sistema tiene su propio subproceso y montón de GC.</span><span class="sxs-lookup"><span data-stu-id="7b663-128">Each of the system's available processors has its own GC heap and thread.</span></span> <span data-ttu-id="7b663-129">Esta suele ser la configuración preferida, ya que optimiza el uso de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="7b663-129">This is typically the preferred setting since it optimizes cache usage.</span></span> <span data-ttu-id="7b663-130">A partir de .NET Framework 4.6.2, al establecer el atributo del elemento **GCNoAffinitize** `enabled` en `true` , se puede especificar que los subprocesos de GC del servidor y las CPU no deben estar estrechamente acoplados.</span><span class="sxs-lookup"><span data-stu-id="7b663-130">Starting with .NET Framework 4.6.2, by setting the **GCNoAffinitize** element's `enabled` attribute to `true`, you can specify that server GC threads and CPUs should not be tightly coupled.</span></span>

<span data-ttu-id="7b663-131">Puede especificar el elemento de configuración **GCNoAffinitize** solo para los subprocesos de GC del servidor de establecer afinidad entre con CPU.</span><span class="sxs-lookup"><span data-stu-id="7b663-131">You can specify the **GCNoAffinitize** configuration element alone to not affinitize server GC threads with CPUs.</span></span> <span data-ttu-id="7b663-132">También puede utilizarlo junto con el elemento [GCHeapCount](gcheapcount-element.md) para controlar el número de subprocesos y montones de GC utilizados por una aplicación.</span><span class="sxs-lookup"><span data-stu-id="7b663-132">You can also use it along with the [GCHeapCount](gcheapcount-element.md) element to control the number of GC heaps and threads used by an application.</span></span>

<span data-ttu-id="7b663-133">Si el `enabled` atributo del elemento **GCNoAffinitize** es `false` (su valor predeterminado), también puede usar el elemento [GCHeapCount](gcheapcount-element.md) para especificar el número de subprocesos y montones de GC, junto con el elemento [GCHeapAffinitizeMask](gcheapaffinitizemask-element.md) para especificar los procesadores en los que los subprocesos de GC y los montones están afinidad con.</span><span class="sxs-lookup"><span data-stu-id="7b663-133">If the `enabled` attribute of the **GCNoAffinitize** element is `false` (its default value), you can also use the [GCHeapCount](gcheapcount-element.md) element to specify the number of GC threads and heaps, along with the [GCHeapAffinitizeMask](gcheapaffinitizemask-element.md) element to specify the processors to which the GC threads and heaps are affinitized.</span></span>

## <a name="example"></a><span data-ttu-id="7b663-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7b663-134">Example</span></span>

<span data-ttu-id="7b663-135">En el ejemplo siguiente no se establecer afinidad entre los subprocesos de GC del servidor:</span><span class="sxs-lookup"><span data-stu-id="7b663-135">The following example does not hard-affinitize server GC threads:</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

<span data-ttu-id="7b663-136">En el ejemplo siguiente no se establecer afinidad entre los subprocesos de GC del servidor y se limita el número de subprocesos o montones de GC a 10:</span><span class="sxs-lookup"><span data-stu-id="7b663-136">The following example does not affinitize server GC threads and limits the number of GC heaps/threads to 10:</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="7b663-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b663-137">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="7b663-138">Elemento GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="7b663-138">GCHeapAffinitizeMask element</span></span>](gcheapaffinitizemask-element.md)
- [<span data-ttu-id="7b663-139">Elemento GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="7b663-139">GCHeapCount element</span></span>](gcheapcount-element.md)
- [<span data-ttu-id="7b663-140">Fundamentos de la recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="7b663-140">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="7b663-141">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="7b663-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="7b663-142">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="7b663-142">Configuration File Schema</span></span>](../index.md)
