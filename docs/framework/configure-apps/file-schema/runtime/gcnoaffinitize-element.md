---
title: Elemento GCNoAffinitize
ms.date: 11/08/2019
helpviewer_keywords:
- gcNoAffinitize element
- <gcNoAffinitize> element
ms.openlocfilehash: 16d6e5adefe2b632d7251669650058d7df7cea70
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "84004743"
---
# <a name="gcnoaffinitize-element"></a><span data-ttu-id="0fe8a-102">Elemento \<GCNoAffinitize></span><span class="sxs-lookup"><span data-stu-id="0fe8a-102">\<GCNoAffinitize> element</span></span>

<span data-ttu-id="0fe8a-103">Especifica si establecer afinidad entre o no los subprocesos de GC del servidor con CPU.</span><span class="sxs-lookup"><span data-stu-id="0fe8a-103">Specifies whether or not to affinitize server GC threads with CPUs.</span></span>

\<configuration>\
&nbsp;&nbsp;\<runtime>\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCNoAffinitize>

## <a name="syntax"></a><span data-ttu-id="0fe8a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0fe8a-104">Syntax</span></span>

```xml
<GCNoAffinitize
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0fe8a-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0fe8a-105">Attributes and elements</span></span>

<span data-ttu-id="0fe8a-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0fe8a-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="0fe8a-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="0fe8a-107">Attributes</span></span>

|<span data-ttu-id="0fe8a-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="0fe8a-108">Attribute</span></span>|<span data-ttu-id="0fe8a-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="0fe8a-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="0fe8a-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="0fe8a-110">Required attribute.</span></span><br /><br /><span data-ttu-id="0fe8a-111">Especifica si los subprocesos o montones de GC del servidor se afinidad con con los procesadores disponibles en la máquina.</span><span class="sxs-lookup"><span data-stu-id="0fe8a-111">Specifies whether server GC threads/heaps are affinitized with the processors available on the machine.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="0fe8a-112">atributo Enabled</span><span class="sxs-lookup"><span data-stu-id="0fe8a-112">enabled attribute</span></span>

|<span data-ttu-id="0fe8a-113">Value</span><span class="sxs-lookup"><span data-stu-id="0fe8a-113">Value</span></span>|<span data-ttu-id="0fe8a-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="0fe8a-114">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="0fe8a-115">Subprocesos de GC del servidor establece con CPU.</span><span class="sxs-lookup"><span data-stu-id="0fe8a-115">Affinitizes server GC threads with CPUs.</span></span> <span data-ttu-id="0fe8a-116">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0fe8a-116">This is the default.</span></span>|
|`true`|<span data-ttu-id="0fe8a-117">No establecer afinidad entre los subprocesos de GC de servidor con CPU.</span><span class="sxs-lookup"><span data-stu-id="0fe8a-117">Does not affinitize server GC threads with CPUs.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="0fe8a-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0fe8a-118">Child elements</span></span>

<span data-ttu-id="0fe8a-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0fe8a-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0fe8a-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0fe8a-120">Parent elements</span></span>

|<span data-ttu-id="0fe8a-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="0fe8a-121">Element</span></span>|<span data-ttu-id="0fe8a-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="0fe8a-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="0fe8a-123">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0fe8a-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="0fe8a-124">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="0fe8a-124">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0fe8a-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0fe8a-125">Remarks</span></span>

<span data-ttu-id="0fe8a-126">De forma predeterminada, los subprocesos de GC de servidor son afinidad cons con sus respectivas CPU.</span><span class="sxs-lookup"><span data-stu-id="0fe8a-126">By default, server GC threads are hard-affinitized with their respective CPUs.</span></span> <span data-ttu-id="0fe8a-127">Cada uno de los procesadores disponibles del sistema tiene su propio subproceso y montón de GC.</span><span class="sxs-lookup"><span data-stu-id="0fe8a-127">Each of the system's available processors has its own GC heap and thread.</span></span> <span data-ttu-id="0fe8a-128">Esta suele ser la configuración preferida, ya que optimiza el uso de la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="0fe8a-128">This is typically the preferred setting since it optimizes cache usage.</span></span> <span data-ttu-id="0fe8a-129">A partir de .NET Framework 4.6.2, al establecer el atributo del elemento **GCNoAffinitize** `enabled` en `true` , se puede especificar que los subprocesos de GC del servidor y las CPU no deben estar estrechamente acoplados.</span><span class="sxs-lookup"><span data-stu-id="0fe8a-129">Starting with .NET Framework 4.6.2, by setting the **GCNoAffinitize** element's `enabled` attribute to `true`, you can specify that server GC threads and CPUs should not be tightly coupled.</span></span>

<span data-ttu-id="0fe8a-130">Puede especificar el elemento de configuración **GCNoAffinitize** solo para los subprocesos de GC del servidor de establecer afinidad entre con CPU.</span><span class="sxs-lookup"><span data-stu-id="0fe8a-130">You can specify the **GCNoAffinitize** configuration element alone to not affinitize server GC threads with CPUs.</span></span> <span data-ttu-id="0fe8a-131">También puede utilizarlo junto con el elemento [GCHeapCount](gcheapcount-element.md) para controlar el número de subprocesos y montones de GC utilizados por una aplicación.</span><span class="sxs-lookup"><span data-stu-id="0fe8a-131">You can also use it along with the [GCHeapCount](gcheapcount-element.md) element to control the number of GC heaps and threads used by an application.</span></span>

<span data-ttu-id="0fe8a-132">Si el `enabled` atributo del elemento **GCNoAffinitize** es `false` (su valor predeterminado), también puede usar el elemento [GCHeapCount](gcheapcount-element.md) para especificar el número de subprocesos y montones de GC, junto con el elemento [GCHeapAffinitizeMask](gcheapaffinitizemask-element.md) para especificar los procesadores en los que los subprocesos de GC y los montones están afinidad con.</span><span class="sxs-lookup"><span data-stu-id="0fe8a-132">If the `enabled` attribute of the **GCNoAffinitize** element is `false` (its default value), you can also use the [GCHeapCount](gcheapcount-element.md) element to specify the number of GC threads and heaps, along with the [GCHeapAffinitizeMask](gcheapaffinitizemask-element.md) element to specify the processors to which the GC threads and heaps are affinitized.</span></span>

## <a name="example"></a><span data-ttu-id="0fe8a-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0fe8a-133">Example</span></span>

<span data-ttu-id="0fe8a-134">En el ejemplo siguiente no se establecer afinidad entre los subprocesos de GC del servidor:</span><span class="sxs-lookup"><span data-stu-id="0fe8a-134">The following example does not hard-affinitize server GC threads:</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

<span data-ttu-id="0fe8a-135">En el ejemplo siguiente no se establecer afinidad entre los subprocesos de GC del servidor y se limita el número de subprocesos o montones de GC a 10:</span><span class="sxs-lookup"><span data-stu-id="0fe8a-135">The following example does not affinitize server GC threads and limits the number of GC heaps/threads to 10:</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="0fe8a-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0fe8a-136">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="0fe8a-137">Elemento GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="0fe8a-137">GCHeapAffinitizeMask element</span></span>](gcheapaffinitizemask-element.md)
- [<span data-ttu-id="0fe8a-138">Elemento GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="0fe8a-138">GCHeapCount element</span></span>](gcheapcount-element.md)
- [<span data-ttu-id="0fe8a-139">Fundamentos de la recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="0fe8a-139">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="0fe8a-140">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="0fe8a-140">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="0fe8a-141">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="0fe8a-141">Configuration File Schema</span></span>](../index.md)
