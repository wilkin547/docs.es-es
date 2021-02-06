---
description: 'Más información acerca de: <performanceCounters> elemento'
title: <performanceCounters> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounters element
- <performanceCounters> element
ms.assetid: a71f605b-c7d9-4501-a5c3-abcbb964a43f
ms.openlocfilehash: 3a9a6c42575be3fc7fb5c5d80ffecd940894e164
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639580"
---
# <a name="performancecounters-element"></a><span data-ttu-id="42412-103">\<performanceCounters> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="42412-103">\<performanceCounters> Element</span></span>

<span data-ttu-id="42412-104">Especifica el tamaño de la memoria global que comparten los contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="42412-104">Specifies the size of the global memory shared by performance counters.</span></span>

[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<performanceCounters>**  

## <a name="syntax"></a><span data-ttu-id="42412-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42412-105">Syntax</span></span>

```xml
<performanceCounters filemappingsize="524288" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="42412-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="42412-106">Attributes and Elements</span></span>

<span data-ttu-id="42412-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="42412-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="42412-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="42412-108">Attributes</span></span>

|<span data-ttu-id="42412-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="42412-109">Attribute</span></span>|<span data-ttu-id="42412-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="42412-110">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="42412-111">filemappingsize</span><span class="sxs-lookup"><span data-stu-id="42412-111">filemappingsize</span></span>|<span data-ttu-id="42412-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="42412-112">Required attribute.</span></span><br /><br /> <span data-ttu-id="42412-113">Especifica el tamaño (en bytes) de la memoria global compartida por los contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="42412-113">Specifies the size, in bytes, of the global memory shared by performance counters.</span></span> <span data-ttu-id="42412-114">El valor predeterminado es 524288.</span><span class="sxs-lookup"><span data-stu-id="42412-114">The default is 524288.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="42412-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="42412-115">Child Elements</span></span>

<span data-ttu-id="42412-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="42412-116">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="42412-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="42412-117">Parent Elements</span></span>

|<span data-ttu-id="42412-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="42412-118">Element</span></span>|<span data-ttu-id="42412-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="42412-119">Description</span></span>|
|-------------|-----------------|
|`Configuration`|<span data-ttu-id="42412-120">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="42412-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`system.diagnostics`|<span data-ttu-id="42412-121">Especifica el elemento raíz de la sección de configuración de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="42412-121">Specifies the root element for the ASP.NET configuration section.</span></span>|

## <a name="remarks"></a><span data-ttu-id="42412-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="42412-122">Remarks</span></span>

<span data-ttu-id="42412-123">Los contadores de rendimiento usan un archivo asignado a la memoria, o la memoria compartida, para publicar datos de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="42412-123">Performance counters use a memory mapped file, or shared memory, to publish performance data.</span></span>  <span data-ttu-id="42412-124">El tamaño de la memoria compartida determina el número de instancias que se pueden usar a la vez.</span><span class="sxs-lookup"><span data-stu-id="42412-124">The size of the shared memory determines how many instances can be used at once.</span></span>  <span data-ttu-id="42412-125">Hay dos tipos de memoria compartida: memoria compartida global y memoria compartida independiente.</span><span class="sxs-lookup"><span data-stu-id="42412-125">There are two types of shared memory: global shared memory and separate shared memory.</span></span>  <span data-ttu-id="42412-126">Todas las categorías de contadores de rendimiento que se instalan con las .NET Framework versiones 1,0 o 1,1 utilizan la memoria compartida global.</span><span class="sxs-lookup"><span data-stu-id="42412-126">The global shared memory is used by all performance counter categories installed with the .NET Framework versions 1.0 or 1.1.</span></span>  <span data-ttu-id="42412-127">Las categorías de contadores de rendimiento instaladas con la .NET Framework versión 2,0 usan una memoria compartida independiente, y cada categoría de contador de rendimiento tiene su propia memoria.</span><span class="sxs-lookup"><span data-stu-id="42412-127">Performance counter categories installed with the .NET Framework version 2.0 use separate shared memory, with each performance counter category having its own memory.</span></span>

<span data-ttu-id="42412-128">El tamaño de la memoria compartida global solo se puede establecer con un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="42412-128">The size of global shared memory can be set only with a configuration file.</span></span>  <span data-ttu-id="42412-129">El tamaño predeterminado es 524.288 BSÍ, el tamaño máximo es de 33.554.432 bytes y el tamaño mínimo es de 32.768 bytes.</span><span class="sxs-lookup"><span data-stu-id="42412-129">The default size is 524,288 byes, the maximum size is 33,554,432 bytes, and the minimum size is 32,768 bytes.</span></span>  <span data-ttu-id="42412-130">Dado que todos los procesos y las categorías comparten la memoria compartida global, el primer creador especifica el tamaño.</span><span class="sxs-lookup"><span data-stu-id="42412-130">Since the global shared memory is shared by all processes and categories, the first creator specifies the size.</span></span>  <span data-ttu-id="42412-131">Si define el tamaño en el archivo de configuración de la aplicación, ese tamaño solo se utiliza si la aplicación es la primera aplicación que hace que se ejecuten los contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="42412-131">If you define the size in your application configuration file, that size is only used if your application is the first application that causes the performance counters to execute.</span></span>  <span data-ttu-id="42412-132">Por lo tanto, la ubicación correcta para especificar el `filemappingsize` valor es el archivo de Machine.config.</span><span class="sxs-lookup"><span data-stu-id="42412-132">Therefore the correct location to specify the `filemappingsize` value is the Machine.config file.</span></span>  <span data-ttu-id="42412-133">Los contadores de rendimiento individuales no pueden liberar memoria en la memoria compartida global, por lo que finalmente se agota la memoria compartida global si se crea un gran número de instancias de contador de rendimiento con nombres diferentes.</span><span class="sxs-lookup"><span data-stu-id="42412-133">Memory in the global shared memory cannot be released by individual performance counters, so eventually global shared memory is exhausted if a large number of performance counter instances with different names are created.</span></span>

<span data-ttu-id="42412-134">Para el tamaño de la memoria compartida independiente, primero se hace referencia al valor DWORD FileMappingSize en la clave del registro HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\ *\<category name>* \Performance, seguido del valor especificado para la memoria compartida global en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="42412-134">For the size of separate shared memory, the DWORD FileMappingSize value in the registry key HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<category name>* \Performance is referenced first, followed by the value specified for the global shared memory in the configuration file.</span></span> <span data-ttu-id="42412-135">Si el valor FileMappingSize no existe, el tamaño de la memoria compartida independiente se establece en un cuarto (1/4) la configuración global del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="42412-135">If the FileMappingSize value does not exist, then the separate shared memory size is set to one fourth (1/4) the global setting in the configuration file.</span></span>

## <a name="see-also"></a><span data-ttu-id="42412-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="42412-136">See also</span></span>

- <xref:System.Diagnostics.PerformanceCounter>
- <xref:System.Diagnostics.PerformanceCounterCategory>
- <xref:System.Diagnostics.PerformanceCounter.InstanceLifetime%2A>
- <xref:System.Diagnostics.PerformanceCounterInstanceLifetime>
