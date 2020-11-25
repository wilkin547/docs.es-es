---
title: Enumeraciones para generación de perfiles
ms.date: 03/30/2017
helpviewer_keywords:
- profiling enumerations [.NET Framework]
- enumerations [.NET Framework profiling]
- unmanaged enumerations [.NET Framework], profiling
ms.assetid: 8d5f9570-9853-4ce8-8101-df235d5b258e
ms.openlocfilehash: 8956a09cf76aa54452e8c020239e650e55d8a0d1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701619"
---
# <a name="profiling-enumerations"></a><span data-ttu-id="74ac1-102">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="74ac1-102">Profiling Enumerations</span></span>

<span data-ttu-id="74ac1-103">En esta sección se describen las enumeraciones no administradas que utiliza la API de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="74ac1-103">This section describes the unmanaged enumerations that the profiling API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="74ac1-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="74ac1-104">In This Section</span></span>  

 [<span data-ttu-id="74ac1-105">COR_PRF_CLAUSE_TYPE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="74ac1-105">COR_PRF_CLAUSE_TYPE Enumeration</span></span>](cor-prf-clause-type-enumeration.md)  
 <span data-ttu-id="74ac1-106">Indica el tipo de cláusula de excepción en la que el código acaba de entrar o de la que acaba de salir.</span><span class="sxs-lookup"><span data-stu-id="74ac1-106">Indicates the type of exception clause that the code has just entered or left.</span></span>  
  
 [<span data-ttu-id="74ac1-107">COR_PRF_CODEGEN_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="74ac1-107">COR_PRF_CODEGEN_FLAGS Enumeration</span></span>](cor-prf-codegen-flags-enumeration.md)  
 <span data-ttu-id="74ac1-108">Define las marcas de generación de código que se pueden establecer con el método [ICorProfilerFunctionControl:: setcodegenflags (](icorprofilerfunctioncontrol-setcodegenflags-method.md) .</span><span class="sxs-lookup"><span data-stu-id="74ac1-108">Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) method.</span></span>  
  
 [<span data-ttu-id="74ac1-109">COR_PRF_FINALIZER_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="74ac1-109">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>](cor-prf-finalizer-flags-enumeration.md)  
 <span data-ttu-id="74ac1-110">Describe el finalizador de un objeto.</span><span class="sxs-lookup"><span data-stu-id="74ac1-110">Describes the finalizer for an object.</span></span>  
  
 [<span data-ttu-id="74ac1-111">COR_PRF_GC_GENERATION (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="74ac1-111">COR_PRF_GC_GENERATION Enumeration</span></span>](cor-prf-gc-generation-enumeration.md)  
 <span data-ttu-id="74ac1-112">Identifica la generación de una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="74ac1-112">Identifies a garbage collection generation.</span></span>  
  
 [<span data-ttu-id="74ac1-113">COR_PRF_GC_REASON (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="74ac1-113">COR_PRF_GC_REASON Enumeration</span></span>](cor-prf-gc-reason-enumeration.md)  
 <span data-ttu-id="74ac1-114">Indica el motivo por el que se está produciendo la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="74ac1-114">Indicates the reason that garbage collection is occurring.</span></span>  
  
 [<span data-ttu-id="74ac1-115">COR_PRF_GC_ROOT_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="74ac1-115">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>](cor-prf-gc-root-flags-enumeration.md)  
 <span data-ttu-id="74ac1-116">Indica las propiedades de la raíz de un recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="74ac1-116">Indicates properties of a garbage collector root.</span></span>  
  
 [<span data-ttu-id="74ac1-117">COR_PRF_GC_ROOT_KIND (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="74ac1-117">COR_PRF_GC_ROOT_KIND Enumeration</span></span>](cor-prf-gc-root-kind-enumeration.md)  
 <span data-ttu-id="74ac1-118">Indica el tipo de raíz del recolector de elementos no utilizados expuesta por la devolución de llamada [ICorProfilerCallback2:: RootReferences2 (](icorprofilercallback2-rootreferences2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="74ac1-118">Indicates the kind of garbage collector root that is exposed by the [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) callback.</span></span>  
  
 [<span data-ttu-id="74ac1-119">COR_PRF_HIGH_MONITOR (enumeración)</span><span class="sxs-lookup"><span data-stu-id="74ac1-119">COR_PRF_HIGH_MONITOR Enumeration</span></span>](cor-prf-high-monitor-enumeration.md)  
 <span data-ttu-id="74ac1-120">Proporciona marcas además de las que se encuentran en la enumeración [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) que el generador de perfiles puede especificar para el método [ICorProfilerInfo5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) cuando se está cargando.</span><span class="sxs-lookup"><span data-stu-id="74ac1-120">Provides flags in addition to those found in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration that the profiler can specify to the [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method when it is loading.</span></span>  
  
 [<span data-ttu-id="74ac1-121">COR_PRF_JIT_CACHE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="74ac1-121">COR_PRF_JIT_CACHE Enumeration</span></span>](cor-prf-jit-cache-enumeration.md)  
 <span data-ttu-id="74ac1-122">Indica el resultado de una búsqueda de función en caché.</span><span class="sxs-lookup"><span data-stu-id="74ac1-122">Indicates the result of a cached function search.</span></span>  
  
 [<span data-ttu-id="74ac1-123">COR_PRF_MISC (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="74ac1-123">COR_PRF_MISC Enumeration</span></span>](cor-prf-misc-enumeration.md)  
 <span data-ttu-id="74ac1-124">Contiene valores constantes que especifican identificadores especiales.</span><span class="sxs-lookup"><span data-stu-id="74ac1-124">Contains constant values that specify special identifiers.</span></span>  
  
 [<span data-ttu-id="74ac1-125">COR_PRF_MODULE_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="74ac1-125">COR_PRF_MODULE_FLAGS Enumeration</span></span>](cor-prf-module-flags-enumeration.md)  
 <span data-ttu-id="74ac1-126">Especifica las propiedades de un módulo.</span><span class="sxs-lookup"><span data-stu-id="74ac1-126">Specifies the properties of a module.</span></span>  
  
 [<span data-ttu-id="74ac1-127">COR_PRF_MONITOR (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="74ac1-127">COR_PRF_MONITOR Enumeration</span></span>](cor-prf-monitor-enumeration.md)  
 <span data-ttu-id="74ac1-128">Contiene valores que se usan para especificar el comportamiento, las funcionalidades o los eventos a los que el generador de perfiles quiere suscribirse.</span><span class="sxs-lookup"><span data-stu-id="74ac1-128">Contains values that are used to specify behavior, capabilities, or events to which the profiler wishes to subscribe.</span></span>  
  
 [<span data-ttu-id="74ac1-129">COR_PRF_RUNTIME_TYPE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="74ac1-129">COR_PRF_RUNTIME_TYPE Enumeration</span></span>](cor-prf-runtime-type-enumeration.md)  
 <span data-ttu-id="74ac1-130">Contiene valores que indican la versión de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="74ac1-130">Contains values that indicate the version of the common language runtime.</span></span>  
  
 [<span data-ttu-id="74ac1-131">COR_PRF_SNAPSHOT_INFO (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="74ac1-131">COR_PRF_SNAPSHOT_INFO Enumeration</span></span>](cor-prf-snapshot-info-enumeration.md)  
 <span data-ttu-id="74ac1-132">Especifica cuántos datos se devolverán con una instantánea de pila en cada llamada a la función `StackSnapshotCallback` del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="74ac1-132">Specifies how much data to pass back with a stack snapshot in each call to the profiler's `StackSnapshotCallback` function.</span></span>  
  
 [<span data-ttu-id="74ac1-133">COR_PRF_STATIC_TYPE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="74ac1-133">COR_PRF_STATIC_TYPE Enumeration</span></span>](cor-prf-static-type-enumeration.md)  
 <span data-ttu-id="74ac1-134">Indica si un campo es estático y, si lo es, la calidad estática que se aplica al campo.</span><span class="sxs-lookup"><span data-stu-id="74ac1-134">Indicates whether a field is static and, if so, the static quality that applies to the field.</span></span>  
  
 [<span data-ttu-id="74ac1-135">COR_PRF_SUSPEND_REASON (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="74ac1-135">COR_PRF_SUSPEND_REASON Enumeration</span></span>](cor-prf-suspend-reason-enumeration.md)  
 <span data-ttu-id="74ac1-136">Indica el motivo por el que el tiempo de ejecución se suspendió.</span><span class="sxs-lookup"><span data-stu-id="74ac1-136">Indicates the reason that the runtime was suspended.</span></span>  
  
 [<span data-ttu-id="74ac1-137">COR_PRF_TRANSITION_REASON (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="74ac1-137">COR_PRF_TRANSITION_REASON Enumeration</span></span>](cor-prf-transition-reason-enumeration.md)  
 <span data-ttu-id="74ac1-138">Indica el motivo para una transición desde código administrado a no administrado, y o viceversa.</span><span class="sxs-lookup"><span data-stu-id="74ac1-138">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="74ac1-139">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="74ac1-139">Related Sections</span></span>  

 [<span data-ttu-id="74ac1-140">Información general sobre la generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="74ac1-140">Profiling Overview</span></span>](profiling-overview.md)  
  
 [<span data-ttu-id="74ac1-141">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="74ac1-141">Profiling Interfaces</span></span>](profiling-interfaces.md)  
  
 [<span data-ttu-id="74ac1-142">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="74ac1-142">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)  
  
 [<span data-ttu-id="74ac1-143">Estructuras para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="74ac1-143">Profiling Structures</span></span>](profiling-structures.md)
