---
title: <performanceCounters> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounters element
- <performanceCounters> element
ms.assetid: a71f605b-c7d9-4501-a5c3-abcbb964a43f
ms.openlocfilehash: f52fdb2d5b0b7911de63f96663e70735d2f2496c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "71697155"
---
# <a name="performancecounters-element"></a><span data-ttu-id="a17b8-102">\<performanceCounters> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="a17b8-102">\<performanceCounters> Element</span></span>

<span data-ttu-id="a17b8-103">Especifica el tamaño de la memoria global que comparten los contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="a17b8-103">Specifies the size of the global memory shared by performance counters.</span></span>

[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<performanceCounters>**  

## <a name="syntax"></a><span data-ttu-id="a17b8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a17b8-104">Syntax</span></span>

```xml
<performanceCounters filemappingsize="524288" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a17b8-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a17b8-105">Attributes and Elements</span></span>

<span data-ttu-id="a17b8-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a17b8-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="a17b8-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="a17b8-107">Attributes</span></span>

|<span data-ttu-id="a17b8-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="a17b8-108">Attribute</span></span>|<span data-ttu-id="a17b8-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="a17b8-109">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="a17b8-110">filemappingsize</span><span class="sxs-lookup"><span data-stu-id="a17b8-110">filemappingsize</span></span>|<span data-ttu-id="a17b8-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="a17b8-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="a17b8-112">Especifica el tamaño (en bytes) de la memoria global compartida por los contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="a17b8-112">Specifies the size, in bytes, of the global memory shared by performance counters.</span></span> <span data-ttu-id="a17b8-113">El valor predeterminado es 524288.</span><span class="sxs-lookup"><span data-stu-id="a17b8-113">The default is 524288.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="a17b8-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a17b8-114">Child Elements</span></span>

<span data-ttu-id="a17b8-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a17b8-115">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a17b8-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a17b8-116">Parent Elements</span></span>

|<span data-ttu-id="a17b8-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="a17b8-117">Element</span></span>|<span data-ttu-id="a17b8-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="a17b8-118">Description</span></span>|
|-------------|-----------------|
|`Configuration`|<span data-ttu-id="a17b8-119">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a17b8-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`system.diagnostics`|<span data-ttu-id="a17b8-120">Especifica el elemento raíz de la sección de configuración de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a17b8-120">Specifies the root element for the ASP.NET configuration section.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a17b8-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a17b8-121">Remarks</span></span>

<span data-ttu-id="a17b8-122">Los contadores de rendimiento usan un archivo asignado a la memoria, o la memoria compartida, para publicar datos de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="a17b8-122">Performance counters use a memory mapped file, or shared memory, to publish performance data.</span></span>  <span data-ttu-id="a17b8-123">El tamaño de la memoria compartida determina el número de instancias que se pueden usar a la vez.</span><span class="sxs-lookup"><span data-stu-id="a17b8-123">The size of the shared memory determines how many instances can be used at once.</span></span>  <span data-ttu-id="a17b8-124">Hay dos tipos de memoria compartida: memoria compartida global y memoria compartida independiente.</span><span class="sxs-lookup"><span data-stu-id="a17b8-124">There are two types of shared memory: global shared memory and separate shared memory.</span></span>  <span data-ttu-id="a17b8-125">Todas las categorías de contadores de rendimiento que se instalan con las .NET Framework versiones 1,0 o 1,1 utilizan la memoria compartida global.</span><span class="sxs-lookup"><span data-stu-id="a17b8-125">The global shared memory is used by all performance counter categories installed with the .NET Framework versions 1.0 or 1.1.</span></span>  <span data-ttu-id="a17b8-126">Las categorías de contadores de rendimiento instaladas con la .NET Framework versión 2,0 usan una memoria compartida independiente, y cada categoría de contador de rendimiento tiene su propia memoria.</span><span class="sxs-lookup"><span data-stu-id="a17b8-126">Performance counter categories installed with the .NET Framework version 2.0 use separate shared memory, with each performance counter category having its own memory.</span></span>

<span data-ttu-id="a17b8-127">El tamaño de la memoria compartida global solo se puede establecer con un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a17b8-127">The size of global shared memory can be set only with a configuration file.</span></span>  <span data-ttu-id="a17b8-128">El tamaño predeterminado es 524.288 BSÍ, el tamaño máximo es de 33.554.432 bytes y el tamaño mínimo es de 32.768 bytes.</span><span class="sxs-lookup"><span data-stu-id="a17b8-128">The default size is 524,288 byes, the maximum size is 33,554,432 bytes, and the minimum size is 32,768 bytes.</span></span>  <span data-ttu-id="a17b8-129">Dado que todos los procesos y las categorías comparten la memoria compartida global, el primer creador especifica el tamaño.</span><span class="sxs-lookup"><span data-stu-id="a17b8-129">Since the global shared memory is shared by all processes and categories, the first creator specifies the size.</span></span>  <span data-ttu-id="a17b8-130">Si define el tamaño en el archivo de configuración de la aplicación, ese tamaño solo se utiliza si la aplicación es la primera aplicación que hace que se ejecuten los contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="a17b8-130">If you define the size in your application configuration file, that size is only used if your application is the first application that causes the performance counters to execute.</span></span>  <span data-ttu-id="a17b8-131">Por lo tanto, la ubicación correcta para especificar el `filemappingsize` valor es el archivo Machine. config.</span><span class="sxs-lookup"><span data-stu-id="a17b8-131">Therefore the correct location to specify the `filemappingsize` value is the Machine.config file.</span></span>  <span data-ttu-id="a17b8-132">Los contadores de rendimiento individuales no pueden liberar memoria en la memoria compartida global, por lo que finalmente se agota la memoria compartida global si se crea un gran número de instancias de contador de rendimiento con nombres diferentes.</span><span class="sxs-lookup"><span data-stu-id="a17b8-132">Memory in the global shared memory cannot be released by individual performance counters, so eventually global shared memory is exhausted if a large number of performance counter instances with different names are created.</span></span>

<span data-ttu-id="a17b8-133">Para el tamaño de la memoria compartida independiente, primero se hace referencia al valor DWORD FileMappingSize en la clave del registro HKEY_LOCAL_MACHINE \SYSTEM\CurrentControlSet\Services \\ *\<category name>* \Performance, seguido del valor especificado para la memoria compartida global en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a17b8-133">For the size of separate shared memory, the DWORD FileMappingSize value in the registry key HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<category name>* \Performance is referenced first, followed by the value specified for the global shared memory in the configuration file.</span></span> <span data-ttu-id="a17b8-134">Si el valor FileMappingSize no existe, el tamaño de la memoria compartida independiente se establece en un cuarto (1/4) la configuración global del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a17b8-134">If the FileMappingSize value does not exist, then the separate shared memory size is set to one fourth (1/4) the global setting in the configuration file.</span></span>

## <a name="see-also"></a><span data-ttu-id="a17b8-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a17b8-135">See also</span></span>

- <xref:System.Diagnostics.PerformanceCounter>
- <xref:System.Diagnostics.PerformanceCounterCategory>
- <xref:System.Diagnostics.PerformanceCounter.InstanceLifetime%2A>
- <xref:System.Diagnostics.PerformanceCounterInstanceLifetime>
