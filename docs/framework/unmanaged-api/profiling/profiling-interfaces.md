---
title: Interfaces para generación de perfiles
ms.date: 04/10/2018
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], profiling
- profiling interfaces [.NET Framework]
- interfaces [.NET Framework profiling]
ms.assetid: d9303db8-e881-4217-91b7-8c7573c8ef9e
ms.openlocfilehash: adc47417265d32d79508af949c118c4d31a83365
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124197"
---
# <a name="profiling-interfaces"></a><span data-ttu-id="11a73-102">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="11a73-102">Profiling Interfaces</span></span>
<span data-ttu-id="11a73-103">En esta sección se describen las interfaces no administradas que permiten generar perfiles para un programa que se ejecuta en Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="11a73-103">This section describes the unmanaged interfaces that enable you to profile a program that is being executed by the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="11a73-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="11a73-104">In This Section</span></span>  
 [<span data-ttu-id="11a73-105">ICLRProfiling (interfaz)</span><span class="sxs-lookup"><span data-stu-id="11a73-105">ICLRProfiling Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-interface.md)  
 <span data-ttu-id="11a73-106">Proporciona el método [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) , que permite a un generador de perfiles asociarse a un proceso en ejecución.</span><span class="sxs-lookup"><span data-stu-id="11a73-106">Provides the [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) method, which enables a profiler to attach to a running process.</span></span>  
  
 [<span data-ttu-id="11a73-107">ICorProfilerAssemblyReferenceProvider (interfaz)</span><span class="sxs-lookup"><span data-stu-id="11a73-107">ICorProfilerAssemblyReferenceProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)  
 <span data-ttu-id="11a73-108">Permite al generador de perfiles informar a CLR de las referencias de ensamblado que el generador de perfiles agregará en la devolución de llamada [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="11a73-108">Enables the profiler to inform the CLR of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
 [<span data-ttu-id="11a73-109">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="11a73-109">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 <span data-ttu-id="11a73-110">Proporciona métodos que CLR usa para notificar a un generador de perfiles de código cuando se produzcan los eventos a los que se ha suscrito el generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="11a73-110">Provides methods that are used by the CLR to notify a code profiler when the events to which the profiler has subscribed occur.</span></span>  
  
 [<span data-ttu-id="11a73-111">ICorProfilerCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="11a73-111">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 <span data-ttu-id="11a73-112">Extiende la interfaz `ICorProfilerCallback` con las devoluciones de llamada admitidas en .NET Framework 2.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="11a73-112">Extends the `ICorProfilerCallback` interface with callbacks supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="11a73-113">ICorProfilerCallback3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="11a73-113">ICorProfilerCallback3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)  
 <span data-ttu-id="11a73-114">Proporciona métodos de devolución de llamada que CLR usa para comunicar la información sobre el estado de asociación y desasociación al generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="11a73-114">Provides callback methods that the CLR uses to communicate attach and detach state information to the profiler.</span></span>  
  
 [<span data-ttu-id="11a73-115">ICorProfilerCallback4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="11a73-115">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 <span data-ttu-id="11a73-116">Proporciona métodos de devolución de llamada que CLR usa para comunicar la información al generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="11a73-116">Provides callback methods that the CLR uses to communicate information to the profiler.</span></span>  
  
 [<span data-ttu-id="11a73-117">ICorProfilerCallback5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="11a73-117">ICorProfilerCallback5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md)  
 <span data-ttu-id="11a73-118">Proporciona un método que identifica el cierre transitivo de los objetos a los que hacen referencia las raíces de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="11a73-118">Provides a method that identifies the transitive closure of objects referenced by garbage collection roots.</span></span>  
  
 [<span data-ttu-id="11a73-119">ICorProfilerCallback6 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="11a73-119">ICorProfilerCallback6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md)  
 <span data-ttu-id="11a73-120">Proporciona un método de devolución de llamada que CLR usa para notificar a un generador de perfiles que un ensamblado se está cargando.</span><span class="sxs-lookup"><span data-stu-id="11a73-120">Provides a callback method that the CLR uses to notify a profiler that an assembly is loading.</span></span>  
  
 [<span data-ttu-id="11a73-121">ICorProfilerCallback7 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="11a73-121">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)  
 <span data-ttu-id="11a73-122">Proporciona un método de devolución de llamada que el Common Language Runtime utiliza para notificar al generador de perfiles que se ha actualizado la secuencia de símbolos asociada a un módulo en memoria.</span><span class="sxs-lookup"><span data-stu-id="11a73-122">Provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  

[<span data-ttu-id="11a73-123">ICorProfilerCallback8 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="11a73-123">ICorProfilerCallback8 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback8-interface.md)  
<span data-ttu-id="11a73-124">Proporciona métodos de devolución de llamada que el Common Language Runtime utiliza para notificar al generador de perfiles que la compilación JIT de un método dinámico se ha iniciado y finalizado.</span><span class="sxs-lookup"><span data-stu-id="11a73-124">Provides callback methods that the common language runtime uses to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span>

[<span data-ttu-id="11a73-125">ICorProfilerCallback9 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="11a73-125">ICorProfilerCallback9 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback9-interface.md)  
<span data-ttu-id="11a73-126">Proporciona un método de devolución de llamada que el Common Language Runtime utiliza para notificar al generador de perfiles que se ha recopilado un método dinámico y que posteriormente se ha descargado.</span><span class="sxs-lookup"><span data-stu-id="11a73-126">Provides a callback method that the common language runtime uses to notify the profiler that a dynamic method is garbage collected and subsequently unloaded.</span></span>

 [<span data-ttu-id="11a73-127">ICorProfilerFunctionControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="11a73-127">ICorProfilerFunctionControl Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)  
 <span data-ttu-id="11a73-128">Proporciona métodos que permiten a un generador de perfiles de código comunicarse con CLR para controlar cómo debe generar el código el compilador JIT cuando vuelva a compilar un método específico.</span><span class="sxs-lookup"><span data-stu-id="11a73-128">Provides methods that allow a code profiler to communicate with the CLR to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
 [<span data-ttu-id="11a73-129">ICorProfilerFunctionEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="11a73-129">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 <span data-ttu-id="11a73-130">Proporciona métodos para iterar secuencialmente por una colección de funciones en CLR.</span><span class="sxs-lookup"><span data-stu-id="11a73-130">Provides methods to sequentially iterate through a collection of functions in the CLR.</span></span>  
  
 [<span data-ttu-id="11a73-131">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="11a73-131">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 <span data-ttu-id="11a73-132">Proporciona métodos que los generadores de perfiles de código usan para comunicarse con CLR para controlar la supervisión de eventos y para solicitar información.</span><span class="sxs-lookup"><span data-stu-id="11a73-132">Provides methods for use by code profilers to communicate with the CLR to control event monitoring and request information.</span></span>  
  
 [<span data-ttu-id="11a73-133">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="11a73-133">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 <span data-ttu-id="11a73-134">Extiende la interfaz `ICorProfilerInfo` con los métodos admitidos en .NET Framework 2.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="11a73-134">Extends the `ICorProfilerInfo` interface with methods supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="11a73-135">ICorProfilerInfo3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="11a73-135">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 <span data-ttu-id="11a73-136">Extiende la interfaz de `ICorProfilerInfo2` con métodos admitidos en el .NET Framework 4 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="11a73-136">Extends the `ICorProfilerInfo2` interface with methods supported in the .NET Framework 4 and later versions.</span></span>  
  
 [<span data-ttu-id="11a73-137">ICorProfilerInfo4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="11a73-137">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 <span data-ttu-id="11a73-138">Proporciona métodos que los generadores de perfiles de código usan para comunicarse con CLR para controlar la supervisión de eventos y para solicitar información.</span><span class="sxs-lookup"><span data-stu-id="11a73-138">Provides methods that code profilers use to communicate with the CLR to control event monitoring and to request information.</span></span>  
  
 [<span data-ttu-id="11a73-139">ICorProfilerInfo5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="11a73-139">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)  
 <span data-ttu-id="11a73-140">Proporciona métodos que los generadores de perfiles de código usan para comunicarse con CLR para controlar la supervisión de eventos.</span><span class="sxs-lookup"><span data-stu-id="11a73-140">Provides methods for use by code profilers to communicate with the CLR to control event monitoring.</span></span>  
  
 [<span data-ttu-id="11a73-141">ICorProfilerInfo6 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="11a73-141">ICorProfilerInfo6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)  
 <span data-ttu-id="11a73-142">Proporciona un enumerador para todos los métodos que pertenecen a un módulo NGen determinado y que están insertados en el cuerpo de un método determinado.</span><span class="sxs-lookup"><span data-stu-id="11a73-142">Provides an enumerator to all the methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>  
  
 [<span data-ttu-id="11a73-143">ICorProfilerInfo7 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="11a73-143">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)  
 <span data-ttu-id="11a73-144">Proporciona un método para aplicar los metadatos recién definidos a un módulo y que proporciona acceso a una secuencia de símbolos en memoria.</span><span class="sxs-lookup"><span data-stu-id="11a73-144">Provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
 [<span data-ttu-id="11a73-145">ICorProfilerModuleEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="11a73-145">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 <span data-ttu-id="11a73-146">Proporciona métodos para iterar secuencialmente por una colección de módulos cargados por la aplicación o por el generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="11a73-146">Provides methods to sequentially iterate through a collection of modules loaded by the application or the profiler.</span></span>  
  
 [<span data-ttu-id="11a73-147">ICorProfilerObjectEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="11a73-147">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)  
 <span data-ttu-id="11a73-148">Proporciona métodos para iterar secuencialmente por una colección de objetos inmovilizados generados por [Ngen. exe (generador de imágenes nativas)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span><span class="sxs-lookup"><span data-stu-id="11a73-148">Provides methods to sequentially iterate through a collection of frozen objects that are generated by [Ngen.exe (Native Image Generator)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span></span>  
  
 [<span data-ttu-id="11a73-149">ICorProfilerThreadEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="11a73-149">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 <span data-ttu-id="11a73-150">Proporciona métodos para iterar secuencialmente por una colección de subprocesos en CLR.</span><span class="sxs-lookup"><span data-stu-id="11a73-150">Provides methods to sequentially iterate through a collection of threads in the CLR.</span></span>  
  
 [<span data-ttu-id="11a73-151">IMethodMalloc (interfaz)</span><span class="sxs-lookup"><span data-stu-id="11a73-151">IMethodMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)  
 <span data-ttu-id="11a73-152">Proporciona el método de [asignación](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md) para asignar memoria para un nuevo cuerpo de la función del lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="11a73-152">Provides the [Alloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md) method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="11a73-153">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="11a73-153">Related Sections</span></span>  
 [<span data-ttu-id="11a73-154">Información general sobre la generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="11a73-154">Profiling Overview</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [<span data-ttu-id="11a73-155">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="11a73-155">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [<span data-ttu-id="11a73-156">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="11a73-156">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
  
 [<span data-ttu-id="11a73-157">Estructuras para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="11a73-157">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
