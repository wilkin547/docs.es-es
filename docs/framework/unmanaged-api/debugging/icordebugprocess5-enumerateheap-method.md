---
description: 'Más información sobre: ICorDebugProcess5:: Enumerateheap ((método)'
title: ICorDebugProcess5::EnumerateHeap (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHeap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHeap
helpviewer_keywords:
- EnumerateHeap method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeap method [.NET Framework debugging]
ms.assetid: b0192104-6073-4089-a4df-dc29ee033074
topic_type:
- apiref
ms.openlocfilehash: b43e7993b114ed64d009f91746ea987198edde74
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722040"
---
# <a name="icordebugprocess5enumerateheap-method"></a><span data-ttu-id="1952f-103">ICorDebugProcess5::EnumerateHeap (Método)</span><span class="sxs-lookup"><span data-stu-id="1952f-103">ICorDebugProcess5::EnumerateHeap Method</span></span>

<span data-ttu-id="1952f-104">Obtiene un enumerador para los objetos en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="1952f-104">Gets an enumerator for the objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1952f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1952f-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHeap(  
    [out] ICorDebugHeapEnum **ppObjects  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1952f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1952f-106">Parameters</span></span>  

 `ppObject`  
 <span data-ttu-id="1952f-107">enuncia Puntero a la dirección de un objeto de interfaz [icordebugheapenum (](icordebugheapenum-interface.md) que es un enumerador para los objetos que residen en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="1952f-107">[out] A pointer to the address of an [ICorDebugHeapEnum](icordebugheapenum-interface.md) interface object that is an enumerator for the objects that reside on the managed heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1952f-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1952f-108">Remarks</span></span>  

 <span data-ttu-id="1952f-109">Antes de llamar al `ICorDebugProcess5::EnumerateHeap` método, debe llamar al método [ICorDebugProcess5:: getgcheapinformation (](icordebugprocess5-getgcheapinformation-method.md) y examinar el valor del `areGCStructuresValid` campo del objeto devuelto [COR_HEAPINFO](cor-heapinfo-structure.md) para asegurarse de que el montón de recolección de elementos no utilizados en su estado actual es Enumerable.</span><span class="sxs-lookup"><span data-stu-id="1952f-109">Before calling the `ICorDebugProcess5::EnumerateHeap` method, you should call the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method and examine the value of the `areGCStructuresValid` field of the returned [COR_HEAPINFO](cor-heapinfo-structure.md) object to ensure that the garbage collection heap in its current state is enumerable.</span></span> <span data-ttu-id="1952f-110">Además, `ICorDebugProcess5::EnumerateHeap` devuelve `E_FAIL` si se adjunta demasiado pronto en la duración del proceso, antes de que se asigne la memoria para el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="1952f-110">In addition, the `ICorDebugProcess5::EnumerateHeap` returns `E_FAIL` if you attach too early in the lifetime of the process, before memory for the managed heap is allocated.</span></span>  
  
 <span data-ttu-id="1952f-111">El objeto de interfaz [icordebugheapenum (](icordebugheapenum-interface.md) es un enumerador estándar derivado de la interfaz ICorDebugEnum que le permite enumerar objetos [COR_HEAPOBJECT](cor-heapobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="1952f-111">The [ICorDebugHeapEnum](icordebugheapenum-interface.md) interface object is a standard enumerator derived from the ICorDebugEnum interface that allows you to enumerate [COR_HEAPOBJECT](cor-heapobject-structure.md) objects.</span></span> <span data-ttu-id="1952f-112">Este método rellena el objeto de colección [icordebugheapenum (](icordebugheapenum-interface.md) con instancias [COR_HEAPOBJECT](cor-heapobject-structure.md) que proporcionan información acerca de todos los objetos.</span><span class="sxs-lookup"><span data-stu-id="1952f-112">This method populates the [ICorDebugHeapEnum](icordebugheapenum-interface.md) collection object with [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that provide information about all objects.</span></span> <span data-ttu-id="1952f-113">La colección también puede incluir instancias de [COR_HEAPOBJECT](cor-heapobject-structure.md) que proporcionan información sobre los objetos que no están raíz de ningún objeto pero que el recolector de elementos no utilizados aún no ha recopilado.</span><span class="sxs-lookup"><span data-stu-id="1952f-113">The collection may also include [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that provide information about objects that are not rooted by any object but have not yet been collected by the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1952f-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1952f-114">Requirements</span></span>  

 <span data-ttu-id="1952f-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1952f-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1952f-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1952f-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1952f-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1952f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1952f-118">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1952f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1952f-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="1952f-119">See also</span></span>

- [<span data-ttu-id="1952f-120">ICorDebugProcess5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1952f-120">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="1952f-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="1952f-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
