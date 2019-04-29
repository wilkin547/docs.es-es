---
title: Enumeraciones para generación de perfiles
ms.date: 03/30/2017
helpviewer_keywords:
- profiling enumerations [.NET Framework]
- enumerations [.NET Framework profiling]
- unmanaged enumerations [.NET Framework], profiling
ms.assetid: 8d5f9570-9853-4ce8-8101-df235d5b258e
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 996352637f34b0b6c0d12e611a6d9e70ab85230e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757578"
---
# <a name="profiling-enumerations"></a><span data-ttu-id="61017-102">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="61017-102">Profiling Enumerations</span></span>
<span data-ttu-id="61017-103">En esta sección se describen las enumeraciones no administradas que utiliza la API de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="61017-103">This section describes the unmanaged enumerations that the profiling API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="61017-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="61017-104">In This Section</span></span>  
 [<span data-ttu-id="61017-105">COR_PRF_CLAUSE_TYPE (enumeración)</span><span class="sxs-lookup"><span data-stu-id="61017-105">COR_PRF_CLAUSE_TYPE Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md)  
 <span data-ttu-id="61017-106">Indica el tipo de cláusula de excepción en la que el código acaba de entrar o de la que acaba de salir.</span><span class="sxs-lookup"><span data-stu-id="61017-106">Indicates the type of exception clause that the code has just entered or left.</span></span>  
  
 [<span data-ttu-id="61017-107">COR_PRF_CODEGEN_FLAGS (enumeración)</span><span class="sxs-lookup"><span data-stu-id="61017-107">COR_PRF_CODEGEN_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md)  
 <span data-ttu-id="61017-108">Define las marcas de generación de código que se pueden establecer con el [Icorprofilerfunctioncontrol](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="61017-108">Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method.</span></span>  
  
 [<span data-ttu-id="61017-109">COR_PRF_FINALIZER_FLAGS (enumeración)</span><span class="sxs-lookup"><span data-stu-id="61017-109">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-finalizer-flags-enumeration.md)  
 <span data-ttu-id="61017-110">Describe el finalizador de un objeto.</span><span class="sxs-lookup"><span data-stu-id="61017-110">Describes the finalizer for an object.</span></span>  
  
 [<span data-ttu-id="61017-111">COR_PRF_GC_GENERATION (enumeración)</span><span class="sxs-lookup"><span data-stu-id="61017-111">COR_PRF_GC_GENERATION Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md)  
 <span data-ttu-id="61017-112">Identifica la generación de una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="61017-112">Identifies a garbage collection generation.</span></span>  
  
 [<span data-ttu-id="61017-113">COR_PRF_GC_REASON (enumeración)</span><span class="sxs-lookup"><span data-stu-id="61017-113">COR_PRF_GC_REASON Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md)  
 <span data-ttu-id="61017-114">Indica el motivo por el que se está produciendo la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="61017-114">Indicates the reason that garbage collection is occurring.</span></span>  
  
 [<span data-ttu-id="61017-115">COR_PRF_GC_ROOT_FLAGS (enumeración)</span><span class="sxs-lookup"><span data-stu-id="61017-115">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-flags-enumeration.md)  
 <span data-ttu-id="61017-116">Indica las propiedades de la raíz de un recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="61017-116">Indicates properties of a garbage collector root.</span></span>  
  
 [<span data-ttu-id="61017-117">COR_PRF_GC_ROOT_KIND (enumeración)</span><span class="sxs-lookup"><span data-stu-id="61017-117">COR_PRF_GC_ROOT_KIND Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-kind-enumeration.md)  
 <span data-ttu-id="61017-118">Indica el tipo de raíz del recolector de elementos que se expone mediante el [ICorProfilerCallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="61017-118">Indicates the kind of garbage collector root that is exposed by the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) callback.</span></span>  
  
 [<span data-ttu-id="61017-119">COR_PRF_HIGH_MONITOR (enumeración)</span><span class="sxs-lookup"><span data-stu-id="61017-119">COR_PRF_HIGH_MONITOR Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md)  
 <span data-ttu-id="61017-120">Proporciona marcas, además de los que se encuentran en el [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeración que el generador de perfiles puede especificar para el [icorprofilerinfo5:: Seteventmask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) método cuando se está cargando.</span><span class="sxs-lookup"><span data-stu-id="61017-120">Provides flags in addition to those found in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration that the profiler can specify to the [ICorProfilerInfo5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method when it is loading.</span></span>  
  
 [<span data-ttu-id="61017-121">COR_PRF_JIT_CACHE (enumeración)</span><span class="sxs-lookup"><span data-stu-id="61017-121">COR_PRF_JIT_CACHE Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-jit-cache-enumeration.md)  
 <span data-ttu-id="61017-122">Indica el resultado de una búsqueda de función en caché.</span><span class="sxs-lookup"><span data-stu-id="61017-122">Indicates the result of a cached function search.</span></span>  
  
 [<span data-ttu-id="61017-123">COR_PRF_MISC (enumeración)</span><span class="sxs-lookup"><span data-stu-id="61017-123">COR_PRF_MISC Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-misc-enumeration.md)  
 <span data-ttu-id="61017-124">Contiene valores constantes que especifican identificadores especiales.</span><span class="sxs-lookup"><span data-stu-id="61017-124">Contains constant values that specify special identifiers.</span></span>  
  
 [<span data-ttu-id="61017-125">COR_PRF_MODULE_FLAGS (enumeración)</span><span class="sxs-lookup"><span data-stu-id="61017-125">COR_PRF_MODULE_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md)  
 <span data-ttu-id="61017-126">Especifica las propiedades de un módulo.</span><span class="sxs-lookup"><span data-stu-id="61017-126">Specifies the properties of a module.</span></span>  
  
 [<span data-ttu-id="61017-127">COR_PRF_MONITOR (enumeración)</span><span class="sxs-lookup"><span data-stu-id="61017-127">COR_PRF_MONITOR Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)  
 <span data-ttu-id="61017-128">Contiene valores que se usan para especificar el comportamiento, las funcionalidades o los eventos a los que el generador de perfiles quiere suscribirse.</span><span class="sxs-lookup"><span data-stu-id="61017-128">Contains values that are used to specify behavior, capabilities, or events to which the profiler wishes to subscribe.</span></span>  
  
 [<span data-ttu-id="61017-129">COR_PRF_RUNTIME_TYPE (enumeración)</span><span class="sxs-lookup"><span data-stu-id="61017-129">COR_PRF_RUNTIME_TYPE Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-runtime-type-enumeration.md)  
 <span data-ttu-id="61017-130">Contiene valores que indican la versión de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="61017-130">Contains values that indicate the version of the common language runtime.</span></span>  
  
 [<span data-ttu-id="61017-131">COR_PRF_SNAPSHOT_INFO (enumeración)</span><span class="sxs-lookup"><span data-stu-id="61017-131">COR_PRF_SNAPSHOT_INFO Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-snapshot-info-enumeration.md)  
 <span data-ttu-id="61017-132">Especifica cuántos datos se devolverán con una instantánea de pila en cada llamada a la función `StackSnapshotCallback` del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="61017-132">Specifies how much data to pass back with a stack snapshot in each call to the profiler's `StackSnapshotCallback` function.</span></span>  
  
 [<span data-ttu-id="61017-133">COR_PRF_STATIC_TYPE (enumeración)</span><span class="sxs-lookup"><span data-stu-id="61017-133">COR_PRF_STATIC_TYPE Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md)  
 <span data-ttu-id="61017-134">Indica si un campo es estático y, si lo es, la calidad estática que se aplica al campo.</span><span class="sxs-lookup"><span data-stu-id="61017-134">Indicates whether a field is static and, if so, the static quality that applies to the field.</span></span>  
  
 [<span data-ttu-id="61017-135">COR_PRF_SUSPEND_REASON (enumeración)</span><span class="sxs-lookup"><span data-stu-id="61017-135">COR_PRF_SUSPEND_REASON Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md)  
 <span data-ttu-id="61017-136">Indica el motivo por el que el tiempo de ejecución se suspendió.</span><span class="sxs-lookup"><span data-stu-id="61017-136">Indicates the reason that the runtime was suspended.</span></span>  
  
 [<span data-ttu-id="61017-137">COR_PRF_TRANSITION_REASON (enumeración)</span><span class="sxs-lookup"><span data-stu-id="61017-137">COR_PRF_TRANSITION_REASON Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md)  
 <span data-ttu-id="61017-138">Indica el motivo para una transición desde código administrado a no administrado, y o viceversa.</span><span class="sxs-lookup"><span data-stu-id="61017-138">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="61017-139">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="61017-139">Related Sections</span></span>  
 [<span data-ttu-id="61017-140">Información general sobre la generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="61017-140">Profiling Overview</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [<span data-ttu-id="61017-141">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="61017-141">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
  
 [<span data-ttu-id="61017-142">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="61017-142">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [<span data-ttu-id="61017-143">Estructuras para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="61017-143">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
