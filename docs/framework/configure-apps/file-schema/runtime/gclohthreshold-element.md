---
title: Elemento GCLOHThreshold
ms.date: 11/20/2019
helpviewer_keywords:
- GCLOHThreshold element
- <GCLOHThreshold> element
ms.openlocfilehash: d72dc9d27984f60dfb6296217263ce8b176093c6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74451327"
---
# <a name="gclohthreshold-element"></a><span data-ttu-id="09b59-102">Elemento GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="09b59-102">GCLOHThreshold element</span></span>

<span data-ttu-id="09b59-103">Especifica el tamaño del umbral, en bytes, que hace que el recolector de elementos no utilizados coloque objetos en el montón de objetos grandes (montón).</span><span class="sxs-lookup"><span data-stu-id="09b59-103">Specifies the threshold size, in bytes, that causes the garbage collector to put objects on the large object heap (LOH).</span></span>

<span data-ttu-id="09b59-104">[\<configuration>](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="09b59-104">[\<configuration>](../configuration-element.md)</span></span>\
<span data-ttu-id="09b59-105">&nbsp;&nbsp;[\<en tiempo de ejecución >](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="09b59-105">&nbsp;&nbsp;[\<runtime>](runtime-element.md)</span></span>\
<span data-ttu-id="09b59-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCLOHThreshold ></span><span class="sxs-lookup"><span data-stu-id="09b59-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCLOHThreshold></span></span>

## <a name="syntax"></a><span data-ttu-id="09b59-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="09b59-107">Syntax</span></span>

```xml
<GCLOHThreshold
   enabled="nnnn"/>
```

## <a name="attributes"></a><span data-ttu-id="09b59-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="09b59-108">Attributes</span></span>

|<span data-ttu-id="09b59-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="09b59-109">Attribute</span></span>|<span data-ttu-id="09b59-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="09b59-110">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="09b59-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="09b59-111">Required attribute.</span></span><br /><br /><span data-ttu-id="09b59-112">Especifica el tamaño del umbral que hace que los objetos se dirijan al montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="09b59-112">Specifies the threshold size that causes objects to go on the large object heap.</span></span>|

### <a name="enabled-attribute"></a><span data-ttu-id="09b59-113">atributo Enabled</span><span class="sxs-lookup"><span data-stu-id="09b59-113">enabled attribute</span></span>

|<span data-ttu-id="09b59-114">Valor</span><span class="sxs-lookup"><span data-stu-id="09b59-114">Value</span></span>|<span data-ttu-id="09b59-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="09b59-115">Description</span></span>|
|-----------|-----------------|
|`nnnn`|<span data-ttu-id="09b59-116">Tamaño del umbral, en bytes, que hace que los objetos vayan al montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="09b59-116">The threshold size, in bytes, that causes objects to go on the large object heap.</span></span>|

## <a name="child-elements"></a><span data-ttu-id="09b59-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="09b59-117">Child elements</span></span>

<span data-ttu-id="09b59-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="09b59-118">None.</span></span>

## <a name="parent-elements"></a><span data-ttu-id="09b59-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="09b59-119">Parent elements</span></span>

|<span data-ttu-id="09b59-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="09b59-120">Element</span></span>|<span data-ttu-id="09b59-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="09b59-121">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="09b59-122">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="09b59-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="09b59-123">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="09b59-123">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="09b59-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="09b59-124">Remarks</span></span>

<span data-ttu-id="09b59-125">Esta configuración se presentó en .NET Framework 4,8.</span><span class="sxs-lookup"><span data-stu-id="09b59-125">This setting was introduced in .NET Framework 4.8.</span></span>

## <a name="see-also"></a><span data-ttu-id="09b59-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="09b59-126">See also</span></span>

- [<span data-ttu-id="09b59-127">Esquema de configuración de tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="09b59-127">Run-time settings schema</span></span>](index.md)
- [<span data-ttu-id="09b59-128">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="09b59-128">Configuration file schema</span></span>](../index.md)
- [<span data-ttu-id="09b59-129">Fundamentos de la recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="09b59-129">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="09b59-130">Opciones de configuración de tiempo de ejecución de .net Core para GC</span><span class="sxs-lookup"><span data-stu-id="09b59-130">NET Core run-time config options for GC</span></span>](../../../../core/run-time-config/garbage-collector.md)
