---
description: 'Más información acerca de: <Thread_UseAllCpuGroups elemento>'
title: Elemento <Thread_UseAllCpuGroups>
ms.date: 03/30/2017
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
ms.openlocfilehash: 3f11ba6855caab25bd261de71c80c78232f2690f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802416"
---
# <a name="thread_useallcpugroups-element"></a><span data-ttu-id="4d310-103">\<Thread_UseAllCpuGroups> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="4d310-103">\<Thread_UseAllCpuGroups> Element</span></span>

<span data-ttu-id="4d310-104">Especifica si el runtime distribuye subprocesos administrados en todos los grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="4d310-104">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<Thread_UseAllCpuGroups>**  

## <a name="syntax"></a><span data-ttu-id="4d310-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d310-105">Syntax</span></span>

```xml
<Thread_UseAllCpuGroups
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="4d310-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4d310-106">Attributes and Elements</span></span>

<span data-ttu-id="4d310-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4d310-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="4d310-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="4d310-108">Attributes</span></span>

|<span data-ttu-id="4d310-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="4d310-109">Attribute</span></span>|<span data-ttu-id="4d310-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d310-110">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="4d310-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="4d310-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="4d310-112">Especifica si el runtime distribuye subprocesos administrados en todos los grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="4d310-112">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="4d310-113">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="4d310-113">enabled Attribute</span></span>

|<span data-ttu-id="4d310-114">Value</span><span class="sxs-lookup"><span data-stu-id="4d310-114">Value</span></span>|<span data-ttu-id="4d310-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d310-115">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="4d310-116">El runtime no distribuye los subprocesos administrados entre varios grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="4d310-116">The runtime does not distribute managed threads across multiple CPU groups.</span></span> <span data-ttu-id="4d310-117">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4d310-117">This is the default.</span></span>|
|`true`|<span data-ttu-id="4d310-118">El motor en tiempo de ejecución distribuye los subprocesos administrados entre varios grupos de CPU, si el equipo tiene varios grupos de CPU y el [\<GCCpuGroup>](gccpugroup-element.md) elemento está habilitado.</span><span class="sxs-lookup"><span data-stu-id="4d310-118">The runtime distributes managed threads across multiple CPU groups, if the computer has multiple CPU groups and the [\<GCCpuGroup>](gccpugroup-element.md) element is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="4d310-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4d310-119">Child Elements</span></span>

<span data-ttu-id="4d310-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4d310-120">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="4d310-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4d310-121">Parent Elements</span></span>

|<span data-ttu-id="4d310-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="4d310-122">Element</span></span>|<span data-ttu-id="4d310-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d310-123">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="4d310-124">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4d310-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="4d310-125">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="4d310-125">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="4d310-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4d310-126">Remarks</span></span>

<span data-ttu-id="4d310-127">Cuando un equipo tiene varios grupos de CPU, la habilitación de este elemento hace que el tiempo de ejecución distribuya los subprocesos administrados en todos los grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="4d310-127">When a computer has multiple CPU groups, enabling this element causes the runtime to distribute managed threads across all CPU groups.</span></span> <span data-ttu-id="4d310-128">Para usar esta característica, también debe habilitar el [\<GCCpuGroup>](gccpugroup-element.md) elemento, que extiende la recolección de elementos no utilizados a todos los grupos de CPU y tiene en cuenta todos los núcleos al crear y equilibrar los montones.</span><span class="sxs-lookup"><span data-stu-id="4d310-128">To use this feature, you must also enable the [\<GCCpuGroup>](gccpugroup-element.md) element, which extends garbage collection to all CPU groups and takes all cores into account when creating and balancing heaps.</span></span> <span data-ttu-id="4d310-129">Para habilitar el elemento, es [\<GCCpuGroup>](gccpugroup-element.md) necesario habilitar el [\<gcServer>](gcserver-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="4d310-129">Enabling the [\<GCCpuGroup>](gccpugroup-element.md) element requires enabling the [\<gcServer>](gcserver-element.md) element.</span></span> <span data-ttu-id="4d310-130">Si estos elementos no están habilitados, la habilitación del `<Thread_UseAllCpuGroups>` elemento no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="4d310-130">If these elements are not enabled, enabling the `<Thread_UseAllCpuGroups>` element has no effect.</span></span>

## <a name="example"></a><span data-ttu-id="4d310-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4d310-131">Example</span></span>

<span data-ttu-id="4d310-132">En el ejemplo siguiente se muestra cómo habilitar la compatibilidad con varios grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="4d310-132">The following example shows how to enable support for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <Thread_UseAllCpuGroups enabled="true"/>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="4d310-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d310-133">See also</span></span>

- [<span data-ttu-id="4d310-134">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="4d310-134">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="4d310-135">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="4d310-135">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="4d310-136">Elemento \<GCCpuGroup></span><span class="sxs-lookup"><span data-stu-id="4d310-136">\<GCCpuGroup> Element</span></span>](gccpugroup-element.md)
