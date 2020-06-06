---
title: Elemento GCLOHThreshold
ms.date: 11/20/2019
helpviewer_keywords:
- GCLOHThreshold element
- <GCLOHThreshold> element
ms.openlocfilehash: d72dc9d27984f60dfb6296217263ce8b176093c6
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74451327"
---
# <a name="gclohthreshold-element"></a><span data-ttu-id="d8305-102">Elemento GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="d8305-102">GCLOHThreshold element</span></span>

<span data-ttu-id="d8305-103">Especifica el tamaño del umbral, en bytes, que hace que el recolector de elementos no utilizados coloque objetos en el montón de objetos grandes (montón).</span><span class="sxs-lookup"><span data-stu-id="d8305-103">Specifies the threshold size, in bytes, that causes the garbage collector to put objects on the large object heap (LOH).</span></span>

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<runtime>](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCLOHThreshold>

## <a name="syntax"></a><span data-ttu-id="d8305-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d8305-104">Syntax</span></span>

```xml
<GCLOHThreshold
   enabled="nnnn"/>
```

## <a name="attributes"></a><span data-ttu-id="d8305-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="d8305-105">Attributes</span></span>

|<span data-ttu-id="d8305-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="d8305-106">Attribute</span></span>|<span data-ttu-id="d8305-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d8305-107">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="d8305-108">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="d8305-108">Required attribute.</span></span><br /><br /><span data-ttu-id="d8305-109">Especifica el tamaño del umbral que hace que los objetos se dirijan al montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="d8305-109">Specifies the threshold size that causes objects to go on the large object heap.</span></span>|

### <a name="enabled-attribute"></a><span data-ttu-id="d8305-110">atributo Enabled</span><span class="sxs-lookup"><span data-stu-id="d8305-110">enabled attribute</span></span>

|<span data-ttu-id="d8305-111">Value</span><span class="sxs-lookup"><span data-stu-id="d8305-111">Value</span></span>|<span data-ttu-id="d8305-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="d8305-112">Description</span></span>|
|-----------|-----------------|
|`nnnn`|<span data-ttu-id="d8305-113">Tamaño del umbral, en bytes, que hace que los objetos vayan al montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="d8305-113">The threshold size, in bytes, that causes objects to go on the large object heap.</span></span>|

## <a name="child-elements"></a><span data-ttu-id="d8305-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d8305-114">Child elements</span></span>

<span data-ttu-id="d8305-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d8305-115">None.</span></span>

## <a name="parent-elements"></a><span data-ttu-id="d8305-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d8305-116">Parent elements</span></span>

|<span data-ttu-id="d8305-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="d8305-117">Element</span></span>|<span data-ttu-id="d8305-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="d8305-118">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="d8305-119">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d8305-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="d8305-120">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="d8305-120">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d8305-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d8305-121">Remarks</span></span>

<span data-ttu-id="d8305-122">Esta configuración se presentó en .NET Framework 4,8.</span><span class="sxs-lookup"><span data-stu-id="d8305-122">This setting was introduced in .NET Framework 4.8.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8305-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d8305-123">See also</span></span>

- [<span data-ttu-id="d8305-124">Esquema de configuración de tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="d8305-124">Run-time settings schema</span></span>](index.md)
- [<span data-ttu-id="d8305-125">Esquema del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="d8305-125">Configuration file schema</span></span>](../index.md)
- [<span data-ttu-id="d8305-126">Fundamentos de la recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="d8305-126">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="d8305-127">Opciones de configuración de tiempo de ejecución de .net Core para GC</span><span class="sxs-lookup"><span data-stu-id="d8305-127">NET Core run-time config options for GC</span></span>](../../../../core/run-time-config/garbage-collector.md)
