---
title: '&lt;performanceCounters&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounters element
- <perfomanceCounters> element
ms.assetid: a71f605b-c7d9-4501-a5c3-abcbb964a43f
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 69d6deafb6aad88f5d379c7e8d4ac707e4c51815
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48032470"
---
# <a name="ltperformancecountersgt-element"></a><span data-ttu-id="82857-102">&lt;performanceCounters&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="82857-102">&lt;performanceCounters&gt; Element</span></span>
<span data-ttu-id="82857-103">Especifica el tamaño de la memoria global que comparten los contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="82857-103">Specifies the size of the global memory shared by performance counters.</span></span>  
  
 <span data-ttu-id="82857-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="82857-104">\<configuration></span></span>  
<span data-ttu-id="82857-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="82857-105">\<system.diagnostics></span></span>  
<span data-ttu-id="82857-106">\<performanceCounters ></span><span class="sxs-lookup"><span data-stu-id="82857-106">\<performanceCounters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82857-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="82857-107">Syntax</span></span>  
  
```xml  
<performanceCounters filemappingsize="524288" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="82857-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="82857-108">Attributes and Elements</span></span>  
 <span data-ttu-id="82857-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="82857-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="82857-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="82857-110">Attributes</span></span>  
  
|<span data-ttu-id="82857-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="82857-111">Attribute</span></span>|<span data-ttu-id="82857-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="82857-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="82857-113">FileMappingSize</span><span class="sxs-lookup"><span data-stu-id="82857-113">filemappingsize</span></span>|<span data-ttu-id="82857-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="82857-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="82857-115">Especifica el tamaño, en bytes, de la memoria global compartida por los contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="82857-115">Specifies the size, in bytes, of the global memory shared by performance counters.</span></span> <span data-ttu-id="82857-116">El valor predeterminado es 524288.</span><span class="sxs-lookup"><span data-stu-id="82857-116">The default is 524288.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="82857-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="82857-117">Child Elements</span></span>  
 <span data-ttu-id="82857-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="82857-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="82857-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="82857-119">Parent Elements</span></span>  
  
|<span data-ttu-id="82857-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="82857-120">Element</span></span>|<span data-ttu-id="82857-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="82857-121">Description</span></span>|  
|-------------|-----------------|  
|`Configuration`|<span data-ttu-id="82857-122">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="82857-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="82857-123">Especifica el elemento raíz de la sección de configuración de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="82857-123">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82857-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="82857-124">Remarks</span></span>  
 <span data-ttu-id="82857-125">Contadores de rendimiento de usar un archivo asignado en memoria, o memoria compartida, para publicar datos de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="82857-125">Performance counters use a memory mapped file, or shared memory, to publish performance data.</span></span>  <span data-ttu-id="82857-126">El tamaño de la memoria compartida determina cuántas instancias se pueden usar a la vez.</span><span class="sxs-lookup"><span data-stu-id="82857-126">The size of the shared memory determines how many instances can be used at once.</span></span>  <span data-ttu-id="82857-127">Hay dos tipos de memoria compartida: memoria compartida global y memoria compartida independiente.</span><span class="sxs-lookup"><span data-stu-id="82857-127">There are two types of shared memory: global shared memory and separate shared memory.</span></span>  <span data-ttu-id="82857-128">Se utiliza la memoria global compartida por todas las categorías de contador de rendimiento instaladas con las versiones de .NET Framework 1.0 o 1.1.</span><span class="sxs-lookup"><span data-stu-id="82857-128">The global shared memory is used by all performance counter categories installed with the .NET Framework versions 1.0 or 1.1.</span></span>  <span data-ttu-id="82857-129">Categorías de contador de rendimiento instaladas con la versión 2.0 de .NET Framework usa memoria compartida independiente, con cada categoría de contador de rendimiento tiene su propia memoria.</span><span class="sxs-lookup"><span data-stu-id="82857-129">Performance counter categories installed with the .NET Framework version 2.0 use separate shared memory, with each performance counter category having its own memory.</span></span>  
  
 <span data-ttu-id="82857-130">Solo con un archivo de configuración se puede establecer el tamaño de memoria compartida global.</span><span class="sxs-lookup"><span data-stu-id="82857-130">The size of global shared memory can be set only with a configuration file.</span></span>  <span data-ttu-id="82857-131">El tamaño predeterminado es 524.288 bytes, el tamaño máximo es 33 554 432 bytes y el tamaño mínimo es de 32.768 bytes.</span><span class="sxs-lookup"><span data-stu-id="82857-131">The default size is 524,288 byes, the maximum size is 33,554,432 bytes, and the minimum size is 32,768 bytes.</span></span>  <span data-ttu-id="82857-132">Puesto que todos los procesos y categorías comparten la memoria compartida global, el creador del primer especifica el tamaño.</span><span class="sxs-lookup"><span data-stu-id="82857-132">Since the global shared memory is shared by all processes and categories, the first creator specifies the size.</span></span>  <span data-ttu-id="82857-133">Si define el tamaño del archivo de configuración de aplicación, sólo se utiliza ese tamaño si la primera aplicación que hace que los contadores de rendimiento ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="82857-133">If you define the size in your application configuration file, that size is only used if your application is the first application that causes the performance counters to execute.</span></span>  <span data-ttu-id="82857-134">Por lo tanto, la ubicación correcta para especificar el `filemappingsize` valor es el archivo Machine.config.</span><span class="sxs-lookup"><span data-stu-id="82857-134">Therefore the correct location to specify the `filemappingsize` value is the Machine.config file.</span></span>  <span data-ttu-id="82857-135">No se puede liberar memoria en la memoria global compartida por los contadores de rendimiento individuales, por lo que finalmente se agota la memoria compartida global si se crea un gran número de instancias de contador de rendimiento con nombres diferentes.</span><span class="sxs-lookup"><span data-stu-id="82857-135">Memory in the global shared memory cannot be released by individual performance counters, so eventually global shared memory is exhausted if a large number of performance counter instances with different names are created.</span></span>  
  
 <span data-ttu-id="82857-136">El tamaño de memoria compartida independiente, el valor de DWORD FileMappingSize en el registro de clave HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<nombre de categoría >* \Performance se hace referencia en primer lugar, seguido por el valor especificado para la memoria compartida global en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="82857-136">For the size of separate shared memory, the DWORD FileMappingSize value in the registry key HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<category name>* \Performance is referenced first, followed by the value specified for the global shared memory in the configuration file.</span></span> <span data-ttu-id="82857-137">Si el valor de FileMappingSize no existe, se establece el tamaño de memoria compartida independiente a un cuarto (1/4) la configuración global en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="82857-137">If the FileMappingSize value does not exist, then the separate shared memory size is set to one fourth (1/4) the global setting in the configuration file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82857-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="82857-138">See Also</span></span>  
 <xref:System.Diagnostics.PerformanceCounter>  
 <xref:System.Diagnostics.PerformanceCounterCategory>  
 <xref:System.Diagnostics.PerformanceCounter.InstanceLifetime%2A>  
 <xref:System.Diagnostics.PerformanceCounterInstanceLifetime>
