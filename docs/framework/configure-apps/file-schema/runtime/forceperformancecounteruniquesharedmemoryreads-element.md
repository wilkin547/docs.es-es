---
title: <forcePerformanceCounterUniqueSharedMemoryReads> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1e9073e48141bc6895d00c773c2d3d2cfeb260f6
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2019
ms.locfileid: "66456461"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a><span data-ttu-id="96339-102">\<forcePerformanceCounterUniqueSharedMemoryReads> Element</span><span class="sxs-lookup"><span data-stu-id="96339-102">\<forcePerformanceCounterUniqueSharedMemoryReads> Element</span></span>
<span data-ttu-id="96339-103">Especifica si PerfCounter.dll usa la configuración del Registro CategoryOptions en una aplicación de .NET Framework 1.1 para determinar si se van a cargar los datos del contador de rendimiento desde la memoria compartida específica de la categoría o la memoria global.</span><span class="sxs-lookup"><span data-stu-id="96339-103">Specifies whether PerfCounter.dll uses the CategoryOptions registry setting in a .NET Framework version 1.1 application to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>  
  
 <span data-ttu-id="96339-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="96339-104">\<configuration></span></span>  
<span data-ttu-id="96339-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="96339-105">\<runtime></span></span>  
<span data-ttu-id="96339-106">\<forcePerformanceCounterUniqueSharedMemoryReads></span><span class="sxs-lookup"><span data-stu-id="96339-106">\<forcePerformanceCounterUniqueSharedMemoryReads></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96339-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="96339-107">Syntax</span></span>  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads   
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="96339-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="96339-108">Attributes and Elements</span></span>  
 <span data-ttu-id="96339-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="96339-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="96339-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="96339-110">Attributes</span></span>  
  
|<span data-ttu-id="96339-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="96339-111">Attribute</span></span>|<span data-ttu-id="96339-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="96339-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="96339-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="96339-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="96339-114">Indica si PerfCounter.dll usa el valor del Registro CategoryOptions para determinar si se debe cargar los datos del contador de rendimiento de memoria compartida específica de la categoría o la memoria global.</span><span class="sxs-lookup"><span data-stu-id="96339-114">Indicates whether PerfCounter.dll uses the CategoryOptions registry setting to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="96339-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="96339-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="96339-116">Valor</span><span class="sxs-lookup"><span data-stu-id="96339-116">Value</span></span>|<span data-ttu-id="96339-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="96339-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="96339-118">PerfCounter.dll no utiliza el CategoryOptions esta configuración del registro es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="96339-118">PerfCounter.dll does not use the CategoryOptions registry setting This is the default.</span></span>|  
|`true`|<span data-ttu-id="96339-119">PerfCounter.dll usa el valor del Registro CategoryOptions.</span><span class="sxs-lookup"><span data-stu-id="96339-119">PerfCounter.dll does use the CategoryOptions registry setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="96339-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="96339-120">Child Elements</span></span>  
 <span data-ttu-id="96339-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="96339-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="96339-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="96339-122">Parent Elements</span></span>  
  
|<span data-ttu-id="96339-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="96339-123">Element</span></span>|<span data-ttu-id="96339-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="96339-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="96339-125">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="96339-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="96339-126">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="96339-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96339-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="96339-127">Remarks</span></span>  
 <span data-ttu-id="96339-128">En las versiones de .NET Framework anteriores a la [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], la versión de PerfCounter.dll que cargó correspondía a la que se cargó en el proceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="96339-128">In versions of the .NET Framework before the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], the version of PerfCounter.dll that was loaded corresponded to the runtime that was loaded in the process.</span></span> <span data-ttu-id="96339-129">Si un equipo tenía tanto la versión de .NET Framework 1.1 y la [!INCLUDE[dnprdnlong](../../../../../includes/dnprdnlong-md.md)] instalado, una aplicación de .NET Framework 1.1 cargaría la versión de .NET Framework 1.1 de PerfCounter.dll.</span><span class="sxs-lookup"><span data-stu-id="96339-129">If a computer had both the .NET Framework version 1.1 and the [!INCLUDE[dnprdnlong](../../../../../includes/dnprdnlong-md.md)] installed, a .NET Framework 1.1 application would load the .NET Framework 1.1 version of PerfCounter.dll.</span></span> <span data-ttu-id="96339-130">A partir de .NET Framework 4, se carga la versión instalada más reciente de PerfCounter.dll.</span><span class="sxs-lookup"><span data-stu-id="96339-130">Starting with the .NET Framework 4, the newest installed version of PerfCounter.dll is loaded.</span></span> <span data-ttu-id="96339-131">Esto significa que una aplicación de .NET Framework 1.1 cargará la versión de .NET Framework 4 de PerfCounter.dll si .NET Framework 4 está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="96339-131">This means that a .NET Framework 1.1 application will load the .NET Framework 4 version of PerfCounter.dll if the .NET Framework 4 is installed on the computer.</span></span>  
  
 <span data-ttu-id="96339-132">A partir de .NET Framework 4, al consumir los contadores de rendimiento, PerfCounter.dll comprueba la entrada del Registro CategoryOptions de cada proveedor para determinar si debe leer desde la memoria compartida específica de la categoría o la memoria compartida global.</span><span class="sxs-lookup"><span data-stu-id="96339-132">Starting with the .NET Framework 4, when consuming performance counters, PerfCounter.dll checks the CategoryOptions registry entry for each provider to determine whether it should read from category-specific shared memory or global shared memory.</span></span> <span data-ttu-id="96339-133">El PerfCounter.dll de .NET Framework 1.1 no lee esa entrada del registro, porque no es consciente de la memoria compartida específica de la categoría; siempre lee la memoria compartida global.</span><span class="sxs-lookup"><span data-stu-id="96339-133">The .NET Framework 1.1 PerfCounter.dll does not read that registry entry, because it is not aware of category-specific shared memory; it always reads from global shared memory.</span></span>  
  
 <span data-ttu-id="96339-134">Por compatibilidad con versiones anteriores, el PerfCounter.dll de .NET Framework 4 no comprueba la entrada del Registro CategoryOptions al ejecutarse en una aplicación de .NET Framework 1.1.</span><span class="sxs-lookup"><span data-stu-id="96339-134">For backward compatibility, the .NET Framework 4 PerfCounter.dll does not check the CategoryOptions registry entry when running in a .NET Framework 1.1 application.</span></span> <span data-ttu-id="96339-135">Simplemente usa memoria compartida global, al igual que el PerfCounter.dll de .NET Framework 1.1.</span><span class="sxs-lookup"><span data-stu-id="96339-135">It simply uses global shared memory, just like the .NET Framework 1.1 PerfCounter.dll.</span></span> <span data-ttu-id="96339-136">Sin embargo, puede indicar el PerfCounter.dll de .NET Framework 4 para comprobar la configuración del Registro habilitando el `<forcePerformanceCounterUniqueSharedMemoryReads>` elemento.</span><span class="sxs-lookup"><span data-stu-id="96339-136">However, you can instruct the .NET Framework 4 PerfCounter.dll to check the registry setting by enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96339-137">Habilitar la `<forcePerformanceCounterUniqueSharedMemoryReads>` elemento no garantiza que se utilizará memoria compartida específica de la categoría.</span><span class="sxs-lookup"><span data-stu-id="96339-137">Enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element does not guarantee that category-specific shared memory will be used.</span></span> <span data-ttu-id="96339-138">El valor habilitado para `true` sólo hace que PerfCounter.dll hacer referencia a la configuración del Registro CategoryOptions.</span><span class="sxs-lookup"><span data-stu-id="96339-138">Setting enabled to `true` only causes PerfCounter.dll to reference the CategoryOptions registry setting.</span></span> <span data-ttu-id="96339-139">La configuración predeterminada para CategoryOptions es usar la memoria compartida específica de la categoría; Sin embargo, puede cambiar CategoryOptions para indicar que se debe usar la memoria compartida global.</span><span class="sxs-lookup"><span data-stu-id="96339-139">The default setting for CategoryOptions is to use category-specific shared memory; however, you can change CategoryOptions to indicate that global shared memory should be used.</span></span>  
  
 <span data-ttu-id="96339-140">La clave del registro que contiene el valor CategoryOptions es HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\< categoryName\>\Performance.</span><span class="sxs-lookup"><span data-stu-id="96339-140">The registry key that contains the CategoryOptions setting is HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\<categoryName\>\Performance.</span></span> <span data-ttu-id="96339-141">De forma predeterminada, CategoryOptions se establece en 3, que indica a PerfCounter.dll para usar memoria compartida específica de la categoría.</span><span class="sxs-lookup"><span data-stu-id="96339-141">By default, CategoryOptions is set to 3, which instructs PerfCounter.dll to use category-specific shared memory.</span></span> <span data-ttu-id="96339-142">Si CategoryOptions está establecido en 0, PerfCounter.dll usa memoria compartida global.</span><span class="sxs-lookup"><span data-stu-id="96339-142">If CategoryOptions is set to 0, PerfCounter.dll uses global shared memory.</span></span> <span data-ttu-id="96339-143">Datos de instancia se reutilizará solo si el nombre de la instancia que se va a crear es idéntico a la instancia que se va a volver a usar.</span><span class="sxs-lookup"><span data-stu-id="96339-143">Instance data will be reused only if the name of the instance being created is identical to the instance being reused.</span></span> <span data-ttu-id="96339-144">Todas las versiones podrán escribir en la categoría.</span><span class="sxs-lookup"><span data-stu-id="96339-144">All versions will be able to write to the category.</span></span> <span data-ttu-id="96339-145">Si CategoryOptions está establecido en 1, se utiliza la memoria compartida global, pero se pueden reutilizar los datos de instancia si el nombre de categoría es la misma longitud que la categoría que se va a volver a usar.</span><span class="sxs-lookup"><span data-stu-id="96339-145">If CategoryOptions is set to 1, global shared memory is used, but instance data can be reused if the category name is the same length as the category being reused.</span></span>  
  
 <span data-ttu-id="96339-146">Los valores 0 y 1 pueden dar lugar a pérdidas de memoria y el rellenado de la memoria del contador de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="96339-146">The settings 0 and 1 can lead to memory leaks and the filling up of performance counter memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96339-147">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="96339-147">Example</span></span>  
 <span data-ttu-id="96339-148">El ejemplo siguiente muestra cómo especificar que PerfCounter.dll debe hacer referencia a la entrada del Registro CategoryOptions para determinar si debe usar la memoria compartida específica de la categoría.</span><span class="sxs-lookup"><span data-stu-id="96339-148">The following example shows how to specify that PerfCounter.dll should reference the CategoryOptions registry entry to determine whether it should use category-specific shared memory.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="96339-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="96339-149">See also</span></span>

- [<span data-ttu-id="96339-150">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="96339-150">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="96339-151">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="96339-151">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
