---
title: Elemento <Thread_UseAllCpuGroups>
ms.date: 03/30/2017
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
ms.openlocfilehash: a3a612c0ffbcb211157b9623d298ce8ad7a13e94
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115410"
---
# <a name="thread_useallcpugroups-element"></a><span data-ttu-id="812dc-102">\<elemento > Thread_UseAllCpuGroups</span><span class="sxs-lookup"><span data-stu-id="812dc-102">\<Thread_UseAllCpuGroups> Element</span></span>

<span data-ttu-id="812dc-103">Especifica si el runtime distribuye subprocesos administrados en todos los grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="812dc-103">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>

<span data-ttu-id="812dc-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="812dc-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="812dc-105">&nbsp;&nbsp;[ **\<en tiempo de ejecución >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="812dc-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="812dc-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Thread_UseAllCpuGroups >**</span><span class="sxs-lookup"><span data-stu-id="812dc-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Thread_UseAllCpuGroups>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="812dc-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="812dc-107">Syntax</span></span>

```xml
<Thread_UseAllCpuGroups
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="812dc-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="812dc-108">Attributes and Elements</span></span>

<span data-ttu-id="812dc-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="812dc-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="812dc-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="812dc-110">Attributes</span></span>

|<span data-ttu-id="812dc-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="812dc-111">Attribute</span></span>|<span data-ttu-id="812dc-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="812dc-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="812dc-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="812dc-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="812dc-114">Especifica si el runtime distribuye subprocesos administrados en todos los grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="812dc-114">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="812dc-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="812dc-115">enabled Attribute</span></span>

|<span data-ttu-id="812dc-116">Valor</span><span class="sxs-lookup"><span data-stu-id="812dc-116">Value</span></span>|<span data-ttu-id="812dc-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="812dc-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="812dc-118">El runtime no distribuye los subprocesos administrados entre varios grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="812dc-118">The runtime does not distribute managed threads across multiple CPU groups.</span></span> <span data-ttu-id="812dc-119">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="812dc-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="812dc-120">El tiempo de ejecución distribuye los subprocesos administrados entre varios grupos de CPU, si el equipo tiene varios grupos de CPU y el elemento [\<GCCpuGroup >](gccpugroup-element.md) está habilitado.</span><span class="sxs-lookup"><span data-stu-id="812dc-120">The runtime distributes managed threads across multiple CPU groups, if the computer has multiple CPU groups and the [\<GCCpuGroup>](gccpugroup-element.md) element is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="812dc-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="812dc-121">Child Elements</span></span>

<span data-ttu-id="812dc-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="812dc-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="812dc-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="812dc-123">Parent Elements</span></span>

|<span data-ttu-id="812dc-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="812dc-124">Element</span></span>|<span data-ttu-id="812dc-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="812dc-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="812dc-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="812dc-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="812dc-127">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="812dc-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="812dc-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="812dc-128">Remarks</span></span>

<span data-ttu-id="812dc-129">Cuando un equipo tiene varios grupos de CPU, la habilitación de este elemento hace que el tiempo de ejecución distribuya los subprocesos administrados en todos los grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="812dc-129">When a computer has multiple CPU groups, enabling this element causes the runtime to distribute managed threads across all CPU groups.</span></span> <span data-ttu-id="812dc-130">Para usar esta característica, también debe habilitar el elemento [\<GCCpuGroup >](gccpugroup-element.md) , que extiende la recolección de elementos no utilizados a todos los grupos de CPU y tiene en cuenta todos los núcleos al crear y equilibrar los montones.</span><span class="sxs-lookup"><span data-stu-id="812dc-130">To use this feature, you must also enable the [\<GCCpuGroup>](gccpugroup-element.md) element, which extends garbage collection to all CPU groups and takes all cores into account when creating and balancing heaps.</span></span> <span data-ttu-id="812dc-131">Para habilitar el elemento [\<GCCpuGroup >](gccpugroup-element.md) , es necesario habilitar el elemento de [> de\<gcServer](gcserver-element.md) .</span><span class="sxs-lookup"><span data-stu-id="812dc-131">Enabling the [\<GCCpuGroup>](gccpugroup-element.md) element requires enabling the [\<gcServer>](gcserver-element.md) element.</span></span> <span data-ttu-id="812dc-132">Si estos elementos no están habilitados, la habilitación del elemento `<Thread_UseAllCpuGroups>` no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="812dc-132">If these elements are not enabled, enabling the `<Thread_UseAllCpuGroups>` element has no effect.</span></span>

## <a name="example"></a><span data-ttu-id="812dc-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="812dc-133">Example</span></span>

<span data-ttu-id="812dc-134">En el ejemplo siguiente se muestra cómo habilitar la compatibilidad con varios grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="812dc-134">The following example shows how to enable support for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <Thread_UseAllCpuGroups enabled="true"/>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="812dc-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="812dc-135">See also</span></span>

- [<span data-ttu-id="812dc-136">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="812dc-136">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="812dc-137">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="812dc-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="812dc-138">\<elemento > GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="812dc-138">\<GCCpuGroup> Element</span></span>](gccpugroup-element.md)
