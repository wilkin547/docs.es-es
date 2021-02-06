---
description: 'Más información sobre: elemento GCLOHThreshold'
title: Elemento GCLOHThreshold
ms.date: 11/20/2019
helpviewer_keywords:
- GCLOHThreshold element
- <GCLOHThreshold> element
ms.openlocfilehash: 5d4ef4e6aaf44642c2307dc27ac2e99e966d3ad0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652814"
---
# <a name="gclohthreshold-element"></a><span data-ttu-id="37f31-103">Elemento GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="37f31-103">GCLOHThreshold element</span></span>

<span data-ttu-id="37f31-104">Especifica el tamaño del umbral, en bytes, que hace que el recolector de elementos no utilizados coloque objetos en el montón de objetos grandes (montón).</span><span class="sxs-lookup"><span data-stu-id="37f31-104">Specifies the threshold size, in bytes, that causes the garbage collector to put objects on the large object heap (LOH).</span></span>

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<runtime>](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCLOHThreshold>

## <a name="syntax"></a><span data-ttu-id="37f31-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="37f31-105">Syntax</span></span>

```xml
<GCLOHThreshold
   enabled="nnnn"/>
```

## <a name="attributes"></a><span data-ttu-id="37f31-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="37f31-106">Attributes</span></span>

|<span data-ttu-id="37f31-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="37f31-107">Attribute</span></span>|<span data-ttu-id="37f31-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="37f31-108">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="37f31-109">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="37f31-109">Required attribute.</span></span><br /><br /><span data-ttu-id="37f31-110">Especifica el tamaño del umbral que hace que los objetos se dirijan al montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="37f31-110">Specifies the threshold size that causes objects to go on the large object heap.</span></span>|

### <a name="enabled-attribute"></a><span data-ttu-id="37f31-111">atributo Enabled</span><span class="sxs-lookup"><span data-stu-id="37f31-111">enabled attribute</span></span>

|<span data-ttu-id="37f31-112">Value</span><span class="sxs-lookup"><span data-stu-id="37f31-112">Value</span></span>|<span data-ttu-id="37f31-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="37f31-113">Description</span></span>|
|-----------|-----------------|
|`nnnn`|<span data-ttu-id="37f31-114">Tamaño del umbral, en bytes, que hace que los objetos vayan al montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="37f31-114">The threshold size, in bytes, that causes objects to go on the large object heap.</span></span>|

## <a name="child-elements"></a><span data-ttu-id="37f31-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="37f31-115">Child elements</span></span>

<span data-ttu-id="37f31-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="37f31-116">None.</span></span>

## <a name="parent-elements"></a><span data-ttu-id="37f31-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="37f31-117">Parent elements</span></span>

|<span data-ttu-id="37f31-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="37f31-118">Element</span></span>|<span data-ttu-id="37f31-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="37f31-119">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="37f31-120">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="37f31-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="37f31-121">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="37f31-121">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="37f31-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="37f31-122">Remarks</span></span>

<span data-ttu-id="37f31-123">Esta configuración se presentó en .NET Framework 4,8.</span><span class="sxs-lookup"><span data-stu-id="37f31-123">This setting was introduced in .NET Framework 4.8.</span></span>

## <a name="see-also"></a><span data-ttu-id="37f31-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="37f31-124">See also</span></span>

- [<span data-ttu-id="37f31-125">Esquema de configuración de tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="37f31-125">Run-time settings schema</span></span>](index.md)
- [<span data-ttu-id="37f31-126">Esquema del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="37f31-126">Configuration file schema</span></span>](../index.md)
- [<span data-ttu-id="37f31-127">Fundamentos de la recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="37f31-127">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="37f31-128">Opciones de configuración de tiempo de ejecución de .net Core para GC</span><span class="sxs-lookup"><span data-stu-id="37f31-128">NET Core run-time config options for GC</span></span>](../../../../core/run-time-config/garbage-collector.md)
