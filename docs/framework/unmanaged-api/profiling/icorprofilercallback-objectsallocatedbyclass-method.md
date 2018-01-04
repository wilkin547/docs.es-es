---
title: "ICorProfilerCallback::ObjectsAllocatedByClass (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ObjectsAllocatedByClass
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ObjectsAllocatedByClass
helpviewer_keywords:
- ObjectsAllocatedByClass method [.NET Framework profiling]
- ICorProfilerCallback::ObjectsAllocatedByClass method [.NET Framework profiling]
ms.assetid: 91d688f3-a80e-419d-9755-ff94bc04188a
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4adeda7ac884b37bcfc2b0c9599dd8e36c469747
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a><span data-ttu-id="44186-102">ICorProfilerCallback::ObjectsAllocatedByClass (Método)</span><span class="sxs-lookup"><span data-stu-id="44186-102">ICorProfilerCallback::ObjectsAllocatedByClass Method</span></span>
<span data-ttu-id="44186-103">Notifica al generador de perfiles sobre el número de instancias de cada clase especificada que se han creado desde la recolección de elementos no utilizados más reciente.</span><span class="sxs-lookup"><span data-stu-id="44186-103">Notifies the profiler about the number of instances of each specified class that have been created since the most recent garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44186-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="44186-104">Syntax</span></span>  
  
```  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="44186-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="44186-105">Parameters</span></span>  
 `cClassCount`  
 <span data-ttu-id="44186-106">[in] El tamaño de la `classIds` y `cObjects` matrices.</span><span class="sxs-lookup"><span data-stu-id="44186-106">[in] The size of the `classIds` and `cObjects` arrays.</span></span>  
  
 `classIds`  
 <span data-ttu-id="44186-107">[in] Una matriz de identificadores, donde cada identificador especifica una clase con una o varias instancias de clases.</span><span class="sxs-lookup"><span data-stu-id="44186-107">[in] An array of class IDs, where each ID specifies a class with one or more instances.</span></span>  
  
 `cObjects`  
 <span data-ttu-id="44186-108">[in] Una matriz de enteros, donde cada entero que especifica el número de instancias de la clase correspondiente en el `classIds` matriz.</span><span class="sxs-lookup"><span data-stu-id="44186-108">[in] An array of integers, where each integer specifies the number of instances for the corresponding class in the `classIds` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44186-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="44186-109">Remarks</span></span>  
 <span data-ttu-id="44186-110">El `classIds` y `cObjects` son matrices paralelas.</span><span class="sxs-lookup"><span data-stu-id="44186-110">The `classIds` and `cObjects` arrays are parallel arrays.</span></span> <span data-ttu-id="44186-111">Por ejemplo, `classIds[i]` y `cObjects[i]` hacen referencia a la misma clase.</span><span class="sxs-lookup"><span data-stu-id="44186-111">For example, `classIds[i]` and `cObjects[i]` reference the same class.</span></span> <span data-ttu-id="44186-112">Si no se ha creado ninguna instancia de una clase desde la recopilación de elementos no utilizados anterior, se omite la clase.</span><span class="sxs-lookup"><span data-stu-id="44186-112">If no instance of a class has been created since the previous garbage collection, the class is omitted.</span></span> <span data-ttu-id="44186-113">El `ObjectsAllocatedByClass` devolución de llamada no informarán los objetos asignados en el montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="44186-113">The `ObjectsAllocatedByClass` callback will not report objects allocated in the large object heap.</span></span>  
  
 <span data-ttu-id="44186-114">Los números notifican por `ObjectsAllocatedByClass` sólo son estimaciones.</span><span class="sxs-lookup"><span data-stu-id="44186-114">The numbers reported by `ObjectsAllocatedByClass` are only estimates.</span></span> <span data-ttu-id="44186-115">Para obtener recuentos exactos, utilice [ICorProfilerCallback:: ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span><span class="sxs-lookup"><span data-stu-id="44186-115">For exact counts, use [ICorProfilerCallback::ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span></span>  
  
 <span data-ttu-id="44186-116">El `classIds` matriz puede contener una o varias entradas null si el correspondiente `cObjects` matriz tiene tipos que se están descargando.</span><span class="sxs-lookup"><span data-stu-id="44186-116">The `classIds` array may contain one or more null entries if the corresponding `cObjects` array has types that are unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44186-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="44186-117">Requirements</span></span>  
 <span data-ttu-id="44186-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44186-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44186-119">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="44186-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="44186-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44186-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44186-121">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44186-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44186-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="44186-122">See Also</span></span>  
 [<span data-ttu-id="44186-123">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="44186-123">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
