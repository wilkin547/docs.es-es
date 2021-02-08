---
description: 'Más información acerca de: interfaces de generación de perfiles'
title: Interfaces para generación de perfiles
ms.date: 04/10/2018
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], profiling
- profiling interfaces [.NET Framework]
- interfaces [.NET Framework profiling]
ms.assetid: d9303db8-e881-4217-91b7-8c7573c8ef9e
ms.openlocfilehash: d35931c0caad93116d7ea26d29020d84e48ebc29
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99798932"
---
# <a name="profiling-interfaces"></a><span data-ttu-id="a627c-103">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="a627c-103">Profiling Interfaces</span></span>

<span data-ttu-id="a627c-104">En esta sección se describen las interfaces no administradas que permiten generar perfiles para un programa que se ejecuta en Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="a627c-104">This section describes the unmanaged interfaces that enable you to profile a program that is being executed by the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a627c-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a627c-105">In This Section</span></span>  

 [<span data-ttu-id="a627c-106">ICLRProfiling (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a627c-106">ICLRProfiling Interface</span></span>](iclrprofiling-interface.md)  
 <span data-ttu-id="a627c-107">Proporciona el método [AttachProfiler](iclrprofiling-attachprofiler-method.md) , que permite a un generador de perfiles asociarse a un proceso en ejecución.</span><span class="sxs-lookup"><span data-stu-id="a627c-107">Provides the [AttachProfiler](iclrprofiling-attachprofiler-method.md) method, which enables a profiler to attach to a running process.</span></span>  
  
 [<span data-ttu-id="a627c-108">ICorProfilerAssemblyReferenceProvider (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a627c-108">ICorProfilerAssemblyReferenceProvider Interface</span></span>](icorprofilerassemblyreferenceprovider-interface.md)  
 <span data-ttu-id="a627c-109">Permite al generador de perfiles informar a CLR de las referencias de ensamblado que el generador de perfiles agregará en la devolución de llamada [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a627c-109">Enables the profiler to inform the CLR of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
 [<span data-ttu-id="a627c-110">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a627c-110">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)  
 <span data-ttu-id="a627c-111">Proporciona métodos que CLR usa para notificar a un generador de perfiles de código cuando se produzcan los eventos a los que se ha suscrito el generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="a627c-111">Provides methods that are used by the CLR to notify a code profiler when the events to which the profiler has subscribed occur.</span></span>  
  
 [<span data-ttu-id="a627c-112">ICorProfilerCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a627c-112">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)  
 <span data-ttu-id="a627c-113">Extiende la interfaz `ICorProfilerCallback` con las devoluciones de llamada admitidas en .NET Framework 2.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="a627c-113">Extends the `ICorProfilerCallback` interface with callbacks supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="a627c-114">ICorProfilerCallback3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a627c-114">ICorProfilerCallback3 Interface</span></span>](icorprofilercallback3-interface.md)  
 <span data-ttu-id="a627c-115">Proporciona métodos de devolución de llamada que CLR usa para comunicar la información sobre el estado de asociación y desasociación al generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="a627c-115">Provides callback methods that the CLR uses to communicate attach and detach state information to the profiler.</span></span>  
  
 [<span data-ttu-id="a627c-116">ICorProfilerCallback4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a627c-116">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)  
 <span data-ttu-id="a627c-117">Proporciona métodos de devolución de llamada que CLR usa para comunicar la información al generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="a627c-117">Provides callback methods that the CLR uses to communicate information to the profiler.</span></span>  
  
 [<span data-ttu-id="a627c-118">ICorProfilerCallback5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a627c-118">ICorProfilerCallback5 Interface</span></span>](icorprofilercallback5-interface.md)  
 <span data-ttu-id="a627c-119">Proporciona un método que identifica el cierre transitivo de los objetos a los que hacen referencia las raíces de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="a627c-119">Provides a method that identifies the transitive closure of objects referenced by garbage collection roots.</span></span>  
  
 [<span data-ttu-id="a627c-120">ICorProfilerCallback6 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a627c-120">ICorProfilerCallback6 Interface</span></span>](icorprofilercallback6-interface.md)  
 <span data-ttu-id="a627c-121">Proporciona un método de devolución de llamada que CLR usa para notificar a un generador de perfiles que un ensamblado se está cargando.</span><span class="sxs-lookup"><span data-stu-id="a627c-121">Provides a callback method that the CLR uses to notify a profiler that an assembly is loading.</span></span>  
  
 [<span data-ttu-id="a627c-122">Interfaz ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="a627c-122">ICorProfilerCallback7 Interface</span></span>](icorprofilercallback7-interface.md)  
 <span data-ttu-id="a627c-123">Proporciona un método de devolución de llamada que el Common Language Runtime utiliza para notificar al generador de perfiles que se ha actualizado la secuencia de símbolos asociada a un módulo en memoria.</span><span class="sxs-lookup"><span data-stu-id="a627c-123">Provides a callback method that the common language runtime uses to notify the profiler that the symbol stream associated with an in-memory module is updated.</span></span>  

[<span data-ttu-id="a627c-124">Interfaz ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="a627c-124">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback8-interface.md)  
<span data-ttu-id="a627c-125">Proporciona métodos de devolución de llamada que el Common Language Runtime utiliza para notificar al generador de perfiles que la compilación JIT de un método dinámico se ha iniciado y finalizado.</span><span class="sxs-lookup"><span data-stu-id="a627c-125">Provides callback methods that the common language runtime uses to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span>

[<span data-ttu-id="a627c-126">Interfaz ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="a627c-126">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)  
<span data-ttu-id="a627c-127">Proporciona un método de devolución de llamada que el Common Language Runtime utiliza para notificar al generador de perfiles que se ha recopilado un método dinámico y que posteriormente se ha descargado.</span><span class="sxs-lookup"><span data-stu-id="a627c-127">Provides a callback method that the common language runtime uses to notify the profiler that a dynamic method is garbage collected and subsequently unloaded.</span></span>

 [<span data-ttu-id="a627c-128">ICorProfilerFunctionControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a627c-128">ICorProfilerFunctionControl Interface</span></span>](icorprofilerfunctioncontrol-interface.md)  
 <span data-ttu-id="a627c-129">Proporciona métodos que permiten a un generador de perfiles de código comunicarse con CLR para controlar cómo debe generar el código el compilador JIT cuando vuelva a compilar un método específico.</span><span class="sxs-lookup"><span data-stu-id="a627c-129">Provides methods that allow a code profiler to communicate with the CLR to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
 [<span data-ttu-id="a627c-130">ICorProfilerFunctionEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a627c-130">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)  
 <span data-ttu-id="a627c-131">Proporciona métodos para iterar secuencialmente por una colección de funciones en CLR.</span><span class="sxs-lookup"><span data-stu-id="a627c-131">Provides methods to sequentially iterate through a collection of functions in the CLR.</span></span>  
  
 [<span data-ttu-id="a627c-132">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a627c-132">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)  
 <span data-ttu-id="a627c-133">Proporciona métodos que los generadores de perfiles de código usan para comunicarse con CLR para controlar la supervisión de eventos y para solicitar información.</span><span class="sxs-lookup"><span data-stu-id="a627c-133">Provides methods for use by code profilers to communicate with the CLR to control event monitoring and request information.</span></span>  
  
 [<span data-ttu-id="a627c-134">ICorProfilerInfo2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a627c-134">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)  
 <span data-ttu-id="a627c-135">Extiende la interfaz `ICorProfilerInfo` con los métodos admitidos en .NET Framework 2.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="a627c-135">Extends the `ICorProfilerInfo` interface with methods supported in the .NET Framework 2.0 and later versions.</span></span>  
  
 [<span data-ttu-id="a627c-136">ICorProfilerInfo3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a627c-136">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)  
 <span data-ttu-id="a627c-137">Extiende la `ICorProfilerInfo2` interfaz con los métodos admitidos en el .NET Framework 4 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="a627c-137">Extends the `ICorProfilerInfo2` interface with methods supported in the .NET Framework 4 and later versions.</span></span>  
  
 [<span data-ttu-id="a627c-138">ICorProfilerInfo4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a627c-138">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)  
 <span data-ttu-id="a627c-139">Proporciona métodos que los generadores de perfiles de código usan para comunicarse con CLR para controlar la supervisión de eventos y para solicitar información.</span><span class="sxs-lookup"><span data-stu-id="a627c-139">Provides methods that code profilers use to communicate with the CLR to control event monitoring and to request information.</span></span>  
  
 [<span data-ttu-id="a627c-140">ICorProfilerInfo5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a627c-140">ICorProfilerInfo5 Interface</span></span>](icorprofilerinfo5-interface.md)  
 <span data-ttu-id="a627c-141">Proporciona métodos que los generadores de perfiles de código usan para comunicarse con CLR para controlar la supervisión de eventos.</span><span class="sxs-lookup"><span data-stu-id="a627c-141">Provides methods for use by code profilers to communicate with the CLR to control event monitoring.</span></span>  
  
 [<span data-ttu-id="a627c-142">Interfaz ICorProfilerInfo6</span><span class="sxs-lookup"><span data-stu-id="a627c-142">ICorProfilerInfo6 Interface</span></span>](icorprofilerinfo6-interface.md)  
 <span data-ttu-id="a627c-143">Proporciona un enumerador para todos los métodos que pertenecen a un módulo NGen determinado y que están insertados en el cuerpo de un método determinado.</span><span class="sxs-lookup"><span data-stu-id="a627c-143">Provides an enumerator to all the methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>  
  
 [<span data-ttu-id="a627c-144">Interfaz ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="a627c-144">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)  
 <span data-ttu-id="a627c-145">Proporciona un método para aplicar los metadatos recién definidos a un módulo y que proporciona acceso a una secuencia de símbolos en memoria.</span><span class="sxs-lookup"><span data-stu-id="a627c-145">Provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
 [<span data-ttu-id="a627c-146">ICorProfilerModuleEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a627c-146">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)  
 <span data-ttu-id="a627c-147">Proporciona métodos para iterar secuencialmente por una colección de módulos cargados por la aplicación o por el generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="a627c-147">Provides methods to sequentially iterate through a collection of modules loaded by the application or the profiler.</span></span>  
  
 [<span data-ttu-id="a627c-148">ICorProfilerObjectEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a627c-148">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)  
 <span data-ttu-id="a627c-149">Proporciona métodos para iterar secuencialmente por una colección de objetos inmovilizados generados por [Ngen.exe (generador de imágenes nativas)](../../tools/ngen-exe-native-image-generator.md).</span><span class="sxs-lookup"><span data-stu-id="a627c-149">Provides methods to sequentially iterate through a collection of frozen objects that are generated by [Ngen.exe (Native Image Generator)](../../tools/ngen-exe-native-image-generator.md).</span></span>  
  
 [<span data-ttu-id="a627c-150">ICorProfilerThreadEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a627c-150">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)  
 <span data-ttu-id="a627c-151">Proporciona métodos para iterar secuencialmente por una colección de subprocesos en CLR.</span><span class="sxs-lookup"><span data-stu-id="a627c-151">Provides methods to sequentially iterate through a collection of threads in the CLR.</span></span>  
  
 [<span data-ttu-id="a627c-152">IMethodMalloc (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a627c-152">IMethodMalloc Interface</span></span>](imethodmalloc-interface.md)  
 <span data-ttu-id="a627c-153">Proporciona el método de [asignación](imethodmalloc-alloc-method.md) para asignar memoria para un nuevo cuerpo de la función del lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="a627c-153">Provides the [Alloc](imethodmalloc-alloc-method.md) method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a627c-154">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="a627c-154">Related Sections</span></span>  

 [<span data-ttu-id="a627c-155">Información general sobre la generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="a627c-155">Profiling Overview</span></span>](profiling-overview.md)  
  
 [<span data-ttu-id="a627c-156">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="a627c-156">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)  
  
 [<span data-ttu-id="a627c-157">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="a627c-157">Profiling Enumerations</span></span>](profiling-enumerations.md)  
  
 [<span data-ttu-id="a627c-158">Estructuras para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="a627c-158">Profiling Structures</span></span>](profiling-structures.md)
