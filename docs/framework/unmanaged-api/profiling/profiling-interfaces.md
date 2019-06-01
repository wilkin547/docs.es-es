---
title: Interfaces para generación de perfiles
ms.date: 04/10/2018
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], profiling
- profiling interfaces [.NET Framework]
- interfaces [.NET Framework profiling]
ms.assetid: d9303db8-e881-4217-91b7-8c7573c8ef9e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d97960a43e1d7ce625d96755a7c597a0425d0911
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2019
ms.locfileid: "66457465"
---
# <a name="profiling-interfaces"></a><span data-ttu-id="054b9-102">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="054b9-102">Profiling Interfaces</span></span>
<span data-ttu-id="054b9-103">En esta sección se describen las interfaces no administradas que permiten generar perfiles para un programa que se ejecuta en Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="054b9-103">This section describes the unmanaged interfaces that enable you to profile a program that is being executed by the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="054b9-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="054b9-104">In This Section</span></span>  
 [<span data-ttu-id="054b9-105">ICLRProfiling (interfaz)</span><span class="sxs-lookup"><span data-stu-id="054b9-105">ICLRProfiling Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-interface.md)  
 <span data-ttu-id="054b9-106">Proporciona el [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) método, que permite a un generador de perfiles adjuntar a un proceso en ejecución.</span><span class="sxs-lookup"><span data-stu-id="054b9-106">Provides the [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) method, which enables a profiler to attach to a running process.</span></span>  
  
 [<span data-ttu-id="054b9-107">ICorProfilerAssemblyReferenceProvider (interfaz)</span><span class="sxs-lookup"><span data-stu-id="054b9-107">ICorProfilerAssemblyReferenceProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)  
 <span data-ttu-id="054b9-108">Permite que el generador de perfiles informar a CLR de referencias de ensamblado que el generador de perfiles agregará en el [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="054b9-108">Enables the profiler to inform the CLR of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
 [<span data-ttu-id="054b9-109">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="054b9-109">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 <span data-ttu-id="054b9-110">Proporciona métodos que CLR usa para notificar a un generador de perfiles de código cuando se produzcan los eventos a los que se ha suscrito el generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="054b9-110">Provides methods that are used by the CLR to notify a code profiler when the events to which the profiler has subscribed occur.</span></span>  
  
 [<span data-ttu-id="054b9-111">ICorProfilerCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="054b9-111">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 <span data-ttu-id="054b9-112">Extiende la interfaz `ICorProfilerCallback` con las devoluciones de llamada admitidas en .NET Framework 2.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="054b9-112">Extends the `ICorProfilerCallback` interface with callbacks supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="054b9-113">ICorProfilerCallback3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="054b9-113">ICorProfilerCallback3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)  
 <span data-ttu-id="054b9-114">Proporciona métodos de devolución de llamada que CLR usa para comunicar la información sobre el estado de asociación y desasociación al generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="054b9-114">Provides callback methods that the CLR uses to communicate attach and detach state information to the profiler.</span></span>  
  
 [<span data-ttu-id="054b9-115">ICorProfilerCallback4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="054b9-115">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 <span data-ttu-id="054b9-116">Proporciona métodos de devolución de llamada que CLR usa para comunicar la información al generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="054b9-116">Provides callback methods that the CLR uses to communicate information to the profiler.</span></span>  
  
 [<span data-ttu-id="054b9-117">ICorProfilerCallback5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="054b9-117">ICorProfilerCallback5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md)  
 <span data-ttu-id="054b9-118">Proporciona un método que identifica el cierre transitivo de los objetos a los que hacen referencia las raíces de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="054b9-118">Provides a method that identifies the transitive closure of objects referenced by garbage collection roots.</span></span>  
  
 [<span data-ttu-id="054b9-119">ICorProfilerCallback6 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="054b9-119">ICorProfilerCallback6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md)  
 <span data-ttu-id="054b9-120">Proporciona un método de devolución de llamada que CLR usa para notificar a un generador de perfiles que un ensamblado se está cargando.</span><span class="sxs-lookup"><span data-stu-id="054b9-120">Provides a callback method that the CLR uses to notify a profiler that an assembly is loading.</span></span>  
  
 [<span data-ttu-id="054b9-121">ICorProfilerCallback7 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="054b9-121">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)  
 <span data-ttu-id="054b9-122">Proporciona un método de devolución de llamada que common language runtime utiliza para notificar que el generador de perfiles que se ha actualizado la secuencia de símbolos asociada a un módulo en memoria.</span><span class="sxs-lookup"><span data-stu-id="054b9-122">Provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  

[<span data-ttu-id="054b9-123">ICorProfilerCallback8 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="054b9-123">ICorProfilerCallback8 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback8-interface.md)  
<span data-ttu-id="054b9-124">Proporciona métodos de devolución de llamada que common language runtime utiliza para notificar al generador de perfiles que se ha iniciado y finalizado la compilación JIT de un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="054b9-124">Provides callback methods that the common language runtime uses to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span>

[<span data-ttu-id="054b9-125">ICorProfilerCallback9 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="054b9-125">ICorProfilerCallback9 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback9-interface.md)  
<span data-ttu-id="054b9-126">Proporciona un método de devolución de llamada que common language runtime utiliza para notificar al generador de perfiles que un método dinámico es recolectado y posteriormente descargan.</span><span class="sxs-lookup"><span data-stu-id="054b9-126">Provides a callback method that the common language runtime uses to notify the profiler that a dynamic method is garbage collected and subsequently unloaded.</span></span>

 [<span data-ttu-id="054b9-127">ICorProfilerFunctionControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="054b9-127">ICorProfilerFunctionControl Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)  
 <span data-ttu-id="054b9-128">Proporciona métodos que permiten a un generador de perfiles de código comunicarse con CLR para controlar cómo debe generar el código el compilador JIT cuando vuelva a compilar un método específico.</span><span class="sxs-lookup"><span data-stu-id="054b9-128">Provides methods that allow a code profiler to communicate with the CLR to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
 [<span data-ttu-id="054b9-129">ICorProfilerFunctionEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="054b9-129">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 <span data-ttu-id="054b9-130">Proporciona métodos para iterar secuencialmente por una colección de funciones en CLR.</span><span class="sxs-lookup"><span data-stu-id="054b9-130">Provides methods to sequentially iterate through a collection of functions in the CLR.</span></span>  
  
 [<span data-ttu-id="054b9-131">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="054b9-131">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 <span data-ttu-id="054b9-132">Proporciona métodos que los generadores de perfiles de código usan para comunicarse con CLR para controlar la supervisión de eventos y para solicitar información.</span><span class="sxs-lookup"><span data-stu-id="054b9-132">Provides methods for use by code profilers to communicate with the CLR to control event monitoring and request information.</span></span>  
  
 [<span data-ttu-id="054b9-133">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="054b9-133">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 <span data-ttu-id="054b9-134">Extiende la interfaz `ICorProfilerInfo` con los métodos admitidos en .NET Framework 2.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="054b9-134">Extends the `ICorProfilerInfo` interface with methods supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="054b9-135">ICorProfilerInfo3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="054b9-135">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 <span data-ttu-id="054b9-136">Extiende la `ICorProfilerInfo2` interfaz con los métodos admitidos en .NET Framework 4 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="054b9-136">Extends the `ICorProfilerInfo2` interface with methods supported in the .NET Framework 4 and later versions.</span></span>  
  
 [<span data-ttu-id="054b9-137">ICorProfilerInfo4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="054b9-137">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 <span data-ttu-id="054b9-138">Proporciona métodos que los generadores de perfiles de código usan para comunicarse con CLR para controlar la supervisión de eventos y para solicitar información.</span><span class="sxs-lookup"><span data-stu-id="054b9-138">Provides methods that code profilers use to communicate with the CLR to control event monitoring and to request information.</span></span>  
  
 [<span data-ttu-id="054b9-139">ICorProfilerInfo5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="054b9-139">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)  
 <span data-ttu-id="054b9-140">Proporciona métodos que los generadores de perfiles de código usan para comunicarse con CLR para controlar la supervisión de eventos.</span><span class="sxs-lookup"><span data-stu-id="054b9-140">Provides methods for use by code profilers to communicate with the CLR to control event monitoring.</span></span>  
  
 [<span data-ttu-id="054b9-141">ICorProfilerInfo6 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="054b9-141">ICorProfilerInfo6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)  
 <span data-ttu-id="054b9-142">Proporciona un enumerador para todos los métodos que pertenecen a un módulo NGen determinado y que se alinean en el cuerpo de un método determinado.</span><span class="sxs-lookup"><span data-stu-id="054b9-142">Provides an enumerator to all the methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>  
  
 [<span data-ttu-id="054b9-143">ICorProfilerInfo7 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="054b9-143">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)  
 <span data-ttu-id="054b9-144">Proporciona un método para aplicar recién definido los metadatos para un módulo y que proporciona acceso a una secuencia de símbolos en memoria.</span><span class="sxs-lookup"><span data-stu-id="054b9-144">Provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
 [<span data-ttu-id="054b9-145">ICorProfilerModuleEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="054b9-145">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 <span data-ttu-id="054b9-146">Proporciona métodos para iterar secuencialmente por una colección de módulos cargados por la aplicación o por el generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="054b9-146">Provides methods to sequentially iterate through a collection of modules loaded by the application or the profiler.</span></span>  
  
 [<span data-ttu-id="054b9-147">ICorProfilerObjectEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="054b9-147">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)  
 <span data-ttu-id="054b9-148">Proporciona métodos para iterar secuencialmente por una colección de objetos congelados generados por [Ngen.exe (Native Image Generator)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span><span class="sxs-lookup"><span data-stu-id="054b9-148">Provides methods to sequentially iterate through a collection of frozen objects that are generated by [Ngen.exe (Native Image Generator)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span></span>  
  
 [<span data-ttu-id="054b9-149">ICorProfilerThreadEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="054b9-149">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 <span data-ttu-id="054b9-150">Proporciona métodos para iterar secuencialmente por una colección de subprocesos en CLR.</span><span class="sxs-lookup"><span data-stu-id="054b9-150">Provides methods to sequentially iterate through a collection of threads in the CLR.</span></span>  
  
 [<span data-ttu-id="054b9-151">IMethodMalloc (interfaz)</span><span class="sxs-lookup"><span data-stu-id="054b9-151">IMethodMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)  
 <span data-ttu-id="054b9-152">Proporciona el [Alloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md) método para asignar memoria para un nuevo cuerpo de función de lenguaje intermedio (MSIL) de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="054b9-152">Provides the [Alloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md) method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="054b9-153">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="054b9-153">Related Sections</span></span>  
 [<span data-ttu-id="054b9-154">Información general sobre la generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="054b9-154">Profiling Overview</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [<span data-ttu-id="054b9-155">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="054b9-155">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [<span data-ttu-id="054b9-156">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="054b9-156">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
  
 [<span data-ttu-id="054b9-157">Estructuras para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="054b9-157">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
