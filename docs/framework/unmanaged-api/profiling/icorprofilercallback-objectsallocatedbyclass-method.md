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
ms.openlocfilehash: 7176c0f88daad64f793131aca8c6d9fa592a878c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503281"
---
# <a name="icorprofilercallbackobjectsallocatedbyclass-method"></a><span data-ttu-id="f2f53-102">ICorProfilerCallback::ObjectsAllocatedByClass (Método)</span><span class="sxs-lookup"><span data-stu-id="f2f53-102">ICorProfilerCallback::ObjectsAllocatedByClass Method</span></span>
<span data-ttu-id="f2f53-103">Notifica al generador de perfiles el número de instancias de cada clase especificada que se han creado desde la última recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="f2f53-103">Notifies the profiler about the number of instances of each specified class that have been created since the most recent garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2f53-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f2f53-104">Syntax</span></span>  
  
```cpp  
HRESULT ObjectsAllocatedByClass(  
    [in] ULONG   cClassCount,  
    [in, size_is(cClassCount)] ClassID classIds[] ,  
    [in, size_is(cClassCount)] ULONG   cObjects[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2f53-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f2f53-105">Parameters</span></span>  
 `cClassCount`  
 <span data-ttu-id="f2f53-106">de Tamaño de las `classIds` matrices y `cObjects` .</span><span class="sxs-lookup"><span data-stu-id="f2f53-106">[in] The size of the `classIds` and `cObjects` arrays.</span></span>  
  
 `classIds`  
 <span data-ttu-id="f2f53-107">de Matriz de identificadores de clase, donde cada identificador especifica una clase con una o más instancias.</span><span class="sxs-lookup"><span data-stu-id="f2f53-107">[in] An array of class IDs, where each ID specifies a class with one or more instances.</span></span>  
  
 `cObjects`  
 <span data-ttu-id="f2f53-108">de Matriz de enteros, donde cada entero especifica el número de instancias de la clase correspondiente en la `classIds` matriz.</span><span class="sxs-lookup"><span data-stu-id="f2f53-108">[in] An array of integers, where each integer specifies the number of instances for the corresponding class in the `classIds` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2f53-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f2f53-109">Remarks</span></span>  
 <span data-ttu-id="f2f53-110">Las `classIds` `cObjects` matrices y son matrices paralelas.</span><span class="sxs-lookup"><span data-stu-id="f2f53-110">The `classIds` and `cObjects` arrays are parallel arrays.</span></span> <span data-ttu-id="f2f53-111">Por ejemplo, `classIds[i]` y `cObjects[i]` hacen referencia a la misma clase.</span><span class="sxs-lookup"><span data-stu-id="f2f53-111">For example, `classIds[i]` and `cObjects[i]` reference the same class.</span></span> <span data-ttu-id="f2f53-112">Si no se ha creado ninguna instancia de una clase desde la recolección de elementos no utilizados anterior, se omite la clase.</span><span class="sxs-lookup"><span data-stu-id="f2f53-112">If no instance of a class has been created since the previous garbage collection, the class is omitted.</span></span> <span data-ttu-id="f2f53-113">La `ObjectsAllocatedByClass` devolución de llamada no notificará los objetos asignados en el montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="f2f53-113">The `ObjectsAllocatedByClass` callback will not report objects allocated in the large object heap.</span></span>  
  
 <span data-ttu-id="f2f53-114">Los números devueltos por `ObjectsAllocatedByClass` son solo estimaciones.</span><span class="sxs-lookup"><span data-stu-id="f2f53-114">The numbers reported by `ObjectsAllocatedByClass` are only estimates.</span></span> <span data-ttu-id="f2f53-115">Para los recuentos exactos, utilice [ICorProfilerCallback:: ObjectAllocated](icorprofilercallback-objectallocated-method.md).</span><span class="sxs-lookup"><span data-stu-id="f2f53-115">For exact counts, use [ICorProfilerCallback::ObjectAllocated](icorprofilercallback-objectallocated-method.md).</span></span>  
  
 <span data-ttu-id="f2f53-116">La `classIds` matriz puede contener una o varias entradas nulas si la `cObjects` matriz correspondiente tiene tipos que se están descargando.</span><span class="sxs-lookup"><span data-stu-id="f2f53-116">The `classIds` array may contain one or more null entries if the corresponding `cObjects` array has types that are unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2f53-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f2f53-117">Requirements</span></span>  
 <span data-ttu-id="f2f53-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2f53-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2f53-119">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f2f53-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f2f53-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2f53-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2f53-121">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2f53-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2f53-122">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="f2f53-122">See also</span></span>

- [<span data-ttu-id="f2f53-123">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f2f53-123">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
