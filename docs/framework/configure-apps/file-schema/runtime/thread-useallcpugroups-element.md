---
title: Elemento <Thread_UseAllCpuGroups>
ms.date: 03/30/2017
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e9ee6bdb7094ea2bc9e283e331c0f6ad9b68e4f9
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663422"
---
# <a name="thread_useallcpugroups-element"></a><span data-ttu-id="c57d5-102">\<Thread_UseAllCpuGroups >, elemento</span><span class="sxs-lookup"><span data-stu-id="c57d5-102">\<Thread_UseAllCpuGroups> Element</span></span>

<span data-ttu-id="c57d5-103">Especifica si el runtime distribuye subprocesos administrados en todos los grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="c57d5-103">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>

<span data-ttu-id="c57d5-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c57d5-104">\<configuration></span></span>\
<span data-ttu-id="c57d5-105">\<> en tiempo de ejecución </span><span class="sxs-lookup"><span data-stu-id="c57d5-105">\<runtime></span></span>\
<span data-ttu-id="c57d5-106">\<> Thread_UseAllCpuGroups</span><span class="sxs-lookup"><span data-stu-id="c57d5-106">\<Thread_UseAllCpuGroups></span></span>

## <a name="syntax"></a><span data-ttu-id="c57d5-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c57d5-107">Syntax</span></span>

```xml
<Thread_UseAllCpuGroups
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c57d5-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c57d5-108">Attributes and Elements</span></span>

<span data-ttu-id="c57d5-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c57d5-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="c57d5-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="c57d5-110">Attributes</span></span>

|<span data-ttu-id="c57d5-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="c57d5-111">Attribute</span></span>|<span data-ttu-id="c57d5-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c57d5-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="c57d5-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="c57d5-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="c57d5-114">Especifica si el runtime distribuye subprocesos administrados en todos los grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="c57d5-114">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="c57d5-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="c57d5-115">enabled Attribute</span></span>

|<span data-ttu-id="c57d5-116">Valor</span><span class="sxs-lookup"><span data-stu-id="c57d5-116">Value</span></span>|<span data-ttu-id="c57d5-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c57d5-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="c57d5-118">El runtime no distribuye los subprocesos administrados entre varios grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="c57d5-118">The runtime does not distribute managed threads across multiple CPU groups.</span></span> <span data-ttu-id="c57d5-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c57d5-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="c57d5-120">El motor en tiempo de ejecución distribuye los subprocesos administrados entre varios grupos de CPU, si el equipo tiene varios grupos de CPU y el [ \<elemento > GCCpuGroup](gccpugroup-element.md) está habilitado.</span><span class="sxs-lookup"><span data-stu-id="c57d5-120">The runtime distributes managed threads across multiple CPU groups, if the computer has multiple CPU groups and the [\<GCCpuGroup>](gccpugroup-element.md) element is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="c57d5-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c57d5-121">Child Elements</span></span>

<span data-ttu-id="c57d5-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c57d5-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c57d5-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c57d5-123">Parent Elements</span></span>

|<span data-ttu-id="c57d5-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="c57d5-124">Element</span></span>|<span data-ttu-id="c57d5-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c57d5-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="c57d5-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c57d5-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="c57d5-127">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="c57d5-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c57d5-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c57d5-128">Remarks</span></span>

<span data-ttu-id="c57d5-129">Cuando un equipo tiene varios grupos de CPU, la habilitación de este elemento hace que el tiempo de ejecución distribuya los subprocesos administrados en todos los grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="c57d5-129">When a computer has multiple CPU groups, enabling this element causes the runtime to distribute managed threads across all CPU groups.</span></span> <span data-ttu-id="c57d5-130">Para usar esta característica, también debe habilitar el elemento [ \<> de GCCpuGroup](gccpugroup-element.md) , que extiende la recolección de elementos no utilizados a todos los grupos de CPU y tiene en cuenta todos los núcleos al crear y equilibrar los montones.</span><span class="sxs-lookup"><span data-stu-id="c57d5-130">To use this feature, you must also enable the [\<GCCpuGroup>](gccpugroup-element.md) element, which extends garbage collection to all CPU groups and takes all cores into account when creating and balancing heaps.</span></span> <span data-ttu-id="c57d5-131">Para habilitar el [ \<elemento > GCCpuGroup](gccpugroup-element.md) es necesario habilitar el [ \<elemento gcServer >](gcserver-element.md) .</span><span class="sxs-lookup"><span data-stu-id="c57d5-131">Enabling the [\<GCCpuGroup>](gccpugroup-element.md) element requires enabling the [\<gcServer>](gcserver-element.md) element.</span></span> <span data-ttu-id="c57d5-132">Si estos elementos no están habilitados, la `<Thread_UseAllCpuGroups>` habilitación del elemento no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="c57d5-132">If these elements are not enabled, enabling the `<Thread_UseAllCpuGroups>` element has no effect.</span></span>

## <a name="example"></a><span data-ttu-id="c57d5-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c57d5-133">Example</span></span>

<span data-ttu-id="c57d5-134">En el ejemplo siguiente se muestra cómo habilitar la compatibilidad con varios grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="c57d5-134">The following example shows how to enable support for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <Thread_UseAllCpuGroups enabled="true"/>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="c57d5-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="c57d5-135">See also</span></span>

- [<span data-ttu-id="c57d5-136">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="c57d5-136">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c57d5-137">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="c57d5-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="c57d5-138">\<GCCpuGroup >, elemento</span><span class="sxs-lookup"><span data-stu-id="c57d5-138">\<GCCpuGroup> Element</span></span>](gccpugroup-element.md)
