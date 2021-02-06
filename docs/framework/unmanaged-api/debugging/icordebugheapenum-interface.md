---
description: 'Más información acerca de: interfaz Icordebugheapenum ('
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
ms.openlocfilehash: c8a2f46bf412e2c4b2fe43d3eb50169191f40445
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660900"
---
# <a name="icordebugheapenum-interface"></a><span data-ttu-id="95dcd-103">ICorDebugHeapEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="95dcd-103">ICorDebugHeapEnum Interface</span></span>

<span data-ttu-id="95dcd-104">Proporciona un enumerador para los objetos del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="95dcd-104">Provides an enumerator for objects on the managed heap.</span></span> <span data-ttu-id="95dcd-105">Esta interfaz es una subclase de la interfaz ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="95dcd-105">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="95dcd-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="95dcd-106">Methods</span></span>  
  
|<span data-ttu-id="95dcd-107">Método</span><span class="sxs-lookup"><span data-stu-id="95dcd-107">Method</span></span>|<span data-ttu-id="95dcd-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="95dcd-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="95dcd-109">Next (método)</span><span class="sxs-lookup"><span data-stu-id="95dcd-109">Next Method</span></span>](icordebugheapenum-next-method.md)|<span data-ttu-id="95dcd-110">Obtiene el número especificado de instancias de [COR_HEAPOBJECT](cor-heapobject-structure.md) que contienen información sobre los objetos del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="95dcd-110">Gets the specified number of [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95dcd-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="95dcd-111">Remarks</span></span>  

 <span data-ttu-id="95dcd-112">La `ICorDebugHeapEnum` interfaz implementa la interfaz ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="95dcd-112">The `ICorDebugHeapEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="95dcd-113">Una `ICorDebugHeapEnum` instancia se rellena con [COR_HEAPOBJECT](cor-heapobject-structure.md) instancias llamando al método [ICorDebugProcess5:: enumerateheap (](icordebugprocess5-enumerateheap-method.md) .</span><span class="sxs-lookup"><span data-stu-id="95dcd-113">An `ICorDebugHeapEnum` instance is populated with [COR_HEAPOBJECT](cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeap](icordebugprocess5-enumerateheap-method.md) method.</span></span> <span data-ttu-id="95dcd-114">Cada instancia de [COR_HEAPOBJECT](cor-heapobject-structure.md) de la colección representa un objeto activo en el montón o un objeto que no está raíz de ningún objeto y que el recolector de elementos no utilizados aún no ha recopilado.</span><span class="sxs-lookup"><span data-stu-id="95dcd-114">Each [COR_HEAPOBJECT](cor-heapobject-structure.md) instance in the collection represents either a live object on the heap or an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span> <span data-ttu-id="95dcd-115">Los objetos [COR_HEAPOBJECT](cor-heapobject-structure.md) de la colección se pueden enumerar llamando al método [Icordebugheapenum (:: Next](icordebugheapenum-next-method.md) .</span><span class="sxs-lookup"><span data-stu-id="95dcd-115">The [COR_HEAPOBJECT](cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapEnum::Next](icordebugheapenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95dcd-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="95dcd-116">Requirements</span></span>  

 <span data-ttu-id="95dcd-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95dcd-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95dcd-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="95dcd-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95dcd-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95dcd-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95dcd-120">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95dcd-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95dcd-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="95dcd-121">See also</span></span>

- [<span data-ttu-id="95dcd-122">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="95dcd-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
