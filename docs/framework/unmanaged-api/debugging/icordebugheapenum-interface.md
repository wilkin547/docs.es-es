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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 79ef77e52e14fede9949121e7ec4575d10b820c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775588"
---
# <a name="icordebugheapenum-interface"></a><span data-ttu-id="315f4-102">ICorDebugHeapEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="315f4-102">ICorDebugHeapEnum Interface</span></span>
<span data-ttu-id="315f4-103">Proporciona un enumerador para los objetos del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="315f4-103">Provides an enumerator for objects on the managed heap.</span></span> <span data-ttu-id="315f4-104">Esta interfaz es una subclase de ICorDebugEnum (interfaz).</span><span class="sxs-lookup"><span data-stu-id="315f4-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="315f4-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="315f4-105">Methods</span></span>  
  
|<span data-ttu-id="315f4-106">Método</span><span class="sxs-lookup"><span data-stu-id="315f4-106">Method</span></span>|<span data-ttu-id="315f4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="315f4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="315f4-108">Next (método)</span><span class="sxs-lookup"><span data-stu-id="315f4-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md)|<span data-ttu-id="315f4-109">Obtiene el número especificado de [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instancias que contienen información acerca de los objetos del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="315f4-109">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="315f4-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="315f4-110">Remarks</span></span>  
 <span data-ttu-id="315f4-111">El `ICorDebugHeapEnum` interfaz implementa la interfaz ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="315f4-111">The `ICorDebugHeapEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="315f4-112">Un `ICorDebugHeapEnum` instancia se rellena con [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instancias mediante una llamada a la [Icordebugprocess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="315f4-112">An `ICorDebugHeapEnum` instance is populated with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) method.</span></span> <span data-ttu-id="315f4-113">Cada [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instancias de la colección representa un objeto activo en el montón o un objeto que no se ha modificado cualquier objeto, pero aún no se han recopilado por el recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="315f4-113">Each [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instance in the collection represents either a live object on the heap or an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span> <span data-ttu-id="315f4-114">El [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) se pueden enumerar los objetos de la colección mediante una llamada a la [Icordebugheapenum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="315f4-114">The [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="315f4-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="315f4-115">Requirements</span></span>  
 <span data-ttu-id="315f4-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="315f4-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="315f4-117">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="315f4-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="315f4-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="315f4-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="315f4-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="315f4-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="315f4-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="315f4-120">See also</span></span>

- [<span data-ttu-id="315f4-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="315f4-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
