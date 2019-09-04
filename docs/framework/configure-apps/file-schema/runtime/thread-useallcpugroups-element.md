---
title: Elemento <Thread_UseAllCpuGroups>
ms.date: 03/30/2017
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e964f1b2861926803b0449be06cbfd9567ac74a3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252270"
---
# <a name="thread_useallcpugroups-element"></a><span data-ttu-id="abf0f-102">\<Thread_UseAllCpuGroups >, elemento</span><span class="sxs-lookup"><span data-stu-id="abf0f-102">\<Thread_UseAllCpuGroups> Element</span></span>

<span data-ttu-id="abf0f-103">Especifica si el runtime distribuye subprocesos administrados en todos los grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="abf0f-103">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>

<span data-ttu-id="abf0f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="abf0f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="abf0f-105">&nbsp;&nbsp;[ **\<> en tiempo de ejecución**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="abf0f-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="abf0f-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<> Thread_UseAllCpuGroups**</span><span class="sxs-lookup"><span data-stu-id="abf0f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Thread_UseAllCpuGroups>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="abf0f-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="abf0f-107">Syntax</span></span>

```xml
<Thread_UseAllCpuGroups
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="abf0f-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="abf0f-108">Attributes and Elements</span></span>

<span data-ttu-id="abf0f-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="abf0f-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="abf0f-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="abf0f-110">Attributes</span></span>

|<span data-ttu-id="abf0f-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="abf0f-111">Attribute</span></span>|<span data-ttu-id="abf0f-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="abf0f-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="abf0f-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="abf0f-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="abf0f-114">Especifica si el runtime distribuye subprocesos administrados en todos los grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="abf0f-114">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="abf0f-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="abf0f-115">enabled Attribute</span></span>

|<span data-ttu-id="abf0f-116">Value</span><span class="sxs-lookup"><span data-stu-id="abf0f-116">Value</span></span>|<span data-ttu-id="abf0f-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="abf0f-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="abf0f-118">El runtime no distribuye los subprocesos administrados entre varios grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="abf0f-118">The runtime does not distribute managed threads across multiple CPU groups.</span></span> <span data-ttu-id="abf0f-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="abf0f-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="abf0f-120">El motor en tiempo de ejecución distribuye los subprocesos administrados entre varios grupos de CPU, si el equipo tiene varios grupos de CPU y el [ \<elemento > GCCpuGroup](gccpugroup-element.md) está habilitado.</span><span class="sxs-lookup"><span data-stu-id="abf0f-120">The runtime distributes managed threads across multiple CPU groups, if the computer has multiple CPU groups and the [\<GCCpuGroup>](gccpugroup-element.md) element is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="abf0f-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="abf0f-121">Child Elements</span></span>

<span data-ttu-id="abf0f-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="abf0f-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="abf0f-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="abf0f-123">Parent Elements</span></span>

|<span data-ttu-id="abf0f-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="abf0f-124">Element</span></span>|<span data-ttu-id="abf0f-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="abf0f-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="abf0f-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="abf0f-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="abf0f-127">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="abf0f-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="abf0f-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="abf0f-128">Remarks</span></span>

<span data-ttu-id="abf0f-129">Cuando un equipo tiene varios grupos de CPU, la habilitación de este elemento hace que el tiempo de ejecución distribuya los subprocesos administrados en todos los grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="abf0f-129">When a computer has multiple CPU groups, enabling this element causes the runtime to distribute managed threads across all CPU groups.</span></span> <span data-ttu-id="abf0f-130">Para usar esta característica, también debe habilitar el elemento [ \<> de GCCpuGroup](gccpugroup-element.md) , que extiende la recolección de elementos no utilizados a todos los grupos de CPU y tiene en cuenta todos los núcleos al crear y equilibrar los montones.</span><span class="sxs-lookup"><span data-stu-id="abf0f-130">To use this feature, you must also enable the [\<GCCpuGroup>](gccpugroup-element.md) element, which extends garbage collection to all CPU groups and takes all cores into account when creating and balancing heaps.</span></span> <span data-ttu-id="abf0f-131">Para habilitar el [ \<elemento > GCCpuGroup](gccpugroup-element.md) es necesario habilitar el [ \<elemento gcServer >](gcserver-element.md) .</span><span class="sxs-lookup"><span data-stu-id="abf0f-131">Enabling the [\<GCCpuGroup>](gccpugroup-element.md) element requires enabling the [\<gcServer>](gcserver-element.md) element.</span></span> <span data-ttu-id="abf0f-132">Si estos elementos no están habilitados, la `<Thread_UseAllCpuGroups>` habilitación del elemento no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="abf0f-132">If these elements are not enabled, enabling the `<Thread_UseAllCpuGroups>` element has no effect.</span></span>

## <a name="example"></a><span data-ttu-id="abf0f-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="abf0f-133">Example</span></span>

<span data-ttu-id="abf0f-134">En el ejemplo siguiente se muestra cómo habilitar la compatibilidad con varios grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="abf0f-134">The following example shows how to enable support for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <Thread_UseAllCpuGroups enabled="true"/>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="abf0f-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="abf0f-135">See also</span></span>

- [<span data-ttu-id="abf0f-136">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="abf0f-136">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="abf0f-137">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="abf0f-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="abf0f-138">\<GCCpuGroup >, elemento</span><span class="sxs-lookup"><span data-stu-id="abf0f-138">\<GCCpuGroup> Element</span></span>](gccpugroup-element.md)
