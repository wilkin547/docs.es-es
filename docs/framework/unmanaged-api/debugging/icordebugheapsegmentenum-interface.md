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
ms.openlocfilehash: 0a5a87c71bea603073c35dd851e443ca8c497523
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210441"
---
# <a name="icordebugheapsegmentenum-interface"></a><span data-ttu-id="554db-102">ICorDebugHeapSegmentEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="554db-102">ICorDebugHeapSegmentEnum Interface</span></span>
<span data-ttu-id="554db-103">Proporciona un enumerador para las regiones de memoria del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="554db-103">Provides an enumerator for the memory regions of the managed heap.</span></span> <span data-ttu-id="554db-104">Esta interfaz es una subclase de la interfaz ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="554db-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="554db-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="554db-105">Methods</span></span>  
  
|<span data-ttu-id="554db-106">Método</span><span class="sxs-lookup"><span data-stu-id="554db-106">Method</span></span>|<span data-ttu-id="554db-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="554db-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="554db-108">Next (Método)</span><span class="sxs-lookup"><span data-stu-id="554db-108">Next Method</span></span>](icordebugheapsegmentenum-next-method.md)|<span data-ttu-id="554db-109">Obtiene el número especificado de instancias de [COR_HEAPOBJECT](cor-heapobject-structure.md) que contienen información sobre las regiones del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="554db-109">Gets the specified number of [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that contain information about regions of the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="554db-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="554db-110">Remarks</span></span>  
 <span data-ttu-id="554db-111">La `ICorDebugHeapSegmentEnum` interfaz implementa la interfaz ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="554db-111">The `ICorDebugHeapSegmentEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="554db-112">Una `ICorDebugHeapSegmentEnum` instancia se rellena con [COR_HEAPOBJECT](cor-heapobject-structure.md) instancias llamando al método [ICorDebugProcess5:: enumerateheapregions (](icordebugprocess5-enumerateheapregions-method.md) .</span><span class="sxs-lookup"><span data-stu-id="554db-112">An `ICorDebugHeapSegmentEnum` instance is populated with [COR_HEAPOBJECT](cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeapRegions](icordebugprocess5-enumerateheapregions-method.md) method.</span></span> <span data-ttu-id="554db-113">Los objetos [COR_HEAPOBJECT](cor-heapobject-structure.md) de la colección se pueden enumerar llamando al método [Icordebugheapsegmentenum (:: Next](icordebugheapsegmentenum-next-method.md) .</span><span class="sxs-lookup"><span data-stu-id="554db-113">The [COR_HEAPOBJECT](cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapSegmentEnum::Next](icordebugheapsegmentenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="554db-114">Un `ICorDebugHeapSegmentEnum` objeto de colección enumera todas las regiones de memoria que pueden contener objetos administrados, pero no garantiza que los objetos administrados residan realmente en esas regiones.</span><span class="sxs-lookup"><span data-stu-id="554db-114">An `ICorDebugHeapSegmentEnum` collection object enumerates all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="554db-115">Puede incluir información sobre las regiones de memoria vacía o reservada.</span><span class="sxs-lookup"><span data-stu-id="554db-115">It may include information about empty or reserved memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="554db-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="554db-116">Requirements</span></span>  
 <span data-ttu-id="554db-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="554db-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="554db-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="554db-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="554db-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="554db-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="554db-120">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="554db-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="554db-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="554db-121">See also</span></span>

- [<span data-ttu-id="554db-122">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="554db-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
