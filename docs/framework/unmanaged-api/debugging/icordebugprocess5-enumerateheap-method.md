---
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
ms.openlocfilehash: c8cfc9cdf6580a002f6ac15080012a9e8c63be20
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129647"
---
# <a name="icordebugprocess5enumerateheap-method"></a><span data-ttu-id="9aced-102">ICorDebugProcess5::EnumerateHeap (Método)</span><span class="sxs-lookup"><span data-stu-id="9aced-102">ICorDebugProcess5::EnumerateHeap Method</span></span>
<span data-ttu-id="9aced-103">Obtiene un enumerador para los objetos en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="9aced-103">Gets an enumerator for the objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9aced-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9aced-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHeap(  
    [out] ICorDebugHeapEnum **ppObjects  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9aced-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9aced-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="9aced-106">enuncia Puntero a la dirección de un objeto de interfaz [icordebugheapenum (](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) que es un enumerador para los objetos que residen en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="9aced-106">[out] A pointer to the address of an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object that is an enumerator for the objects that reside on the managed heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9aced-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9aced-107">Remarks</span></span>  
 <span data-ttu-id="9aced-108">Antes de llamar al método `ICorDebugProcess5::EnumerateHeap`, debe llamar al método [ICorDebugProcess5:: getgcheapinformation (](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) y examinar el valor del campo `areGCStructuresValid` del objeto [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) devuelto para asegurarse de que el montón de recolección de elementos no utilizados en su el estado actual es Enumerable.</span><span class="sxs-lookup"><span data-stu-id="9aced-108">Before calling the `ICorDebugProcess5::EnumerateHeap` method, you should call the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method and examine the value of the `areGCStructuresValid` field of the returned [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) object to ensure that the garbage collection heap in its current state is enumerable.</span></span> <span data-ttu-id="9aced-109">Además, el `ICorDebugProcess5::EnumerateHeap` devuelve `E_FAIL` si se adjunta demasiado pronto en la duración del proceso, antes de que se asigne la memoria para el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="9aced-109">In addition, the `ICorDebugProcess5::EnumerateHeap` returns `E_FAIL` if you attach too early in the lifetime of the process, before memory for the managed heap is allocated.</span></span>  
  
 <span data-ttu-id="9aced-110">El objeto de interfaz [icordebugheapenum (](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) es un enumerador estándar derivado de la interfaz ICorDebugEnum que le permite enumerar objetos [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="9aced-110">The [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object is a standard enumerator derived from the ICorDebugEnum interface that allows you to enumerate [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects.</span></span> <span data-ttu-id="9aced-111">Este método rellena el objeto de colección [icordebugheapenum (](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) con instancias [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) que proporcionan información acerca de todos los objetos.</span><span class="sxs-lookup"><span data-stu-id="9aced-111">This method populates the [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) collection object with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that provide information about all objects.</span></span> <span data-ttu-id="9aced-112">La colección también puede incluir instancias de [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) que proporcionan información sobre los objetos que no están raíz de ningún objeto pero que el recolector de elementos no utilizados aún no ha recopilado.</span><span class="sxs-lookup"><span data-stu-id="9aced-112">The collection may also include [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that provide information about objects that are not rooted by any object but have not yet been collected by the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9aced-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9aced-113">Requirements</span></span>  
 <span data-ttu-id="9aced-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9aced-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9aced-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9aced-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9aced-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9aced-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9aced-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9aced-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9aced-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="9aced-118">See also</span></span>

- [<span data-ttu-id="9aced-119">ICorDebugProcess5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9aced-119">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="9aced-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="9aced-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
