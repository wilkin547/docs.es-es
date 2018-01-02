---
title: '&lt;performanceCounters&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounters element
- <perfomanceCounters> element
ms.assetid: a71f605b-c7d9-4501-a5c3-abcbb964a43f
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 64afd62c6eeca7bce14e331fdc65fccfa3d02bce
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltperformancecountersgt-element"></a><span data-ttu-id="14742-102">&lt;performanceCounters&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="14742-102">&lt;performanceCounters&gt; Element</span></span>
<span data-ttu-id="14742-103">Especifica el tamaño de la memoria global que comparten los contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="14742-103">Specifies the size of the global memory shared by performance counters.</span></span>  
  
 <span data-ttu-id="14742-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="14742-104">\<configuration></span></span>  
<span data-ttu-id="14742-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="14742-105">\<system.diagnostics></span></span>  
<span data-ttu-id="14742-106">\<performanceCounters ></span><span class="sxs-lookup"><span data-stu-id="14742-106">\<performanceCounters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14742-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="14742-107">Syntax</span></span>  
  
```xml  
<performanceCounters filemappingsize="524288" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14742-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="14742-108">Attributes and Elements</span></span>  
 <span data-ttu-id="14742-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="14742-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14742-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="14742-110">Attributes</span></span>  
  
|<span data-ttu-id="14742-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="14742-111">Attribute</span></span>|<span data-ttu-id="14742-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="14742-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="14742-113">FileMappingSize</span><span class="sxs-lookup"><span data-stu-id="14742-113">filemappingsize</span></span>|<span data-ttu-id="14742-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="14742-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="14742-115">Especifica el tamaño, en bytes, de la memoria global compartida por los contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="14742-115">Specifies the size, in bytes, of the global memory shared by performance counters.</span></span> <span data-ttu-id="14742-116">El valor predeterminado es 524288.</span><span class="sxs-lookup"><span data-stu-id="14742-116">The default is 524288.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="14742-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="14742-117">Child Elements</span></span>  
 <span data-ttu-id="14742-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="14742-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="14742-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="14742-119">Parent Elements</span></span>  
  
|<span data-ttu-id="14742-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="14742-120">Element</span></span>|<span data-ttu-id="14742-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="14742-121">Description</span></span>|  
|-------------|-----------------|  
|`Configuration`|<span data-ttu-id="14742-122">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="14742-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="14742-123">Especifica el elemento raíz de la sección de configuración de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="14742-123">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14742-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="14742-124">Remarks</span></span>  
 <span data-ttu-id="14742-125">Contadores de rendimiento de usar un archivo asignado a memoria, o memoria compartida, para publicar los datos de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="14742-125">Performance counters use a memory mapped file, or shared memory, to publish performance data.</span></span>  <span data-ttu-id="14742-126">El tamaño de la memoria compartida determina cuántas instancias se pueden utilizar a la vez.</span><span class="sxs-lookup"><span data-stu-id="14742-126">The size of the shared memory determines how many instances can be used at once.</span></span>  <span data-ttu-id="14742-127">Hay dos tipos de memoria compartida: memoria compartida global y memoria compartida independiente.</span><span class="sxs-lookup"><span data-stu-id="14742-127">There are two types of shared memory: global shared memory and separate shared memory.</span></span>  <span data-ttu-id="14742-128">La memoria compartida global se usa por todas las categorías de contador de rendimiento instaladas con las versiones de .NET Framework 1.0 o 1.1.</span><span class="sxs-lookup"><span data-stu-id="14742-128">The global shared memory is used by all performance counter categories installed with the .NET Framework versions 1.0 or 1.1.</span></span>  <span data-ttu-id="14742-129">Las categorías de contador de rendimiento instaladas con la versión 2.0 de .NET Framework utilizan memoria compartida independiente, y cada categoría de contador de rendimiento tiene su propia memoria.</span><span class="sxs-lookup"><span data-stu-id="14742-129">Performance counter categories installed with the .NET Framework version 2.0 use separate shared memory, with each performance counter category having its own memory.</span></span>  
  
 <span data-ttu-id="14742-130">El tamaño de la memoria compartida global puede establecerse solo con un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="14742-130">The size of global shared memory can be set only with a configuration file.</span></span>  <span data-ttu-id="14742-131">El tamaño predeterminado es 524.288 bytes, el tamaño máximo es de 33.554.432 bytes y el tamaño mínimo es de 32.768 bytes.</span><span class="sxs-lookup"><span data-stu-id="14742-131">The default size is 524,288 byes, the maximum size is 33,554,432 bytes, and the minimum size is 32,768 bytes.</span></span>  <span data-ttu-id="14742-132">Puesto que todos los procesos y categorías comparten la memoria compartida global, el primer creador especifica el tamaño.</span><span class="sxs-lookup"><span data-stu-id="14742-132">Since the global shared memory is shared by all processes and categories, the first creator specifies the size.</span></span>  <span data-ttu-id="14742-133">Si el tamaño se define en el archivo de configuración de aplicación, ese tamaño sólo se utiliza si la aplicación es la primera aplicación que hace que los contadores de rendimiento ejecutar.</span><span class="sxs-lookup"><span data-stu-id="14742-133">If you define the size in your application configuration file, that size is only used if your application is the first application that causes the performance counters to execute.</span></span>  <span data-ttu-id="14742-134">Por lo tanto, la ubicación correcta para especificar el `filemappingsize` valor es el archivo Machine.config.</span><span class="sxs-lookup"><span data-stu-id="14742-134">Therefore the correct location to specify the `filemappingsize` value is the Machine.config file.</span></span>  <span data-ttu-id="14742-135">No se puede liberar memoria en la memoria compartida global mediante contadores de rendimiento individuales, por lo que finalmente se agota la memoria compartida global si se crea una gran cantidad de instancias de contador de rendimiento con nombres diferentes.</span><span class="sxs-lookup"><span data-stu-id="14742-135">Memory in the global shared memory cannot be released by individual performance counters, so eventually global shared memory is exhausted if a large number of performance counter instances with different names are created.</span></span>  
  
 <span data-ttu-id="14742-136">El tamaño de memoria compartida independiente, el valor de DWORD FileMappingSize en el registro de clave HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<nombre de categoría >*\Performance se hace referencia en primer lugar, seguido por el valor especificado para la memoria compartida global en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="14742-136">For the size of separate shared memory, the DWORD FileMappingSize value in the registry key HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<category name>*\Performance is referenced first, followed by the value specified for the global shared memory in the configuration file.</span></span> <span data-ttu-id="14742-137">Si el valor de FileMappingSize no existe, el tamaño de memoria compartida independiente se establece en una cuarta (1/4) la configuración global en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="14742-137">If the FileMappingSize value does not exist, then the separate shared memory size is set to one fourth (1/4) the global setting in the configuration file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14742-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="14742-138">See Also</span></span>  
 <xref:System.Diagnostics.PerformanceCounter>  
 <xref:System.Diagnostics.PerformanceCounterCategory>  
 <xref:System.Diagnostics.PerformanceCounter.InstanceLifetime%2A>  
 <xref:System.Diagnostics.PerformanceCounterInstanceLifetime>
