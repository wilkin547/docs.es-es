---
description: 'Más información sobre: enumeraciones de generación de perfiles'
title: Enumeraciones para generación de perfiles
ms.date: 03/30/2017
helpviewer_keywords:
- profiling enumerations [.NET Framework]
- enumerations [.NET Framework profiling]
- unmanaged enumerations [.NET Framework], profiling
ms.assetid: 8d5f9570-9853-4ce8-8101-df235d5b258e
ms.openlocfilehash: f202e70dd27654dd39740851549477d4a6bf77a3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736757"
---
# <a name="profiling-enumerations"></a><span data-ttu-id="d8a2d-103">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="d8a2d-103">Profiling Enumerations</span></span>

<span data-ttu-id="d8a2d-104">En esta sección se describen las enumeraciones no administradas que utiliza la API de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="d8a2d-104">This section describes the unmanaged enumerations that the profiling API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d8a2d-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d8a2d-105">In This Section</span></span>  

 [<span data-ttu-id="d8a2d-106">COR_PRF_CLAUSE_TYPE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d8a2d-106">COR_PRF_CLAUSE_TYPE Enumeration</span></span>](cor-prf-clause-type-enumeration.md)  
 <span data-ttu-id="d8a2d-107">Indica el tipo de cláusula de excepción en la que el código acaba de entrar o de la que acaba de salir.</span><span class="sxs-lookup"><span data-stu-id="d8a2d-107">Indicates the type of exception clause that the code has just entered or left.</span></span>  
  
 [<span data-ttu-id="d8a2d-108">COR_PRF_CODEGEN_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d8a2d-108">COR_PRF_CODEGEN_FLAGS Enumeration</span></span>](cor-prf-codegen-flags-enumeration.md)  
 <span data-ttu-id="d8a2d-109">Define las marcas de generación de código que se pueden establecer con el método [ICorProfilerFunctionControl:: setcodegenflags (](icorprofilerfunctioncontrol-setcodegenflags-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d8a2d-109">Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md) method.</span></span>  
  
 [<span data-ttu-id="d8a2d-110">COR_PRF_FINALIZER_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d8a2d-110">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>](cor-prf-finalizer-flags-enumeration.md)  
 <span data-ttu-id="d8a2d-111">Describe el finalizador de un objeto.</span><span class="sxs-lookup"><span data-stu-id="d8a2d-111">Describes the finalizer for an object.</span></span>  
  
 [<span data-ttu-id="d8a2d-112">COR_PRF_GC_GENERATION (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d8a2d-112">COR_PRF_GC_GENERATION Enumeration</span></span>](cor-prf-gc-generation-enumeration.md)  
 <span data-ttu-id="d8a2d-113">Identifica la generación de una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="d8a2d-113">Identifies a garbage collection generation.</span></span>  
  
 [<span data-ttu-id="d8a2d-114">COR_PRF_GC_REASON (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d8a2d-114">COR_PRF_GC_REASON Enumeration</span></span>](cor-prf-gc-reason-enumeration.md)  
 <span data-ttu-id="d8a2d-115">Indica el motivo por el que se está produciendo la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="d8a2d-115">Indicates the reason that garbage collection is occurring.</span></span>  
  
 [<span data-ttu-id="d8a2d-116">COR_PRF_GC_ROOT_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d8a2d-116">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>](cor-prf-gc-root-flags-enumeration.md)  
 <span data-ttu-id="d8a2d-117">Indica las propiedades de la raíz de un recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="d8a2d-117">Indicates properties of a garbage collector root.</span></span>  
  
 [<span data-ttu-id="d8a2d-118">COR_PRF_GC_ROOT_KIND (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d8a2d-118">COR_PRF_GC_ROOT_KIND Enumeration</span></span>](cor-prf-gc-root-kind-enumeration.md)  
 <span data-ttu-id="d8a2d-119">Indica el tipo de raíz del recolector de elementos no utilizados expuesta por la devolución de llamada [ICorProfilerCallback2:: RootReferences2 (](icorprofilercallback2-rootreferences2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d8a2d-119">Indicates the kind of garbage collector root that is exposed by the [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) callback.</span></span>  
  
 [<span data-ttu-id="d8a2d-120">COR_PRF_HIGH_MONITOR (enumeración)</span><span class="sxs-lookup"><span data-stu-id="d8a2d-120">COR_PRF_HIGH_MONITOR Enumeration</span></span>](cor-prf-high-monitor-enumeration.md)  
 <span data-ttu-id="d8a2d-121">Proporciona marcas además de las que se encuentran en la enumeración [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) que el generador de perfiles puede especificar para el método [ICorProfilerInfo5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) cuando se está cargando.</span><span class="sxs-lookup"><span data-stu-id="d8a2d-121">Provides flags in addition to those found in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration that the profiler can specify to the [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method when it is loading.</span></span>  
  
 [<span data-ttu-id="d8a2d-122">COR_PRF_JIT_CACHE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d8a2d-122">COR_PRF_JIT_CACHE Enumeration</span></span>](cor-prf-jit-cache-enumeration.md)  
 <span data-ttu-id="d8a2d-123">Indica el resultado de una búsqueda de función en caché.</span><span class="sxs-lookup"><span data-stu-id="d8a2d-123">Indicates the result of a cached function search.</span></span>  
  
 [<span data-ttu-id="d8a2d-124">COR_PRF_MISC (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d8a2d-124">COR_PRF_MISC Enumeration</span></span>](cor-prf-misc-enumeration.md)  
 <span data-ttu-id="d8a2d-125">Contiene valores constantes que especifican identificadores especiales.</span><span class="sxs-lookup"><span data-stu-id="d8a2d-125">Contains constant values that specify special identifiers.</span></span>  
  
 [<span data-ttu-id="d8a2d-126">COR_PRF_MODULE_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d8a2d-126">COR_PRF_MODULE_FLAGS Enumeration</span></span>](cor-prf-module-flags-enumeration.md)  
 <span data-ttu-id="d8a2d-127">Especifica las propiedades de un módulo.</span><span class="sxs-lookup"><span data-stu-id="d8a2d-127">Specifies the properties of a module.</span></span>  
  
 [<span data-ttu-id="d8a2d-128">COR_PRF_MONITOR (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d8a2d-128">COR_PRF_MONITOR Enumeration</span></span>](cor-prf-monitor-enumeration.md)  
 <span data-ttu-id="d8a2d-129">Contiene valores que se usan para especificar el comportamiento, las funcionalidades o los eventos a los que el generador de perfiles quiere suscribirse.</span><span class="sxs-lookup"><span data-stu-id="d8a2d-129">Contains values that are used to specify behavior, capabilities, or events to which the profiler wishes to subscribe.</span></span>  
  
 [<span data-ttu-id="d8a2d-130">COR_PRF_RUNTIME_TYPE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d8a2d-130">COR_PRF_RUNTIME_TYPE Enumeration</span></span>](cor-prf-runtime-type-enumeration.md)  
 <span data-ttu-id="d8a2d-131">Contiene valores que indican la versión de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="d8a2d-131">Contains values that indicate the version of the common language runtime.</span></span>  
  
 [<span data-ttu-id="d8a2d-132">COR_PRF_SNAPSHOT_INFO (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d8a2d-132">COR_PRF_SNAPSHOT_INFO Enumeration</span></span>](cor-prf-snapshot-info-enumeration.md)  
 <span data-ttu-id="d8a2d-133">Especifica cuántos datos se devolverán con una instantánea de pila en cada llamada a la función `StackSnapshotCallback` del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="d8a2d-133">Specifies how much data to pass back with a stack snapshot in each call to the profiler's `StackSnapshotCallback` function.</span></span>  
  
 [<span data-ttu-id="d8a2d-134">COR_PRF_STATIC_TYPE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d8a2d-134">COR_PRF_STATIC_TYPE Enumeration</span></span>](cor-prf-static-type-enumeration.md)  
 <span data-ttu-id="d8a2d-135">Indica si un campo es estático y, si lo es, la calidad estática que se aplica al campo.</span><span class="sxs-lookup"><span data-stu-id="d8a2d-135">Indicates whether a field is static and, if so, the static quality that applies to the field.</span></span>  
  
 [<span data-ttu-id="d8a2d-136">COR_PRF_SUSPEND_REASON (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d8a2d-136">COR_PRF_SUSPEND_REASON Enumeration</span></span>](cor-prf-suspend-reason-enumeration.md)  
 <span data-ttu-id="d8a2d-137">Indica el motivo por el que el tiempo de ejecución se suspendió.</span><span class="sxs-lookup"><span data-stu-id="d8a2d-137">Indicates the reason that the runtime was suspended.</span></span>  
  
 [<span data-ttu-id="d8a2d-138">COR_PRF_TRANSITION_REASON (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d8a2d-138">COR_PRF_TRANSITION_REASON Enumeration</span></span>](cor-prf-transition-reason-enumeration.md)  
 <span data-ttu-id="d8a2d-139">Indica el motivo para una transición desde código administrado a no administrado, y o viceversa.</span><span class="sxs-lookup"><span data-stu-id="d8a2d-139">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d8a2d-140">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="d8a2d-140">Related Sections</span></span>  

 [<span data-ttu-id="d8a2d-141">Información general sobre la generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="d8a2d-141">Profiling Overview</span></span>](profiling-overview.md)  
  
 [<span data-ttu-id="d8a2d-142">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="d8a2d-142">Profiling Interfaces</span></span>](profiling-interfaces.md)  
  
 [<span data-ttu-id="d8a2d-143">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="d8a2d-143">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)  
  
 [<span data-ttu-id="d8a2d-144">Estructuras para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="d8a2d-144">Profiling Structures</span></span>](profiling-structures.md)
