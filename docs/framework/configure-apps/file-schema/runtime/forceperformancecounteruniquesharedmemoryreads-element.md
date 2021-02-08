---
description: 'Más información acerca de: <forcePerformanceCounterUniqueSharedMemoryReads> elemento'
title: <forcePerformanceCounterUniqueSharedMemoryReads> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
ms.openlocfilehash: 63fe695cc993faa851a9ea3196294397d2992c45
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787037"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a><span data-ttu-id="02c00-103">\<forcePerformanceCounterUniqueSharedMemoryReads> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="02c00-103">\<forcePerformanceCounterUniqueSharedMemoryReads> Element</span></span>

<span data-ttu-id="02c00-104">Especifica si PerfCounter.dll usa la configuración del Registro CategoryOptions en una aplicación de .NET Framework 1.1 para determinar si se van a cargar los datos del contador de rendimiento desde la memoria compartida específica de la categoría o la memoria global.</span><span class="sxs-lookup"><span data-stu-id="02c00-104">Specifies whether PerfCounter.dll uses the CategoryOptions registry setting in a .NET Framework version 1.1 application to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<forcePerformanceCounterUniqueSharedMemoryReads>**  
  
## <a name="syntax"></a><span data-ttu-id="02c00-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02c00-105">Syntax</span></span>  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02c00-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="02c00-106">Attributes and Elements</span></span>  

 <span data-ttu-id="02c00-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="02c00-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02c00-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="02c00-108">Attributes</span></span>  
  
|<span data-ttu-id="02c00-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="02c00-109">Attribute</span></span>|<span data-ttu-id="02c00-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="02c00-110">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="02c00-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="02c00-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="02c00-112">Indica si PerfCounter.dll usa la configuración del Registro CategoryOptions para determinar si se van a cargar los datos del contador de rendimiento de la memoria compartida específica de la categoría o de la memoria global.</span><span class="sxs-lookup"><span data-stu-id="02c00-112">Indicates whether PerfCounter.dll uses the CategoryOptions registry setting to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="02c00-113">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="02c00-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="02c00-114">Value</span><span class="sxs-lookup"><span data-stu-id="02c00-114">Value</span></span>|<span data-ttu-id="02c00-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="02c00-115">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="02c00-116">PerfCounter.dll no usa el valor del Registro CategoryOptions es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="02c00-116">PerfCounter.dll does not use the CategoryOptions registry setting This is the default.</span></span>|  
|`true`|<span data-ttu-id="02c00-117">PerfCounter.dll usa la configuración del Registro CategoryOptions.</span><span class="sxs-lookup"><span data-stu-id="02c00-117">PerfCounter.dll does use the CategoryOptions registry setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="02c00-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="02c00-118">Child Elements</span></span>  

 <span data-ttu-id="02c00-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="02c00-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="02c00-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="02c00-120">Parent Elements</span></span>  
  
|<span data-ttu-id="02c00-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="02c00-121">Element</span></span>|<span data-ttu-id="02c00-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="02c00-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="02c00-123">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="02c00-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="02c00-124">Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="02c00-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02c00-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="02c00-125">Remarks</span></span>  

 <span data-ttu-id="02c00-126">En las versiones de la .NET Framework antes del .NET Framework 4, la versión de PerfCounter.dll que se cargó correspondía al tiempo de ejecución que se cargó en el proceso.</span><span class="sxs-lookup"><span data-stu-id="02c00-126">In versions of the .NET Framework before the .NET Framework 4, the version of PerfCounter.dll that was loaded corresponded to the runtime that was loaded in the process.</span></span> <span data-ttu-id="02c00-127">Si un equipo tenía la .NET Framework la versión 1,1 y el .NET Framework 2,0 instalado, una aplicación .NET Framework 1,1 cargaría la versión .NET Framework 1,1 de PerfCounter.dll.</span><span class="sxs-lookup"><span data-stu-id="02c00-127">If a computer had both the .NET Framework version 1.1 and the .NET Framework 2.0 installed, a .NET Framework 1.1 application would load the .NET Framework 1.1 version of PerfCounter.dll.</span></span> <span data-ttu-id="02c00-128">A partir de la .NET Framework 4, se carga la versión más reciente instalada de PerfCounter.dll.</span><span class="sxs-lookup"><span data-stu-id="02c00-128">Starting with the .NET Framework 4, the newest installed version of PerfCounter.dll is loaded.</span></span> <span data-ttu-id="02c00-129">Esto significa que una aplicación .NET Framework 1,1 cargará la versión .NET Framework 4 de PerfCounter.dll si .NET Framework 4 está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="02c00-129">This means that a .NET Framework 1.1 application will load the .NET Framework 4 version of PerfCounter.dll if the .NET Framework 4 is installed on the computer.</span></span>  
  
 <span data-ttu-id="02c00-130">A partir de la .NET Framework 4, cuando se usan contadores de rendimiento, PerfCounter.dll comprueba la entrada del registro de CategoryOptions para cada proveedor para determinar si debe leer la memoria compartida específica de la categoría o la memoria compartida global.</span><span class="sxs-lookup"><span data-stu-id="02c00-130">Starting with the .NET Framework 4, when consuming performance counters, PerfCounter.dll checks the CategoryOptions registry entry for each provider to determine whether it should read from category-specific shared memory or global shared memory.</span></span> <span data-ttu-id="02c00-131">El PerfCounter.dll .NET Framework 1,1 no lee la entrada del registro, ya que no es consciente de la memoria compartida específica de la categoría. siempre lee de la memoria compartida global.</span><span class="sxs-lookup"><span data-stu-id="02c00-131">The .NET Framework 1.1 PerfCounter.dll does not read that registry entry, because it is not aware of category-specific shared memory; it always reads from global shared memory.</span></span>  
  
 <span data-ttu-id="02c00-132">Por compatibilidad con versiones anteriores, el PerfCounter.dll de .NET Framework 4 no comprueba la entrada del registro de CategoryOptions cuando se ejecuta en una aplicación .NET Framework 1,1.</span><span class="sxs-lookup"><span data-stu-id="02c00-132">For backward compatibility, the .NET Framework 4 PerfCounter.dll does not check the CategoryOptions registry entry when running in a .NET Framework 1.1 application.</span></span> <span data-ttu-id="02c00-133">Simplemente usa la memoria compartida global, al igual que el .NET Framework 1,1 PerfCounter.dll.</span><span class="sxs-lookup"><span data-stu-id="02c00-133">It simply uses global shared memory, just like the .NET Framework 1.1 PerfCounter.dll.</span></span> <span data-ttu-id="02c00-134">Sin embargo, puede indicar al PerfCounter.dll de .NET Framework 4 que Compruebe la configuración del registro habilitando el `<forcePerformanceCounterUniqueSharedMemoryReads>` elemento.</span><span class="sxs-lookup"><span data-stu-id="02c00-134">However, you can instruct the .NET Framework 4 PerfCounter.dll to check the registry setting by enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="02c00-135">Al habilitar el elemento no se `<forcePerformanceCounterUniqueSharedMemoryReads>` garantiza que se utilice la memoria compartida específica de la categoría.</span><span class="sxs-lookup"><span data-stu-id="02c00-135">Enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element does not guarantee that category-specific shared memory will be used.</span></span> <span data-ttu-id="02c00-136">Establecer habilitado `true` solo hace que PerfCounter.dll haga referencia al valor del Registro CategoryOptions.</span><span class="sxs-lookup"><span data-stu-id="02c00-136">Setting enabled to `true` only causes PerfCounter.dll to reference the CategoryOptions registry setting.</span></span> <span data-ttu-id="02c00-137">La configuración predeterminada de CategoryOptions es usar la memoria compartida específica de la categoría. sin embargo, puede cambiar CategoryOptions para indicar que se debe usar la memoria compartida global.</span><span class="sxs-lookup"><span data-stu-id="02c00-137">The default setting for CategoryOptions is to use category-specific shared memory; however, you can change CategoryOptions to indicate that global shared memory should be used.</span></span>  
  
 <span data-ttu-id="02c00-138">La clave del registro que contiene el valor de CategoryOptions es HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\<categoryName \> \Performance.</span><span class="sxs-lookup"><span data-stu-id="02c00-138">The registry key that contains the CategoryOptions setting is HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\<categoryName\>\Performance.</span></span> <span data-ttu-id="02c00-139">De forma predeterminada, CategoryOptions se establece en 3, lo que indica a PerfCounter.dll que use la memoria compartida específica de la categoría.</span><span class="sxs-lookup"><span data-stu-id="02c00-139">By default, CategoryOptions is set to 3, which instructs PerfCounter.dll to use category-specific shared memory.</span></span> <span data-ttu-id="02c00-140">Si CategoryOptions se establece en 0, PerfCounter.dll usa la memoria compartida global.</span><span class="sxs-lookup"><span data-stu-id="02c00-140">If CategoryOptions is set to 0, PerfCounter.dll uses global shared memory.</span></span> <span data-ttu-id="02c00-141">Los datos de instancia se reutilizarán solo si el nombre de la instancia que se va a crear es idéntico a la instancia que se va a reutilizar.</span><span class="sxs-lookup"><span data-stu-id="02c00-141">Instance data will be reused only if the name of the instance being created is identical to the instance being reused.</span></span> <span data-ttu-id="02c00-142">Todas las versiones podrán escribir en la categoría.</span><span class="sxs-lookup"><span data-stu-id="02c00-142">All versions will be able to write to the category.</span></span> <span data-ttu-id="02c00-143">Si CategoryOptions está establecido en 1, se usa la memoria compartida global, pero se pueden volver a usar los datos de instancia si el nombre de la categoría tiene la misma longitud que la categoría que se va a reutilizar.</span><span class="sxs-lookup"><span data-stu-id="02c00-143">If CategoryOptions is set to 1, global shared memory is used, but instance data can be reused if the category name is the same length as the category being reused.</span></span>  
  
 <span data-ttu-id="02c00-144">Los valores 0 y 1 pueden dar lugar a pérdidas de memoria y al rellenar la memoria del contador de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="02c00-144">The settings 0 and 1 can lead to memory leaks and the filling up of performance counter memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02c00-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="02c00-145">Example</span></span>  

 <span data-ttu-id="02c00-146">En el ejemplo siguiente se muestra cómo especificar que PerfCounter.dll debe hacer referencia a la entrada del Registro CategoryOptions para determinar si debe usar la memoria compartida específica de la categoría.</span><span class="sxs-lookup"><span data-stu-id="02c00-146">The following example shows how to specify that PerfCounter.dll should reference the CategoryOptions registry entry to determine whether it should use category-specific shared memory.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="02c00-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="02c00-147">See also</span></span>

- [<span data-ttu-id="02c00-148">Esquema de la configuración de Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="02c00-148">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="02c00-149">Esquema de los archivos de configuración</span><span class="sxs-lookup"><span data-stu-id="02c00-149">Configuration File Schema</span></span>](../index.md)
