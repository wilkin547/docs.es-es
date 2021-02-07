---
description: 'Más información sobre: ICorProfilerCallback:: ObjectsAllocatedByClass ((método)'
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
ms.openlocfilehash: df9f3dde27664de7db4afb264b221f640753ddb3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745065"
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a><span data-ttu-id="62853-103">ICorProfilerCallback::ObjectsAllocatedByClass (Método)</span><span class="sxs-lookup"><span data-stu-id="62853-103">ICorProfilerCallback::ObjectsAllocatedByClass Method</span></span>

<span data-ttu-id="62853-104">Notifica al generador de perfiles el número de instancias de cada clase especificada que se han creado desde la última recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="62853-104">Notifies the profiler about the number of instances of each specified class that have been created since the most recent garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62853-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="62853-105">Syntax</span></span>  
  
```cpp  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="62853-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="62853-106">Parameters</span></span>  

 `cClassCount`  
 <span data-ttu-id="62853-107">de Tamaño de las `classIds` matrices y `cObjects` .</span><span class="sxs-lookup"><span data-stu-id="62853-107">[in] The size of the `classIds` and `cObjects` arrays.</span></span>  
  
 `classIds`  
 <span data-ttu-id="62853-108">de Matriz de identificadores de clase, donde cada identificador especifica una clase con una o más instancias.</span><span class="sxs-lookup"><span data-stu-id="62853-108">[in] An array of class IDs, where each ID specifies a class with one or more instances.</span></span>  
  
 `cObjects`  
 <span data-ttu-id="62853-109">de Matriz de enteros, donde cada entero especifica el número de instancias de la clase correspondiente en la `classIds` matriz.</span><span class="sxs-lookup"><span data-stu-id="62853-109">[in] An array of integers, where each integer specifies the number of instances for the corresponding class in the `classIds` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62853-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="62853-110">Remarks</span></span>  

 <span data-ttu-id="62853-111">Las `classIds` `cObjects` matrices y son matrices paralelas.</span><span class="sxs-lookup"><span data-stu-id="62853-111">The `classIds` and `cObjects` arrays are parallel arrays.</span></span> <span data-ttu-id="62853-112">Por ejemplo, `classIds[i]` y `cObjects[i]` hacen referencia a la misma clase.</span><span class="sxs-lookup"><span data-stu-id="62853-112">For example, `classIds[i]` and `cObjects[i]` reference the same class.</span></span> <span data-ttu-id="62853-113">Si no se ha creado ninguna instancia de una clase desde la recolección de elementos no utilizados anterior, se omite la clase.</span><span class="sxs-lookup"><span data-stu-id="62853-113">If no instance of a class has been created since the previous garbage collection, the class is omitted.</span></span> <span data-ttu-id="62853-114">La `ObjectsAllocatedByClass` devolución de llamada no notificará los objetos asignados en el montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="62853-114">The `ObjectsAllocatedByClass` callback will not report objects allocated in the large object heap.</span></span>  
  
 <span data-ttu-id="62853-115">Los números devueltos por `ObjectsAllocatedByClass` son solo estimaciones.</span><span class="sxs-lookup"><span data-stu-id="62853-115">The numbers reported by `ObjectsAllocatedByClass` are only estimates.</span></span> <span data-ttu-id="62853-116">Para los recuentos exactos, utilice [ICorProfilerCallback:: ObjectAllocated](icorprofilercallback-objectallocated-method.md).</span><span class="sxs-lookup"><span data-stu-id="62853-116">For exact counts, use [ICorProfilerCallback::ObjectAllocated](icorprofilercallback-objectallocated-method.md).</span></span>  
  
 <span data-ttu-id="62853-117">La `classIds` matriz puede contener una o varias entradas nulas si la `cObjects` matriz correspondiente tiene tipos que se están descargando.</span><span class="sxs-lookup"><span data-stu-id="62853-117">The `classIds` array may contain one or more null entries if the corresponding `cObjects` array has types that are unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62853-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="62853-118">Requirements</span></span>  

 <span data-ttu-id="62853-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62853-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62853-120">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="62853-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="62853-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62853-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62853-122">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62853-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62853-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="62853-123">See also</span></span>

- [<span data-ttu-id="62853-124">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="62853-124">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
