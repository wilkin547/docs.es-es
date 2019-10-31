---
title: ICorDebugHeapSegmentEnum (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugHealRegionEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapSegmentEnum
helpviewer_keywords:
- ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 20fc1b9d-e228-4107-bd76-53934c1724b9
topic_type:
- apiref
ms.openlocfilehash: e9679029cd54ac44832add9bc4f47f8c8e9a26a2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138449"
---
# <a name="icordebugheapsegmentenum-interface"></a><span data-ttu-id="db470-102">ICorDebugHeapSegmentEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="db470-102">ICorDebugHeapSegmentEnum Interface</span></span>
<span data-ttu-id="db470-103">Proporciona un enumerador para las regiones de memoria del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="db470-103">Provides an enumerator for the memory regions of the managed heap.</span></span> <span data-ttu-id="db470-104">Esta interfaz es una subclase de la interfaz ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="db470-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="db470-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="db470-105">Methods</span></span>  
  
|<span data-ttu-id="db470-106">Método</span><span class="sxs-lookup"><span data-stu-id="db470-106">Method</span></span>|<span data-ttu-id="db470-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="db470-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="db470-108">Next (método)</span><span class="sxs-lookup"><span data-stu-id="db470-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md)|<span data-ttu-id="db470-109">Obtiene el número especificado de instancias de [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) que contienen información sobre las regiones del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="db470-109">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about regions of the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db470-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="db470-110">Remarks</span></span>  
 <span data-ttu-id="db470-111">La interfaz de `ICorDebugHeapSegmentEnum` implementa la interfaz ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="db470-111">The `ICorDebugHeapSegmentEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="db470-112">Una instancia de `ICorDebugHeapSegmentEnum` se rellena con instancias de [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) llamando al método [ICorDebugProcess5:: enumerateheapregions (](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) .</span><span class="sxs-lookup"><span data-stu-id="db470-112">An `ICorDebugHeapSegmentEnum` instance is populated with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) method.</span></span> <span data-ttu-id="db470-113">Los objetos [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) de la colección se pueden enumerar llamando al método [Icordebugheapsegmentenum (:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md) .</span><span class="sxs-lookup"><span data-stu-id="db470-113">The [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapSegmentEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="db470-114">Un objeto de colección `ICorDebugHeapSegmentEnum` enumera todas las regiones de memoria que pueden contener objetos administrados, pero no garantiza que los objetos administrados residan realmente en esas regiones.</span><span class="sxs-lookup"><span data-stu-id="db470-114">An `ICorDebugHeapSegmentEnum` collection object enumerates all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="db470-115">Puede incluir información sobre las regiones de memoria vacía o reservada.</span><span class="sxs-lookup"><span data-stu-id="db470-115">It may include information about empty or reserved memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db470-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="db470-116">Requirements</span></span>  
 <span data-ttu-id="db470-117">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db470-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db470-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db470-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db470-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db470-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db470-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db470-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db470-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="db470-121">See also</span></span>

- [<span data-ttu-id="db470-122">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="db470-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
