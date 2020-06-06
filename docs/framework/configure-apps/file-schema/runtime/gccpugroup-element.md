---
title: <GCCpuGroup> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
ms.openlocfilehash: f1cbe5a7109d6e4aae2e92710920a1c6b3a40d00
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "82102897"
---
# <a name="gccpugroup-element"></a><span data-ttu-id="576b3-102">\<GCCpuGroup> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="576b3-102">\<GCCpuGroup> Element</span></span>

<span data-ttu-id="576b3-103">Especifica si la recolección de elementos no utilizados admite varios grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="576b3-103">Specifies whether garbage collection supports multiple CPU groups.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<GCCpuGroup>**

## <a name="syntax"></a><span data-ttu-id="576b3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="576b3-104">Syntax</span></span>

```xml
<GCCpuGroup
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="576b3-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="576b3-105">Attributes and Elements</span></span>

<span data-ttu-id="576b3-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="576b3-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="576b3-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="576b3-107">Attributes</span></span>

|<span data-ttu-id="576b3-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="576b3-108">Attribute</span></span>|<span data-ttu-id="576b3-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="576b3-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="576b3-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="576b3-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="576b3-111">Especifica si la recolección de elementos no utilizados admite varios grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="576b3-111">Specifies whether garbage collection supports multiple CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="576b3-112">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="576b3-112">enabled Attribute</span></span>

|<span data-ttu-id="576b3-113">Value</span><span class="sxs-lookup"><span data-stu-id="576b3-113">Value</span></span>|<span data-ttu-id="576b3-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="576b3-114">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="576b3-115">La recolección de elementos no utilizados no admite varios grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="576b3-115">Garbage collection does not support multiple CPU groups.</span></span> <span data-ttu-id="576b3-116">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="576b3-116">This is the default.</span></span>|
|`true`|<span data-ttu-id="576b3-117">La recolección de elementos no utilizados admite varios grupos de CPU, si está habilitada la recolección de elementos no utilizados de servidor.</span><span class="sxs-lookup"><span data-stu-id="576b3-117">Garbage collection supports multiple CPU groups, if server garbage collection is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="576b3-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="576b3-118">Child Elements</span></span>

<span data-ttu-id="576b3-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="576b3-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="576b3-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="576b3-120">Parent Elements</span></span>

|<span data-ttu-id="576b3-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="576b3-121">Element</span></span>|<span data-ttu-id="576b3-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="576b3-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="576b3-123">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="576b3-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="576b3-124">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="576b3-124">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="576b3-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="576b3-125">Remarks</span></span>

<span data-ttu-id="576b3-126">Cuando un equipo tiene varios grupos de CPU y la recolección de elementos no utilizados de servidor está habilitada (vea el [\<gcServer>](gcserver-element.md) elemento), la habilitación de este elemento extiende la recolección de elementos no utilizados en todos los grupos de CPU y tiene en cuenta todos los núcleos al crear y equilibrar los montones.</span><span class="sxs-lookup"><span data-stu-id="576b3-126">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span></span>

> [!NOTE]
> <span data-ttu-id="576b3-127">Este elemento solo se aplica a los subprocesos de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="576b3-127">This element applies only to garbage collection threads.</span></span> <span data-ttu-id="576b3-128">Para permitir que el tiempo de ejecución distribuya los subprocesos de usuario en todos los grupos de CPU, también debe habilitar el [\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="576b3-128">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) element.</span></span>

## <a name="example"></a><span data-ttu-id="576b3-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="576b3-129">Example</span></span>

<span data-ttu-id="576b3-130">En el ejemplo siguiente se muestra cómo habilitar la recolección de elementos no utilizados para varios grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="576b3-130">The following example shows how to enable garbage collection for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="576b3-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="576b3-131">See also</span></span>

- [<span data-ttu-id="576b3-132">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="576b3-132">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="576b3-133">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="576b3-133">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="576b3-134">Deshabilitar la recolección de elementos no utilizados simultánea</span><span class="sxs-lookup"><span data-stu-id="576b3-134">Disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [<span data-ttu-id="576b3-135">Recolección de elementos no utilizados de estación de trabajo y de servidor</span><span class="sxs-lookup"><span data-stu-id="576b3-135">Workstation and server garbage collection</span></span>](../../../../standard/garbage-collection/workstation-server-gc.md)
