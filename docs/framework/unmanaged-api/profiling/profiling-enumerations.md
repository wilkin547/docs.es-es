---
title: "Enumeraciones para generación de perfiles"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- profiling enumerations [.NET Framework]
- enumerations [.NET Framework profiling]
- unmanaged enumerations [.NET Framework], profiling
ms.assetid: 8d5f9570-9853-4ce8-8101-df235d5b258e
caps.latest.revision: "21"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2e0b539c8e455040cc97f37f75476b0efe796abb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="profiling-enumerations"></a><span data-ttu-id="b3a07-102">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="b3a07-102">Profiling Enumerations</span></span>
<span data-ttu-id="b3a07-103">En esta sección se describen las enumeraciones no administradas que utiliza la API de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="b3a07-103">This section describes the unmanaged enumerations that the profiling API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b3a07-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b3a07-104">In This Section</span></span>  
 [<span data-ttu-id="b3a07-105">COR_PRF_CLAUSE_TYPE (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b3a07-105">COR_PRF_CLAUSE_TYPE Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md)  
 <span data-ttu-id="b3a07-106">Indica el tipo de cláusula de excepción en la que el código acaba de entrar o de la que acaba de salir.</span><span class="sxs-lookup"><span data-stu-id="b3a07-106">Indicates the type of exception clause that the code has just entered or left.</span></span>  
  
 [<span data-ttu-id="b3a07-107">COR_PRF_CODEGEN_FLAGS (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b3a07-107">COR_PRF_CODEGEN_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md)  
 <span data-ttu-id="b3a07-108">Define las marcas de generación de código que se pueden establecer con el [icorprofilerfunctioncontrol:: Setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="b3a07-108">Defines the code generation flags that can be set with the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) method.</span></span>  
  
 [<span data-ttu-id="b3a07-109">COR_PRF_FINALIZER_FLAGS (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b3a07-109">COR_PRF_FINALIZER_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-finalizer-flags-enumeration.md)  
 <span data-ttu-id="b3a07-110">Describe el finalizador de un objeto.</span><span class="sxs-lookup"><span data-stu-id="b3a07-110">Describes the finalizer for an object.</span></span>  
  
 [<span data-ttu-id="b3a07-111">COR_PRF_GC_GENERATION (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b3a07-111">COR_PRF_GC_GENERATION Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md)  
 <span data-ttu-id="b3a07-112">Identifica la generación de una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b3a07-112">Identifies a garbage collection generation.</span></span>  
  
 [<span data-ttu-id="b3a07-113">COR_PRF_GC_REASON (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b3a07-113">COR_PRF_GC_REASON Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md)  
 <span data-ttu-id="b3a07-114">Indica el motivo por el que se está produciendo la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b3a07-114">Indicates the reason that garbage collection is occurring.</span></span>  
  
 [<span data-ttu-id="b3a07-115">COR_PRF_GC_ROOT_FLAGS (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b3a07-115">COR_PRF_GC_ROOT_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-flags-enumeration.md)  
 <span data-ttu-id="b3a07-116">Indica las propiedades de la raíz de un recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b3a07-116">Indicates properties of a garbage collector root.</span></span>  
  
 [<span data-ttu-id="b3a07-117">COR_PRF_GC_ROOT_KIND (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b3a07-117">COR_PRF_GC_ROOT_KIND Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-kind-enumeration.md)  
 <span data-ttu-id="b3a07-118">Indica el tipo de raíz del recolector de elementos no utilizados que se expone mediante el [ICorProfilerCallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="b3a07-118">Indicates the kind of garbage collector root that is exposed by the [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) callback.</span></span>  
  
 [<span data-ttu-id="b3a07-119">COR_PRF_HIGH_MONITOR (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b3a07-119">COR_PRF_HIGH_MONITOR Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md)  
 <span data-ttu-id="b3a07-120">Proporciona marcas, además de las que se encuentran en el [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeración que puede especificar el generador de perfiles a la [icorprofilerinfo5:: Seteventmask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) método cuando se está cargando.</span><span class="sxs-lookup"><span data-stu-id="b3a07-120">Provides flags in addition to those found in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration that the profiler can specify to the [ICorProfilerInfo5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method when it is loading.</span></span>  
  
 [<span data-ttu-id="b3a07-121">COR_PRF_JIT_CACHE (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b3a07-121">COR_PRF_JIT_CACHE Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-jit-cache-enumeration.md)  
 <span data-ttu-id="b3a07-122">Indica el resultado de una búsqueda de función en caché.</span><span class="sxs-lookup"><span data-stu-id="b3a07-122">Indicates the result of a cached function search.</span></span>  
  
 [<span data-ttu-id="b3a07-123">COR_PRF_MISC (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b3a07-123">COR_PRF_MISC Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-misc-enumeration.md)  
 <span data-ttu-id="b3a07-124">Contiene valores constantes que especifican identificadores especiales.</span><span class="sxs-lookup"><span data-stu-id="b3a07-124">Contains constant values that specify special identifiers.</span></span>  
  
 [<span data-ttu-id="b3a07-125">COR_PRF_MODULE_FLAGS (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b3a07-125">COR_PRF_MODULE_FLAGS Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md)  
 <span data-ttu-id="b3a07-126">Especifica las propiedades de un módulo.</span><span class="sxs-lookup"><span data-stu-id="b3a07-126">Specifies the properties of a module.</span></span>  
  
 [<span data-ttu-id="b3a07-127">COR_PRF_MONITOR (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b3a07-127">COR_PRF_MONITOR Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)  
 <span data-ttu-id="b3a07-128">Contiene valores que se usan para especificar el comportamiento, las funcionalidades o los eventos a los que el generador de perfiles quiere suscribirse.</span><span class="sxs-lookup"><span data-stu-id="b3a07-128">Contains values that are used to specify behavior, capabilities, or events to which the profiler wishes to subscribe.</span></span>  
  
 [<span data-ttu-id="b3a07-129">COR_PRF_RUNTIME_TYPE (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b3a07-129">COR_PRF_RUNTIME_TYPE Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-runtime-type-enumeration.md)  
 <span data-ttu-id="b3a07-130">Contiene valores que indican la versión de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="b3a07-130">Contains values that indicate the version of the common language runtime.</span></span>  
  
 [<span data-ttu-id="b3a07-131">COR_PRF_SNAPSHOT_INFO (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b3a07-131">COR_PRF_SNAPSHOT_INFO Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-snapshot-info-enumeration.md)  
 <span data-ttu-id="b3a07-132">Especifica cuántos datos se devolverán con una instantánea de pila en cada llamada a la función `StackSnapshotCallback` del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="b3a07-132">Specifies how much data to pass back with a stack snapshot in each call to the profiler's `StackSnapshotCallback` function.</span></span>  
  
 [<span data-ttu-id="b3a07-133">COR_PRF_STATIC_TYPE (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b3a07-133">COR_PRF_STATIC_TYPE Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md)  
 <span data-ttu-id="b3a07-134">Indica si un campo es estático y, si lo es, la calidad estática que se aplica al campo.</span><span class="sxs-lookup"><span data-stu-id="b3a07-134">Indicates whether a field is static and, if so, the static quality that applies to the field.</span></span>  
  
 [<span data-ttu-id="b3a07-135">COR_PRF_SUSPEND_REASON (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b3a07-135">COR_PRF_SUSPEND_REASON Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md)  
 <span data-ttu-id="b3a07-136">Indica el motivo por el que el tiempo de ejecución se suspendió.</span><span class="sxs-lookup"><span data-stu-id="b3a07-136">Indicates the reason that the runtime was suspended.</span></span>  
  
 [<span data-ttu-id="b3a07-137">COR_PRF_TRANSITION_REASON (enumeración)</span><span class="sxs-lookup"><span data-stu-id="b3a07-137">COR_PRF_TRANSITION_REASON Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md)  
 <span data-ttu-id="b3a07-138">Indica el motivo para una transición desde código administrado a no administrado, y o viceversa.</span><span class="sxs-lookup"><span data-stu-id="b3a07-138">Indicates the reason for a transition from managed to unmanaged code, or vice versa.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b3a07-139">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="b3a07-139">Related Sections</span></span>  
 [<span data-ttu-id="b3a07-140">Información general de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="b3a07-140">Profiling Overview</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [<span data-ttu-id="b3a07-141">Interfaces de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="b3a07-141">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
  
 [<span data-ttu-id="b3a07-142">Funciones estáticas globales de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="b3a07-142">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [<span data-ttu-id="b3a07-143">Estructuras de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="b3a07-143">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
