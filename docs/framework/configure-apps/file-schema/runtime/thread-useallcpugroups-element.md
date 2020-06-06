---
title: Elemento <Thread_UseAllCpuGroups>
ms.date: 03/30/2017
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
ms.openlocfilehash: a3a612c0ffbcb211157b9623d298ce8ad7a13e94
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73115410"
---
# <a name="thread_useallcpugroups-element"></a><span data-ttu-id="2253b-102">\<Thread_UseAllCpuGroups> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="2253b-102">\<Thread_UseAllCpuGroups> Element</span></span>

<span data-ttu-id="2253b-103">Especifica si el runtime distribuye subprocesos administrados en todos los grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="2253b-103">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<Thread_UseAllCpuGroups>**  

## <a name="syntax"></a><span data-ttu-id="2253b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2253b-104">Syntax</span></span>

```xml
<Thread_UseAllCpuGroups
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2253b-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2253b-105">Attributes and Elements</span></span>

<span data-ttu-id="2253b-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2253b-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="2253b-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="2253b-107">Attributes</span></span>

|<span data-ttu-id="2253b-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="2253b-108">Attribute</span></span>|<span data-ttu-id="2253b-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="2253b-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="2253b-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="2253b-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="2253b-111">Especifica si el runtime distribuye subprocesos administrados en todos los grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="2253b-111">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="2253b-112">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="2253b-112">enabled Attribute</span></span>

|<span data-ttu-id="2253b-113">Value</span><span class="sxs-lookup"><span data-stu-id="2253b-113">Value</span></span>|<span data-ttu-id="2253b-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="2253b-114">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="2253b-115">El runtime no distribuye los subprocesos administrados entre varios grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="2253b-115">The runtime does not distribute managed threads across multiple CPU groups.</span></span> <span data-ttu-id="2253b-116">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2253b-116">This is the default.</span></span>|
|`true`|<span data-ttu-id="2253b-117">El motor en tiempo de ejecución distribuye los subprocesos administrados entre varios grupos de CPU, si el equipo tiene varios grupos de CPU y el [\<GCCpuGroup>](gccpugroup-element.md) elemento está habilitado.</span><span class="sxs-lookup"><span data-stu-id="2253b-117">The runtime distributes managed threads across multiple CPU groups, if the computer has multiple CPU groups and the [\<GCCpuGroup>](gccpugroup-element.md) element is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="2253b-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2253b-118">Child Elements</span></span>

<span data-ttu-id="2253b-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2253b-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2253b-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2253b-120">Parent Elements</span></span>

|<span data-ttu-id="2253b-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="2253b-121">Element</span></span>|<span data-ttu-id="2253b-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="2253b-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="2253b-123">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2253b-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="2253b-124">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="2253b-124">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2253b-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2253b-125">Remarks</span></span>

<span data-ttu-id="2253b-126">Cuando un equipo tiene varios grupos de CPU, la habilitación de este elemento hace que el tiempo de ejecución distribuya los subprocesos administrados en todos los grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="2253b-126">When a computer has multiple CPU groups, enabling this element causes the runtime to distribute managed threads across all CPU groups.</span></span> <span data-ttu-id="2253b-127">Para usar esta característica, también debe habilitar el [\<GCCpuGroup>](gccpugroup-element.md) elemento, que extiende la recolección de elementos no utilizados a todos los grupos de CPU y tiene en cuenta todos los núcleos al crear y equilibrar los montones.</span><span class="sxs-lookup"><span data-stu-id="2253b-127">To use this feature, you must also enable the [\<GCCpuGroup>](gccpugroup-element.md) element, which extends garbage collection to all CPU groups and takes all cores into account when creating and balancing heaps.</span></span> <span data-ttu-id="2253b-128">Para habilitar el elemento, es [\<GCCpuGroup>](gccpugroup-element.md) necesario habilitar el [\<gcServer>](gcserver-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="2253b-128">Enabling the [\<GCCpuGroup>](gccpugroup-element.md) element requires enabling the [\<gcServer>](gcserver-element.md) element.</span></span> <span data-ttu-id="2253b-129">Si estos elementos no están habilitados, la habilitación del `<Thread_UseAllCpuGroups>` elemento no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="2253b-129">If these elements are not enabled, enabling the `<Thread_UseAllCpuGroups>` element has no effect.</span></span>

## <a name="example"></a><span data-ttu-id="2253b-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2253b-130">Example</span></span>

<span data-ttu-id="2253b-131">En el ejemplo siguiente se muestra cómo habilitar la compatibilidad con varios grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="2253b-131">The following example shows how to enable support for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <Thread_UseAllCpuGroups enabled="true"/>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="2253b-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2253b-132">See also</span></span>

- [<span data-ttu-id="2253b-133">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="2253b-133">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="2253b-134">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="2253b-134">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="2253b-135">\<GCCpuGroup>Element</span><span class="sxs-lookup"><span data-stu-id="2253b-135">\<GCCpuGroup> Element</span></span>](gccpugroup-element.md)
