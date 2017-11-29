---
title: "Interfaces para generación de perfiles"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], profiling
- profiling interfaces [.NET Framework]
- interfaces [.NET Framework profiling]
ms.assetid: d9303db8-e881-4217-91b7-8c7573c8ef9e
caps.latest.revision: "31"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5c0423f9c8b01c1289e1107c0c16c59968a6e2a4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="profiling-interfaces"></a><span data-ttu-id="f9e9c-102">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="f9e9c-102">Profiling Interfaces</span></span>
<span data-ttu-id="f9e9c-103">En esta sección se describen las interfaces no administradas que permiten generar perfiles para un programa que se ejecuta en Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="f9e9c-103">This section describes the unmanaged interfaces that enable you to profile a program that is being executed by the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f9e9c-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f9e9c-104">In This Section</span></span>  
 [<span data-ttu-id="f9e9c-105">ICLRProfiling (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f9e9c-105">ICLRProfiling Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-interface.md)  
 <span data-ttu-id="f9e9c-106">Proporciona el [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) método, lo que permite a un generador de perfiles adjuntar a un proceso en ejecución.</span><span class="sxs-lookup"><span data-stu-id="f9e9c-106">Provides the [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) method, which enables a profiler to attach to a running process.</span></span>  
  
 [<span data-ttu-id="f9e9c-107">ICorProfilerAssemblyReferenceProvider (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f9e9c-107">ICorProfilerAssemblyReferenceProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)  
 <span data-ttu-id="f9e9c-108">Permite al generador de perfiles informar a CLR de referencias de ensamblado que el generador de perfiles agregará en el [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="f9e9c-108">Enables the profiler to inform the CLR of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
 [<span data-ttu-id="f9e9c-109">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f9e9c-109">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 <span data-ttu-id="f9e9c-110">Proporciona métodos que CLR usa para notificar a un generador de perfiles de código cuando se produzcan los eventos a los que se ha suscrito el generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="f9e9c-110">Provides methods that are used by the CLR to notify a code profiler when the events to which the profiler has subscribed occur.</span></span>  
  
 [<span data-ttu-id="f9e9c-111">ICorProfilerCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f9e9c-111">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 <span data-ttu-id="f9e9c-112">Extiende la interfaz `ICorProfilerCallback` con las devoluciones de llamada admitidas en .NET Framework 2.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="f9e9c-112">Extends the `ICorProfilerCallback` interface with callbacks supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="f9e9c-113">ICorProfilerCallback3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f9e9c-113">ICorProfilerCallback3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)  
 <span data-ttu-id="f9e9c-114">Proporciona métodos de devolución de llamada que CLR usa para comunicar la información sobre el estado de asociación y desasociación al generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="f9e9c-114">Provides callback methods that the CLR uses to communicate attach and detach state information to the profiler.</span></span>  
  
 [<span data-ttu-id="f9e9c-115">ICorProfilerCallback4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f9e9c-115">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 <span data-ttu-id="f9e9c-116">Proporciona métodos de devolución de llamada que CLR usa para comunicar la información al generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="f9e9c-116">Provides callback methods that the CLR uses to communicate information to the profiler.</span></span>  
  
 [<span data-ttu-id="f9e9c-117">ICorProfilerCallback5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f9e9c-117">ICorProfilerCallback5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md)  
 <span data-ttu-id="f9e9c-118">Proporciona un método que identifica el cierre transitivo de los objetos a los que hacen referencia las raíces de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="f9e9c-118">Provides a method that identifies the transitive closure of objects referenced by garbage collection roots.</span></span>  
  
 [<span data-ttu-id="f9e9c-119">ICorProfilerCallback6 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f9e9c-119">ICorProfilerCallback6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md)  
 <span data-ttu-id="f9e9c-120">Proporciona un método de devolución de llamada que CLR usa para notificar a un generador de perfiles que un ensamblado se está cargando.</span><span class="sxs-lookup"><span data-stu-id="f9e9c-120">Provides a callback method that the CLR uses to notify a profiler that an assembly is loading.</span></span>  
  
 [<span data-ttu-id="f9e9c-121">Interfaz ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="f9e9c-121">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)  
 <span data-ttu-id="f9e9c-122">Proporciona un método de devolución de llamada que common language runtime utiliza para notificar al generador de perfiles que se actualiza la secuencia de símbolos asociada a un módulo en memoria.</span><span class="sxs-lookup"><span data-stu-id="f9e9c-122">Provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  
  
 [<span data-ttu-id="f9e9c-123">ICorProfilerFunctionControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f9e9c-123">ICorProfilerFunctionControl Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)  
 <span data-ttu-id="f9e9c-124">Proporciona métodos que permiten a un generador de perfiles de código comunicarse con CLR para controlar cómo debe generar el código el compilador JIT cuando vuelva a compilar un método específico.</span><span class="sxs-lookup"><span data-stu-id="f9e9c-124">Provides methods that allow a code profiler to communicate with the CLR to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
 [<span data-ttu-id="f9e9c-125">ICorProfilerFunctionEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f9e9c-125">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 <span data-ttu-id="f9e9c-126">Proporciona métodos para iterar secuencialmente por una colección de funciones en CLR.</span><span class="sxs-lookup"><span data-stu-id="f9e9c-126">Provides methods to sequentially iterate through a collection of functions in the CLR.</span></span>  
  
 [<span data-ttu-id="f9e9c-127">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f9e9c-127">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 <span data-ttu-id="f9e9c-128">Proporciona métodos que los generadores de perfiles de código usan para comunicarse con CLR para controlar la supervisión de eventos y para solicitar información.</span><span class="sxs-lookup"><span data-stu-id="f9e9c-128">Provides methods for use by code profilers to communicate with the CLR to control event monitoring and request information.</span></span>  
  
 [<span data-ttu-id="f9e9c-129">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f9e9c-129">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 <span data-ttu-id="f9e9c-130">Extiende la interfaz `ICorProfilerInfo` con los métodos admitidos en .NET Framework 2.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="f9e9c-130">Extends the `ICorProfilerInfo` interface with methods supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="f9e9c-131">ICorProfilerInfo3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f9e9c-131">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 <span data-ttu-id="f9e9c-132">Extiende la interfaz `ICorProfilerInfo2` con los métodos admitidos en [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="f9e9c-132">Extends the `ICorProfilerInfo2` interface with methods supported in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] and later versions.</span></span>  
  
 [<span data-ttu-id="f9e9c-133">ICorProfilerInfo4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f9e9c-133">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 <span data-ttu-id="f9e9c-134">Proporciona métodos que los generadores de perfiles de código usan para comunicarse con CLR para controlar la supervisión de eventos y para solicitar información.</span><span class="sxs-lookup"><span data-stu-id="f9e9c-134">Provides methods that code profilers use to communicate with the CLR to control event monitoring and to request information.</span></span>  
  
 [<span data-ttu-id="f9e9c-135">ICorProfilerInfo5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f9e9c-135">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)  
 <span data-ttu-id="f9e9c-136">Proporciona métodos que los generadores de perfiles de código usan para comunicarse con CLR para controlar la supervisión de eventos.</span><span class="sxs-lookup"><span data-stu-id="f9e9c-136">Provides methods for use by code profilers to communicate with the CLR to control event monitoring.</span></span>  
  
 [<span data-ttu-id="f9e9c-137">Interfaz ICorProfilerInfo6</span><span class="sxs-lookup"><span data-stu-id="f9e9c-137">ICorProfilerInfo6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)  
 <span data-ttu-id="f9e9c-138">Proporciona un enumerador para todos los métodos que pertenecen a un módulo de NGen determinado y que se alinean en el cuerpo de un método determinado.</span><span class="sxs-lookup"><span data-stu-id="f9e9c-138">Provides an enumerator to all the methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>  
  
 [<span data-ttu-id="f9e9c-139">Interfaz ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="f9e9c-139">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)  
 <span data-ttu-id="f9e9c-140">Proporciona un método para aplicar recién definido los metadatos para un módulo y que proporciona acceso a una secuencia de símbolos en memoria.</span><span class="sxs-lookup"><span data-stu-id="f9e9c-140">Provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
 [<span data-ttu-id="f9e9c-141">ICorProfilerModuleEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f9e9c-141">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 <span data-ttu-id="f9e9c-142">Proporciona métodos para iterar secuencialmente por una colección de módulos cargados por la aplicación o por el generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="f9e9c-142">Provides methods to sequentially iterate through a collection of modules loaded by the application or the profiler.</span></span>  
  
 [<span data-ttu-id="f9e9c-143">ICorProfilerObjectEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f9e9c-143">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)  
 <span data-ttu-id="f9e9c-144">Proporciona métodos para iterar secuencialmente por una colección de objetos inmovilizados generados por [Ngen.exe (generador de imágenes nativas)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span><span class="sxs-lookup"><span data-stu-id="f9e9c-144">Provides methods to sequentially iterate through a collection of frozen objects that are generated by [Ngen.exe (Native Image Generator)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span></span>  
  
 [<span data-ttu-id="f9e9c-145">ICorProfilerThreadEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f9e9c-145">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 <span data-ttu-id="f9e9c-146">Proporciona métodos para iterar secuencialmente por una colección de subprocesos en CLR.</span><span class="sxs-lookup"><span data-stu-id="f9e9c-146">Provides methods to sequentially iterate through a collection of threads in the CLR.</span></span>  
  
 [<span data-ttu-id="f9e9c-147">IMethodMalloc (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f9e9c-147">IMethodMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)  
 <span data-ttu-id="f9e9c-148">Proporciona el [Alloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md) método para asignar memoria para un nuevo cuerpo de función del lenguaje intermedio (MSIL) de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f9e9c-148">Provides the [Alloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md) method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f9e9c-149">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="f9e9c-149">Related Sections</span></span>  
 [<span data-ttu-id="f9e9c-150">Información general de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="f9e9c-150">Profiling Overview</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [<span data-ttu-id="f9e9c-151">Funciones estáticas globales de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="f9e9c-151">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [<span data-ttu-id="f9e9c-152">Enumeraciones de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="f9e9c-152">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
  
 [<span data-ttu-id="f9e9c-153">Estructuras de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="f9e9c-153">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
