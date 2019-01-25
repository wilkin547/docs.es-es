---
title: ICorProfilerCallback::ObjectsAllocatedByClass (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectsAllocatedByClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectsAllocatedByClass
helpviewer_keywords:
- ObjectsAllocatedByClass method [.NET Framework profiling]
- ICorProfilerCallback::ObjectsAllocatedByClass method [.NET Framework profiling]
ms.assetid: 91d688f3-a80e-419d-9755-ff94bc04188a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1200ca14b91c101a8145a3aed8023002ddb9298b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746640"
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a><span data-ttu-id="9d53b-102">ICorProfilerCallback::ObjectsAllocatedByClass (Método)</span><span class="sxs-lookup"><span data-stu-id="9d53b-102">ICorProfilerCallback::ObjectsAllocatedByClass Method</span></span>
<span data-ttu-id="9d53b-103">Notifica al generador de perfiles sobre el número de instancias de cada clase especificada que se han creado desde la última recolección.</span><span class="sxs-lookup"><span data-stu-id="9d53b-103">Notifies the profiler about the number of instances of each specified class that have been created since the most recent garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d53b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9d53b-104">Syntax</span></span>  
  
```  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9d53b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9d53b-105">Parameters</span></span>  
 `cClassCount`  
 <span data-ttu-id="9d53b-106">[in] El tamaño de la `classIds` y `cObjects` matrices.</span><span class="sxs-lookup"><span data-stu-id="9d53b-106">[in] The size of the `classIds` and `cObjects` arrays.</span></span>  
  
 `classIds`  
 <span data-ttu-id="9d53b-107">[in] Una matriz de identificadores, donde cada identificador especifica una clase con una o varias instancias de clases.</span><span class="sxs-lookup"><span data-stu-id="9d53b-107">[in] An array of class IDs, where each ID specifies a class with one or more instances.</span></span>  
  
 `cObjects`  
 <span data-ttu-id="9d53b-108">[in] Una matriz de enteros, donde cada entero que especifica el número de instancias de la clase correspondiente en el `classIds` matriz.</span><span class="sxs-lookup"><span data-stu-id="9d53b-108">[in] An array of integers, where each integer specifies the number of instances for the corresponding class in the `classIds` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d53b-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9d53b-109">Remarks</span></span>  
 <span data-ttu-id="9d53b-110">El `classIds` y `cObjects` son matrices paralelas.</span><span class="sxs-lookup"><span data-stu-id="9d53b-110">The `classIds` and `cObjects` arrays are parallel arrays.</span></span> <span data-ttu-id="9d53b-111">Por ejemplo, `classIds[i]` y `cObjects[i]` hacen referencia a la misma clase.</span><span class="sxs-lookup"><span data-stu-id="9d53b-111">For example, `classIds[i]` and `cObjects[i]` reference the same class.</span></span> <span data-ttu-id="9d53b-112">Si la colección de elementos no utilizados anterior no se ha creado ninguna instancia de una clase, se omite la clase.</span><span class="sxs-lookup"><span data-stu-id="9d53b-112">If no instance of a class has been created since the previous garbage collection, the class is omitted.</span></span> <span data-ttu-id="9d53b-113">El `ObjectsAllocatedByClass` devolución de llamada no notificará los objetos asignados en el montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="9d53b-113">The `ObjectsAllocatedByClass` callback will not report objects allocated in the large object heap.</span></span>  
  
 <span data-ttu-id="9d53b-114">Los números notifican por `ObjectsAllocatedByClass` son solo estimaciones.</span><span class="sxs-lookup"><span data-stu-id="9d53b-114">The numbers reported by `ObjectsAllocatedByClass` are only estimates.</span></span> <span data-ttu-id="9d53b-115">Para obtener recuentos exactos, usar [ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span><span class="sxs-lookup"><span data-stu-id="9d53b-115">For exact counts, use [ICorProfilerCallback::ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span></span>  
  
 <span data-ttu-id="9d53b-116">El `classIds` matriz puede contener una o más entradas null si correspondiente `cObjects` matriz tiene tipos que se están descargando.</span><span class="sxs-lookup"><span data-stu-id="9d53b-116">The `classIds` array may contain one or more null entries if the corresponding `cObjects` array has types that are unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d53b-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9d53b-117">Requirements</span></span>  
 <span data-ttu-id="9d53b-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d53b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d53b-119">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9d53b-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9d53b-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d53b-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d53b-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d53b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d53b-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d53b-122">See also</span></span>
- [<span data-ttu-id="9d53b-123">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9d53b-123">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
