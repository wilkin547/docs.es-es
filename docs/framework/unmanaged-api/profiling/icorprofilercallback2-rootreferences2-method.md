---
description: 'Más información sobre: método ICorProfilerCallback2:: Rootreferences2 ('
title: ICorProfilerCallback2::RootReferences2 (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.RootReferences2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::RootReferences2
helpviewer_keywords:
- RootReferences2 method [.NET Framework profiling]
- ICorProfilerCallback2::RootReferences2 method [.NET Framework profiling]
ms.assetid: 55a2f907-d216-42eb-8f2f-e5d59c2eebd6
topic_type:
- apiref
ms.openlocfilehash: a599014cc9fb47b103a136b9e5569d38031c9377
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799088"
---
# <a name="icorprofilercallback2rootreferences2-method"></a><span data-ttu-id="64f54-103">ICorProfilerCallback2::RootReferences2 (Método)</span><span class="sxs-lookup"><span data-stu-id="64f54-103">ICorProfilerCallback2::RootReferences2 Method</span></span>

<span data-ttu-id="64f54-104">Notifica al generador de perfiles las referencias raíz después de que se haya producido la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="64f54-104">Notifies the profiler about root references after a garbage collection has occurred.</span></span> <span data-ttu-id="64f54-105">Este método es una extensión del método [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) .</span><span class="sxs-lookup"><span data-stu-id="64f54-105">This method is an extension of the [ICorProfilerCallback::RootReferences](icorprofilercallback-rootreferences-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64f54-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="64f54-106">Syntax</span></span>  
  
```cpp  
HRESULT RootReferences2(  
    [in] ULONG  cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_KIND rootKinds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_FLAGS rootFlags[],  
    [in, size_is(cRootRefs)] UINT_PTR rootIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64f54-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="64f54-107">Parameters</span></span>  

 `cRootRefs`  
 <span data-ttu-id="64f54-108">de El número de elementos de las `rootRefIds` `rootKinds` matrices,, `rootFlags` y `rootIds` .</span><span class="sxs-lookup"><span data-stu-id="64f54-108">[in] The number of elements in the `rootRefIds`, `rootKinds`, `rootFlags`, and `rootIds` arrays.</span></span>  
  
 `rootRefIds`  
 <span data-ttu-id="64f54-109">de Matriz de identificadores de objeto, cada uno de los cuales hace referencia a un objeto estático o a un objeto de la pila.</span><span class="sxs-lookup"><span data-stu-id="64f54-109">[in] An array of object IDs, each of which references either a static object or an object on the stack.</span></span> <span data-ttu-id="64f54-110">Los elementos de la `rootKinds` matriz proporcionan información para clasificar los elementos correspondientes de la `rootRefIds` matriz.</span><span class="sxs-lookup"><span data-stu-id="64f54-110">Elements in the `rootKinds` array provide information to classify corresponding elements in the `rootRefIds` array.</span></span>  
  
 `rootKinds`  
 <span data-ttu-id="64f54-111">de Matriz de valores de [COR_PRF_GC_ROOT_KIND](cor-prf-gc-root-kind-enumeration.md) que indican el tipo de la raíz de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="64f54-111">[in] An array of [COR_PRF_GC_ROOT_KIND](cor-prf-gc-root-kind-enumeration.md) values that indicate the type of the garbage collection root.</span></span>  
  
 `rootFlags`  
 <span data-ttu-id="64f54-112">de Matriz de valores de [COR_PRF_GC_ROOT_FLAGS](cor-prf-gc-root-flags-enumeration.md) que describen las propiedades de una raíz de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="64f54-112">[in] An array of [COR_PRF_GC_ROOT_FLAGS](cor-prf-gc-root-flags-enumeration.md) values that describe the properties of a garbage collection root.</span></span>  
  
 `rootIds`  
 <span data-ttu-id="64f54-113">de Matriz de valores de UINT_PTR que apuntan a un entero que contiene información adicional sobre la raíz de la recolección de elementos no utilizados, dependiendo del valor del `rootKinds` parámetro.</span><span class="sxs-lookup"><span data-stu-id="64f54-113">[in] An array of UINT_PTR values that point to an integer that contains additional information about the garbage collection root, depending on the value of the `rootKinds` parameter.</span></span>  
  
 <span data-ttu-id="64f54-114">Si el tipo de la raíz es una pila, el identificador raíz es para la función que contiene la variable.</span><span class="sxs-lookup"><span data-stu-id="64f54-114">If the type of the root is a stack, the root ID is for the function that contains the variable.</span></span> <span data-ttu-id="64f54-115">Si el identificador raíz es 0, la función es una función sin nombre que es interna de CLR.</span><span class="sxs-lookup"><span data-stu-id="64f54-115">If that root ID is 0, the function is an unnamed function that is internal to the CLR.</span></span> <span data-ttu-id="64f54-116">Si el tipo de la raíz es un identificador, el identificador raíz es para el identificador de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="64f54-116">If the type of the root is a handle, the root ID is for the garbage collection handle.</span></span> <span data-ttu-id="64f54-117">Para los demás tipos raíz, el ID. es un valor opaco y debe omitirse.</span><span class="sxs-lookup"><span data-stu-id="64f54-117">For the other root types, the ID is an opaque value and should be ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64f54-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="64f54-118">Remarks</span></span>  

 <span data-ttu-id="64f54-119">Las `rootRefIds` `rootKinds` matrices,, `rootFlags` y `rootIds` son matrices paralelas.</span><span class="sxs-lookup"><span data-stu-id="64f54-119">The `rootRefIds`, `rootKinds`, `rootFlags`, and `rootIds` arrays are parallel arrays.</span></span> <span data-ttu-id="64f54-120">Es decir,,, `rootRefIds[i]` `rootKinds[i]` `rootFlags[i]` y `rootIds[i]` afectan a la misma raíz.</span><span class="sxs-lookup"><span data-stu-id="64f54-120">That is, `rootRefIds[i]`, `rootKinds[i]`, `rootFlags[i]`, and `rootIds[i]` all concern the same root.</span></span>  
  
 <span data-ttu-id="64f54-121">`RootReferences` `RootReferences2` Se llama a y para notificar al generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="64f54-121">Both `RootReferences` and `RootReferences2` are called to notify the profiler.</span></span> <span data-ttu-id="64f54-122">Normalmente, los generadores implementarán un método o el otro, pero no ambos, porque la información `RootReferences2` que se pasa es un superconjunto de que se ha pasado `RootReferences` .</span><span class="sxs-lookup"><span data-stu-id="64f54-122">Profilers will normally implement one method or the other, but not both, because the information passed in `RootReferences2` is a superset of that passed in `RootReferences`.</span></span>  
  
 <span data-ttu-id="64f54-123">Es posible que las entradas de `rootRefIds` sean cero, lo que implica que la referencia raíz correspondiente es NULL y no hace referencia a un objeto en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="64f54-123">It is possible for entries in `rootRefIds` to be zero, which implies that the corresponding root reference is null and does not refer to an object on the managed heap.</span></span>  
  
 <span data-ttu-id="64f54-124">Los identificadores de objeto devueltos por `RootReferences2` no son válidos durante la devolución de llamada, ya que la recolección de elementos no utilizados podría estar en medio de mover objetos de direcciones antiguas a direcciones nuevas.</span><span class="sxs-lookup"><span data-stu-id="64f54-124">The object IDs returned by `RootReferences2` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects from old addresses to new addresses.</span></span> <span data-ttu-id="64f54-125">Por lo tanto, los generadores de perfiles no deben intentar inspeccionar objetos durante una llamada a `RootReferences2`.</span><span class="sxs-lookup"><span data-stu-id="64f54-125">Therefore, profilers should not attempt to inspect objects during a `RootReferences2` call.</span></span> <span data-ttu-id="64f54-126">Cuando se llama a [ICorProfilerCallback2:: garbagecollectionfinished (](icorprofilercallback2-garbagecollectionfinished-method.md) , todos los objetos se movieron a sus nuevas ubicaciones y se pueden inspeccionar de forma segura.</span><span class="sxs-lookup"><span data-stu-id="64f54-126">When [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) is called, all objects have been moved to their new locations and can be safely inspected.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64f54-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="64f54-127">Requirements</span></span>  

 <span data-ttu-id="64f54-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64f54-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64f54-129">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="64f54-129">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="64f54-130">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64f54-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64f54-131">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64f54-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64f54-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="64f54-132">See also</span></span>

- [<span data-ttu-id="64f54-133">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="64f54-133">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="64f54-134">ICorProfilerCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="64f54-134">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
