---
title: <forcePerformanceCounterUniqueSharedMemoryReads> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
ms.openlocfilehash: 742b444c445ba67d6977b622e615a6a8f591826e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154145"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a><span data-ttu-id="47cea-102">\<forcePerformanceCounterUniqueSharedMemoryReads> Element</span><span class="sxs-lookup"><span data-stu-id="47cea-102">\<forcePerformanceCounterUniqueSharedMemoryReads> Element</span></span>
<span data-ttu-id="47cea-103">Especifica si PerfCounter.dll usa la configuración del Registro CategoryOptions en una aplicación de .NET Framework 1.1 para determinar si se van a cargar los datos del contador de rendimiento desde la memoria compartida específica de la categoría o la memoria global.</span><span class="sxs-lookup"><span data-stu-id="47cea-103">Specifies whether PerfCounter.dll uses the CategoryOptions registry setting in a .NET Framework version 1.1 application to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>  
  
<span data-ttu-id="47cea-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="47cea-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="47cea-105">&nbsp;&nbsp;[**\<>en tiempo de ejecución**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="47cea-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="47cea-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<forcePerformanceCounterUniqueSharedMemoryReads>**</span><span class="sxs-lookup"><span data-stu-id="47cea-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<forcePerformanceCounterUniqueSharedMemoryReads>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47cea-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47cea-107">Syntax</span></span>  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="47cea-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="47cea-108">Attributes and Elements</span></span>  
 <span data-ttu-id="47cea-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="47cea-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="47cea-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="47cea-110">Attributes</span></span>  
  
|<span data-ttu-id="47cea-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="47cea-111">Attribute</span></span>|<span data-ttu-id="47cea-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="47cea-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="47cea-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="47cea-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="47cea-114">Indica si PerfCounter.dll usa la configuración del Registro CategoryOptions para determinar si se deben cargar datos del contador de rendimiento desde memoria compartida específica de categoría o memoria global.</span><span class="sxs-lookup"><span data-stu-id="47cea-114">Indicates whether PerfCounter.dll uses the CategoryOptions registry setting to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="47cea-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="47cea-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="47cea-116">Value</span><span class="sxs-lookup"><span data-stu-id="47cea-116">Value</span></span>|<span data-ttu-id="47cea-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="47cea-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="47cea-118">PerfCounter.dll no usa la configuración del Registro CategoryOptions Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="47cea-118">PerfCounter.dll does not use the CategoryOptions registry setting This is the default.</span></span>|  
|`true`|<span data-ttu-id="47cea-119">PerfCounter.dll utiliza la configuración del Registro CategoryOptions.</span><span class="sxs-lookup"><span data-stu-id="47cea-119">PerfCounter.dll does use the CategoryOptions registry setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="47cea-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="47cea-120">Child Elements</span></span>  
 <span data-ttu-id="47cea-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="47cea-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="47cea-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="47cea-122">Parent Elements</span></span>  
  
|<span data-ttu-id="47cea-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="47cea-123">Element</span></span>|<span data-ttu-id="47cea-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="47cea-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="47cea-125">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="47cea-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="47cea-126">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="47cea-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47cea-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="47cea-127">Remarks</span></span>  
 <span data-ttu-id="47cea-128">En las versiones de .NET Framework anteriores a .NET Framework 4, la versión de PerfCounter.dll que se cargó correspondía al tiempo de ejecución que se cargó en el proceso.</span><span class="sxs-lookup"><span data-stu-id="47cea-128">In versions of the .NET Framework before the .NET Framework 4, the version of PerfCounter.dll that was loaded corresponded to the runtime that was loaded in the process.</span></span> <span data-ttu-id="47cea-129">Si un equipo tuviera instalada la versión 1.1 de .NET Framework y .NET Framework 2.0, una aplicación de .NET Framework 1.1 cargaría la versión de PerfCounter.dll de .NET Framework 1.1.</span><span class="sxs-lookup"><span data-stu-id="47cea-129">If a computer had both the .NET Framework version 1.1 and the .NET Framework 2.0 installed, a .NET Framework 1.1 application would load the .NET Framework 1.1 version of PerfCounter.dll.</span></span> <span data-ttu-id="47cea-130">A partir de .NET Framework 4, se carga la versión instalada más reciente de PerfCounter.dll.</span><span class="sxs-lookup"><span data-stu-id="47cea-130">Starting with the .NET Framework 4, the newest installed version of PerfCounter.dll is loaded.</span></span> <span data-ttu-id="47cea-131">Esto significa que una aplicación de .NET Framework 1.1 cargará la versión de .NET Framework 4 de PerfCounter.dll si .NET Framework 4 está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="47cea-131">This means that a .NET Framework 1.1 application will load the .NET Framework 4 version of PerfCounter.dll if the .NET Framework 4 is installed on the computer.</span></span>  
  
 <span data-ttu-id="47cea-132">A partir de .NET Framework 4, al consumir contadores de rendimiento, PerfCounter.dll comprueba la entrada del Registro CategoryOptions para cada proveedor para determinar si debe leer desde memoria compartida específica de categoría o memoria compartida global.</span><span class="sxs-lookup"><span data-stu-id="47cea-132">Starting with the .NET Framework 4, when consuming performance counters, PerfCounter.dll checks the CategoryOptions registry entry for each provider to determine whether it should read from category-specific shared memory or global shared memory.</span></span> <span data-ttu-id="47cea-133">.NET Framework 1.1 PerfCounter.dll no lee esa entrada del Registro, porque no es consciente de la memoria compartida específica de la categoría; siempre lee de la memoria compartida global.</span><span class="sxs-lookup"><span data-stu-id="47cea-133">The .NET Framework 1.1 PerfCounter.dll does not read that registry entry, because it is not aware of category-specific shared memory; it always reads from global shared memory.</span></span>  
  
 <span data-ttu-id="47cea-134">Por compatibilidad con versiones anteriores, .NET Framework 4 PerfCounter.dll no comprueba la entrada del Registro CategoryOptions cuando se ejecuta en una aplicación de .NET Framework 1.1.</span><span class="sxs-lookup"><span data-stu-id="47cea-134">For backward compatibility, the .NET Framework 4 PerfCounter.dll does not check the CategoryOptions registry entry when running in a .NET Framework 1.1 application.</span></span> <span data-ttu-id="47cea-135">Simplemente usa memoria compartida global, al igual que .NET Framework 1.1 PerfCounter.dll.</span><span class="sxs-lookup"><span data-stu-id="47cea-135">It simply uses global shared memory, just like the .NET Framework 1.1 PerfCounter.dll.</span></span> <span data-ttu-id="47cea-136">Sin embargo, puede indicar a .NET Framework 4 PerfCounter.dll que compruebe la configuración del Registro habilitando el `<forcePerformanceCounterUniqueSharedMemoryReads>` elemento.</span><span class="sxs-lookup"><span data-stu-id="47cea-136">However, you can instruct the .NET Framework 4 PerfCounter.dll to check the registry setting by enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="47cea-137">Habilitar `<forcePerformanceCounterUniqueSharedMemoryReads>` el elemento no garantiza que se usará la memoria compartida específica de la categoría.</span><span class="sxs-lookup"><span data-stu-id="47cea-137">Enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element does not guarantee that category-specific shared memory will be used.</span></span> <span data-ttu-id="47cea-138">Establecer habilitado `true` solo hace que PerfCounter.dll haga referencia a la configuración del Registro CategoryOptions.</span><span class="sxs-lookup"><span data-stu-id="47cea-138">Setting enabled to `true` only causes PerfCounter.dll to reference the CategoryOptions registry setting.</span></span> <span data-ttu-id="47cea-139">La configuración predeterminada para CategoryOptions es usar memoria compartida específica de categoría; sin embargo, puede cambiar CategoryOptions para indicar que se debe usar la memoria compartida global.</span><span class="sxs-lookup"><span data-stu-id="47cea-139">The default setting for CategoryOptions is to use category-specific shared memory; however, you can change CategoryOptions to indicate that global shared memory should be used.</span></span>  
  
 <span data-ttu-id="47cea-140">La clave del Registro que contiene la configuración de CategoryOptions se HKEY_LOCAL_MACHINE, System, CurrentControlSet, Services\\<nombredecategoría\>.</span><span class="sxs-lookup"><span data-stu-id="47cea-140">The registry key that contains the CategoryOptions setting is HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\<categoryName\>\Performance.</span></span> <span data-ttu-id="47cea-141">De forma predeterminada, CategoryOptions se establece en 3, lo que indica a PerfCounter.dll que use memoria compartida específica de la categoría.</span><span class="sxs-lookup"><span data-stu-id="47cea-141">By default, CategoryOptions is set to 3, which instructs PerfCounter.dll to use category-specific shared memory.</span></span> <span data-ttu-id="47cea-142">Si CategoryOptions se establece en 0, PerfCounter.dll utiliza memoria compartida global.</span><span class="sxs-lookup"><span data-stu-id="47cea-142">If CategoryOptions is set to 0, PerfCounter.dll uses global shared memory.</span></span> <span data-ttu-id="47cea-143">Los datos de instancia solo se reutilizarán si el nombre de la instancia que se está creando es idéntico a la instancia que se está reutilizando.</span><span class="sxs-lookup"><span data-stu-id="47cea-143">Instance data will be reused only if the name of the instance being created is identical to the instance being reused.</span></span> <span data-ttu-id="47cea-144">Todas las versiones podrán escribir en la categoría.</span><span class="sxs-lookup"><span data-stu-id="47cea-144">All versions will be able to write to the category.</span></span> <span data-ttu-id="47cea-145">Si CategoryOptions se establece en 1, se utiliza la memoria compartida global, pero los datos de instancia se pueden reutilizar si el nombre de categoría tiene la misma longitud que la categoría que se reutiliza.</span><span class="sxs-lookup"><span data-stu-id="47cea-145">If CategoryOptions is set to 1, global shared memory is used, but instance data can be reused if the category name is the same length as the category being reused.</span></span>  
  
 <span data-ttu-id="47cea-146">Los ajustes 0 y 1 pueden provocar pérdidas de memoria y el llenado de la memoria del contador de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="47cea-146">The settings 0 and 1 can lead to memory leaks and the filling up of performance counter memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47cea-147">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="47cea-147">Example</span></span>  
 <span data-ttu-id="47cea-148">En el ejemplo siguiente se muestra cómo especificar que PerfCounter.dll debe hacer referencia a la entrada del Registro CategoryOptions para determinar si debe usar memoria compartida específica de categoría.</span><span class="sxs-lookup"><span data-stu-id="47cea-148">The following example shows how to specify that PerfCounter.dll should reference the CategoryOptions registry entry to determine whether it should use category-specific shared memory.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="47cea-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="47cea-149">See also</span></span>

- [<span data-ttu-id="47cea-150">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="47cea-150">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="47cea-151">Esquema del archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="47cea-151">Configuration File Schema</span></span>](../index.md)
