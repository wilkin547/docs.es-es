---
description: 'Más información acerca de: <GCCpuGroup> elemento'
title: <GCCpuGroup> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
ms.openlocfilehash: d4b3aa7084cbc2cb23b273bea95ffaec6e3a74d6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786998"
---
# <a name="gccpugroup-element"></a><span data-ttu-id="cf2cb-103">\<GCCpuGroup> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="cf2cb-103">\<GCCpuGroup> Element</span></span>

<span data-ttu-id="cf2cb-104">Especifica si la recolección de elementos no utilizados admite varios grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="cf2cb-104">Specifies whether garbage collection supports multiple CPU groups.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<GCCpuGroup>**

## <a name="syntax"></a><span data-ttu-id="cf2cb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cf2cb-105">Syntax</span></span>

```xml
<GCCpuGroup
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cf2cb-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="cf2cb-106">Attributes and Elements</span></span>

<span data-ttu-id="cf2cb-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="cf2cb-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="cf2cb-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="cf2cb-108">Attributes</span></span>

|<span data-ttu-id="cf2cb-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="cf2cb-109">Attribute</span></span>|<span data-ttu-id="cf2cb-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="cf2cb-110">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="cf2cb-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="cf2cb-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="cf2cb-112">Especifica si la recolección de elementos no utilizados admite varios grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="cf2cb-112">Specifies whether garbage collection supports multiple CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="cf2cb-113">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="cf2cb-113">enabled Attribute</span></span>

|<span data-ttu-id="cf2cb-114">Value</span><span class="sxs-lookup"><span data-stu-id="cf2cb-114">Value</span></span>|<span data-ttu-id="cf2cb-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="cf2cb-115">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="cf2cb-116">La recolección de elementos no utilizados no admite varios grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="cf2cb-116">Garbage collection does not support multiple CPU groups.</span></span> <span data-ttu-id="cf2cb-117">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="cf2cb-117">This is the default.</span></span>|
|`true`|<span data-ttu-id="cf2cb-118">La recolección de elementos no utilizados admite varios grupos de CPU, si está habilitada la recolección de elementos no utilizados de servidor.</span><span class="sxs-lookup"><span data-stu-id="cf2cb-118">Garbage collection supports multiple CPU groups, if server garbage collection is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="cf2cb-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="cf2cb-119">Child Elements</span></span>

<span data-ttu-id="cf2cb-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="cf2cb-120">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="cf2cb-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cf2cb-121">Parent Elements</span></span>

|<span data-ttu-id="cf2cb-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="cf2cb-122">Element</span></span>|<span data-ttu-id="cf2cb-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="cf2cb-123">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="cf2cb-124">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cf2cb-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="cf2cb-125">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="cf2cb-125">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="cf2cb-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cf2cb-126">Remarks</span></span>

<span data-ttu-id="cf2cb-127">Cuando un equipo tiene varios grupos de CPU y la recolección de elementos no utilizados de servidor está habilitada (vea el [\<gcServer>](gcserver-element.md) elemento), la habilitación de este elemento extiende la recolección de elementos no utilizados en todos los grupos de CPU y tiene en cuenta todos los núcleos al crear y equilibrar los montones.</span><span class="sxs-lookup"><span data-stu-id="cf2cb-127">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span></span>

> [!NOTE]
> <span data-ttu-id="cf2cb-128">Este elemento solo se aplica a los subprocesos de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="cf2cb-128">This element applies only to garbage collection threads.</span></span> <span data-ttu-id="cf2cb-129">Para permitir que el tiempo de ejecución distribuya los subprocesos de usuario en todos los grupos de CPU, también debe habilitar el [\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="cf2cb-129">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) element.</span></span>

## <a name="example"></a><span data-ttu-id="cf2cb-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cf2cb-130">Example</span></span>

<span data-ttu-id="cf2cb-131">En el ejemplo siguiente se muestra cómo habilitar la recolección de elementos no utilizados para varios grupos de CPU.</span><span class="sxs-lookup"><span data-stu-id="cf2cb-131">The following example shows how to enable garbage collection for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="cf2cb-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf2cb-132">See also</span></span>

- [<span data-ttu-id="cf2cb-133">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="cf2cb-133">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="cf2cb-134">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="cf2cb-134">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="cf2cb-135">Deshabilitar la recolección de elementos no utilizados simultánea</span><span class="sxs-lookup"><span data-stu-id="cf2cb-135">Disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [<span data-ttu-id="cf2cb-136">Recolección de elementos no utilizados de estación de trabajo y de servidor</span><span class="sxs-lookup"><span data-stu-id="cf2cb-136">Workstation and server garbage collection</span></span>](../../../../standard/garbage-collection/workstation-server-gc.md)
