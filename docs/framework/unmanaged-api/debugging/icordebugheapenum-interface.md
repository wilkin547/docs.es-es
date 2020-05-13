---
title: ICorDebugHeapEnum (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugHeapEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapEnum
helpviewer_keywords:
- ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 99cbc1eb-d539-4f76-a0d8-b93348112f14
topic_type:
- apiref
ms.openlocfilehash: ff290cd8ad331ff109c3bbbf87638d22b9b183bc
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208543"
---
# <a name="icordebugheapenum-interface"></a><span data-ttu-id="b0b81-102">ICorDebugHeapEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b0b81-102">ICorDebugHeapEnum Interface</span></span>
<span data-ttu-id="b0b81-103">Proporciona un enumerador para los objetos del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="b0b81-103">Provides an enumerator for objects on the managed heap.</span></span> <span data-ttu-id="b0b81-104">Esta interfaz es una subclase de la interfaz ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="b0b81-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b0b81-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="b0b81-105">Methods</span></span>  
  
|<span data-ttu-id="b0b81-106">Método</span><span class="sxs-lookup"><span data-stu-id="b0b81-106">Method</span></span>|<span data-ttu-id="b0b81-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0b81-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b0b81-108">Next (Método)</span><span class="sxs-lookup"><span data-stu-id="b0b81-108">Next Method</span></span>](icordebugheapenum-next-method.md)|<span data-ttu-id="b0b81-109">Obtiene el número especificado de instancias de [COR_HEAPOBJECT](cor-heapobject-structure.md) que contienen información sobre los objetos del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="b0b81-109">Gets the specified number of [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0b81-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b0b81-110">Remarks</span></span>  
 <span data-ttu-id="b0b81-111">La `ICorDebugHeapEnum` interfaz implementa la interfaz ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="b0b81-111">The `ICorDebugHeapEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="b0b81-112">Una `ICorDebugHeapEnum` instancia se rellena con [COR_HEAPOBJECT](cor-heapobject-structure.md) instancias llamando al método [ICorDebugProcess5:: enumerateheap (](icordebugprocess5-enumerateheap-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b0b81-112">An `ICorDebugHeapEnum` instance is populated with [COR_HEAPOBJECT](cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeap](icordebugprocess5-enumerateheap-method.md) method.</span></span> <span data-ttu-id="b0b81-113">Cada instancia de [COR_HEAPOBJECT](cor-heapobject-structure.md) de la colección representa un objeto activo en el montón o un objeto que no está raíz de ningún objeto y que el recolector de elementos no utilizados aún no ha recopilado.</span><span class="sxs-lookup"><span data-stu-id="b0b81-113">Each [COR_HEAPOBJECT](cor-heapobject-structure.md) instance in the collection represents either a live object on the heap or an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span> <span data-ttu-id="b0b81-114">Los objetos [COR_HEAPOBJECT](cor-heapobject-structure.md) de la colección se pueden enumerar llamando al método [Icordebugheapenum (:: Next](icordebugheapenum-next-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b0b81-114">The [COR_HEAPOBJECT](cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapEnum::Next](icordebugheapenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0b81-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b0b81-115">Requirements</span></span>  
 <span data-ttu-id="b0b81-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0b81-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0b81-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0b81-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0b81-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0b81-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0b81-119">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0b81-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0b81-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b0b81-120">See also</span></span>

- [<span data-ttu-id="b0b81-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="b0b81-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
