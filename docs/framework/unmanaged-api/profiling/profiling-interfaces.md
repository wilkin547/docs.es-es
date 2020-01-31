---
title: Interfaces para generación de perfiles
ms.date: 04/10/2018
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], profiling
- profiling interfaces [.NET Framework]
- interfaces [.NET Framework profiling]
ms.assetid: d9303db8-e881-4217-91b7-8c7573c8ef9e
ms.openlocfilehash: 8b6b9acff2945e2d8fd684bfa31e4af086ea5ab9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868153"
---
# <a name="profiling-interfaces"></a><span data-ttu-id="e94e8-102">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="e94e8-102">Profiling Interfaces</span></span>
<span data-ttu-id="e94e8-103">En esta sección se describen las interfaces no administradas que permiten generar perfiles para un programa que se ejecuta en Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="e94e8-103">This section describes the unmanaged interfaces that enable you to profile a program that is being executed by the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e94e8-104">Esta sección</span><span class="sxs-lookup"><span data-stu-id="e94e8-104">In This Section</span></span>  
 [<span data-ttu-id="e94e8-105">ICLRProfiling (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e94e8-105">ICLRProfiling Interface</span></span>](iclrprofiling-interface.md)  
 <span data-ttu-id="e94e8-106">Proporciona el método [AttachProfiler](iclrprofiling-attachprofiler-method.md) , que permite a un generador de perfiles asociarse a un proceso en ejecución.</span><span class="sxs-lookup"><span data-stu-id="e94e8-106">Provides the [AttachProfiler](iclrprofiling-attachprofiler-method.md) method, which enables a profiler to attach to a running process.</span></span>  
  
 [<span data-ttu-id="e94e8-107">ICorProfilerAssemblyReferenceProvider (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e94e8-107">ICorProfilerAssemblyReferenceProvider Interface</span></span>](icorprofilerassemblyreferenceprovider-interface.md)  
 <span data-ttu-id="e94e8-108">Permite al generador de perfiles informar a CLR de las referencias de ensamblado que el generador de perfiles agregará en la devolución de llamada [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e94e8-108">Enables the profiler to inform the CLR of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
 [<span data-ttu-id="e94e8-109">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e94e8-109">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)  
 <span data-ttu-id="e94e8-110">Proporciona métodos que CLR usa para notificar a un generador de perfiles de código cuando se produzcan los eventos a los que se ha suscrito el generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="e94e8-110">Provides methods that are used by the CLR to notify a code profiler when the events to which the profiler has subscribed occur.</span></span>  
  
 [<span data-ttu-id="e94e8-111">ICorProfilerCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e94e8-111">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)  
 <span data-ttu-id="e94e8-112">Extiende la interfaz `ICorProfilerCallback` con las devoluciones de llamada admitidas en .NET Framework 2.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="e94e8-112">Extends the `ICorProfilerCallback` interface with callbacks supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="e94e8-113">ICorProfilerCallback3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e94e8-113">ICorProfilerCallback3 Interface</span></span>](icorprofilercallback3-interface.md)  
 <span data-ttu-id="e94e8-114">Proporciona métodos de devolución de llamada que CLR usa para comunicar la información sobre el estado de asociación y desasociación al generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="e94e8-114">Provides callback methods that the CLR uses to communicate attach and detach state information to the profiler.</span></span>  
  
 [<span data-ttu-id="e94e8-115">ICorProfilerCallback4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e94e8-115">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)  
 <span data-ttu-id="e94e8-116">Proporciona métodos de devolución de llamada que CLR usa para comunicar la información al generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="e94e8-116">Provides callback methods that the CLR uses to communicate information to the profiler.</span></span>  
  
 [<span data-ttu-id="e94e8-117">ICorProfilerCallback5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e94e8-117">ICorProfilerCallback5 Interface</span></span>](icorprofilercallback5-interface.md)  
 <span data-ttu-id="e94e8-118">Proporciona un método que identifica el cierre transitivo de los objetos a los que hacen referencia las raíces de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="e94e8-118">Provides a method that identifies the transitive closure of objects referenced by garbage collection roots.</span></span>  
  
 [<span data-ttu-id="e94e8-119">ICorProfilerCallback6 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e94e8-119">ICorProfilerCallback6 Interface</span></span>](icorprofilercallback6-interface.md)  
 <span data-ttu-id="e94e8-120">Proporciona un método de devolución de llamada que CLR usa para notificar a un generador de perfiles que un ensamblado se está cargando.</span><span class="sxs-lookup"><span data-stu-id="e94e8-120">Provides a callback method that the CLR uses to notify a profiler that an assembly is loading.</span></span>  
  
 [<span data-ttu-id="e94e8-121">ICorProfilerCallback7 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e94e8-121">ICorProfilerCallback7 Interface</span></span>](icorprofilercallback7-interface.md)  
 <span data-ttu-id="e94e8-122">Proporciona un método de devolución de llamada que el Common Language Runtime utiliza para notificar al generador de perfiles que se ha actualizado la secuencia de símbolos asociada a un módulo en memoria.</span><span class="sxs-lookup"><span data-stu-id="e94e8-122">Provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  

[<span data-ttu-id="e94e8-123">ICorProfilerCallback8 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e94e8-123">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)  
<span data-ttu-id="e94e8-124">Proporciona métodos de devolución de llamada que el Common Language Runtime utiliza para notificar al generador de perfiles que la compilación JIT de un método dinámico se ha iniciado y finalizado.</span><span class="sxs-lookup"><span data-stu-id="e94e8-124">Provides callback methods that the common language runtime uses to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span>

[<span data-ttu-id="e94e8-125">ICorProfilerCallback9 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e94e8-125">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)  
<span data-ttu-id="e94e8-126">Proporciona un método de devolución de llamada que el Common Language Runtime utiliza para notificar al generador de perfiles que se ha recopilado un método dinámico y que posteriormente se ha descargado.</span><span class="sxs-lookup"><span data-stu-id="e94e8-126">Provides a callback method that the common language runtime uses to notify the profiler that a dynamic method is garbage collected and subsequently unloaded.</span></span>

 [<span data-ttu-id="e94e8-127">ICorProfilerFunctionControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e94e8-127">ICorProfilerFunctionControl Interface</span></span>](icorprofilerfunctioncontrol-interface.md)  
 <span data-ttu-id="e94e8-128">Proporciona métodos que permiten a un generador de perfiles de código comunicarse con CLR para controlar cómo debe generar el código el compilador JIT cuando vuelva a compilar un método específico.</span><span class="sxs-lookup"><span data-stu-id="e94e8-128">Provides methods that allow a code profiler to communicate with the CLR to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
 [<span data-ttu-id="e94e8-129">ICorProfilerFunctionEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e94e8-129">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)  
 <span data-ttu-id="e94e8-130">Proporciona métodos para iterar secuencialmente por una colección de funciones en CLR.</span><span class="sxs-lookup"><span data-stu-id="e94e8-130">Provides methods to sequentially iterate through a collection of functions in the CLR.</span></span>  
  
 [<span data-ttu-id="e94e8-131">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e94e8-131">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)  
 <span data-ttu-id="e94e8-132">Proporciona métodos que los generadores de perfiles de código usan para comunicarse con CLR para controlar la supervisión de eventos y para solicitar información.</span><span class="sxs-lookup"><span data-stu-id="e94e8-132">Provides methods for use by code profilers to communicate with the CLR to control event monitoring and request information.</span></span>  
  
 [<span data-ttu-id="e94e8-133">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e94e8-133">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)  
 <span data-ttu-id="e94e8-134">Extiende la interfaz `ICorProfilerInfo` con los métodos admitidos en .NET Framework 2.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="e94e8-134">Extends the `ICorProfilerInfo` interface with methods supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="e94e8-135">ICorProfilerInfo3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e94e8-135">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)  
 <span data-ttu-id="e94e8-136">Extiende la interfaz de `ICorProfilerInfo2` con métodos admitidos en el .NET Framework 4 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="e94e8-136">Extends the `ICorProfilerInfo2` interface with methods supported in the .NET Framework 4 and later versions.</span></span>  
  
 [<span data-ttu-id="e94e8-137">ICorProfilerInfo4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e94e8-137">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)  
 <span data-ttu-id="e94e8-138">Proporciona métodos que los generadores de perfiles de código usan para comunicarse con CLR para controlar la supervisión de eventos y para solicitar información.</span><span class="sxs-lookup"><span data-stu-id="e94e8-138">Provides methods that code profilers use to communicate with the CLR to control event monitoring and to request information.</span></span>  
  
 [<span data-ttu-id="e94e8-139">ICorProfilerInfo5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e94e8-139">ICorProfilerInfo5 Interface</span></span>](icorprofilerinfo5-interface.md)  
 <span data-ttu-id="e94e8-140">Proporciona métodos que los generadores de perfiles de código usan para comunicarse con CLR para controlar la supervisión de eventos.</span><span class="sxs-lookup"><span data-stu-id="e94e8-140">Provides methods for use by code profilers to communicate with the CLR to control event monitoring.</span></span>  
  
 [<span data-ttu-id="e94e8-141">ICorProfilerInfo6 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e94e8-141">ICorProfilerInfo6 Interface</span></span>](icorprofilerinfo6-interface.md)  
 <span data-ttu-id="e94e8-142">Proporciona un enumerador para todos los métodos que pertenecen a un módulo NGen determinado y que están insertados en el cuerpo de un método determinado.</span><span class="sxs-lookup"><span data-stu-id="e94e8-142">Provides an enumerator to all the methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>  
  
 [<span data-ttu-id="e94e8-143">ICorProfilerInfo7 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e94e8-143">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)  
 <span data-ttu-id="e94e8-144">Proporciona un método para aplicar los metadatos recién definidos a un módulo y que proporciona acceso a una secuencia de símbolos en memoria.</span><span class="sxs-lookup"><span data-stu-id="e94e8-144">Provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
 [<span data-ttu-id="e94e8-145">ICorProfilerModuleEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e94e8-145">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)  
 <span data-ttu-id="e94e8-146">Proporciona métodos para iterar secuencialmente por una colección de módulos cargados por la aplicación o por el generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="e94e8-146">Provides methods to sequentially iterate through a collection of modules loaded by the application or the profiler.</span></span>  
  
 [<span data-ttu-id="e94e8-147">ICorProfilerObjectEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e94e8-147">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)  
 <span data-ttu-id="e94e8-148">Proporciona métodos para iterar secuencialmente por una colección de objetos inmovilizados generados por [Ngen. exe (generador de imágenes nativas)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span><span class="sxs-lookup"><span data-stu-id="e94e8-148">Provides methods to sequentially iterate through a collection of frozen objects that are generated by [Ngen.exe (Native Image Generator)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span></span>  
  
 [<span data-ttu-id="e94e8-149">ICorProfilerThreadEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e94e8-149">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)  
 <span data-ttu-id="e94e8-150">Proporciona métodos para iterar secuencialmente por una colección de subprocesos en CLR.</span><span class="sxs-lookup"><span data-stu-id="e94e8-150">Provides methods to sequentially iterate through a collection of threads in the CLR.</span></span>  
  
 [<span data-ttu-id="e94e8-151">IMethodMalloc (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e94e8-151">IMethodMalloc Interface</span></span>](imethodmalloc-interface.md)  
 <span data-ttu-id="e94e8-152">Proporciona el método de [asignación](imethodmalloc-alloc-method.md) para asignar memoria para un nuevo cuerpo de la función del lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="e94e8-152">Provides the [Alloc](imethodmalloc-alloc-method.md) method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e94e8-153">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="e94e8-153">Related Sections</span></span>  
 [<span data-ttu-id="e94e8-154">Información general sobre la generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="e94e8-154">Profiling Overview</span></span>](profiling-overview.md)  
  
 [<span data-ttu-id="e94e8-155">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="e94e8-155">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)  
  
 [<span data-ttu-id="e94e8-156">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="e94e8-156">Profiling Enumerations</span></span>](profiling-enumerations.md)  
  
 [<span data-ttu-id="e94e8-157">Estructuras para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="e94e8-157">Profiling Structures</span></span>](profiling-structures.md)
