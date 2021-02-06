---
description: 'Más información acerca de: interfaz Icordebugheapsegmentenum ('
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
ms.openlocfilehash: 614bae0ea5e3eb7816fdeec23a0dc7aa6e44801d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660887"
---
# <a name="icordebugheapsegmentenum-interface"></a><span data-ttu-id="89578-103">ICorDebugHeapSegmentEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="89578-103">ICorDebugHeapSegmentEnum Interface</span></span>

<span data-ttu-id="89578-104">Proporciona un enumerador para las regiones de memoria del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="89578-104">Provides an enumerator for the memory regions of the managed heap.</span></span> <span data-ttu-id="89578-105">Esta interfaz es una subclase de la interfaz ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="89578-105">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="89578-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="89578-106">Methods</span></span>  
  
|<span data-ttu-id="89578-107">Método</span><span class="sxs-lookup"><span data-stu-id="89578-107">Method</span></span>|<span data-ttu-id="89578-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="89578-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="89578-109">Next (método)</span><span class="sxs-lookup"><span data-stu-id="89578-109">Next Method</span></span>](icordebugheapsegmentenum-next-method.md)|<span data-ttu-id="89578-110">Obtiene el número especificado de instancias de [COR_SEGMENT](cor-segment-structure.md) que contienen información sobre las regiones del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="89578-110">Gets the specified number of [COR_SEGMENT](cor-segment-structure.md) instances that contain information about regions of the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89578-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="89578-111">Remarks</span></span>  

 <span data-ttu-id="89578-112">La `ICorDebugHeapSegmentEnum` interfaz implementa la interfaz ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="89578-112">The `ICorDebugHeapSegmentEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="89578-113">Una `ICorDebugHeapSegmentEnum` instancia se rellena con [COR_SEGMENT](cor-segment-structure.md) instancias llamando al método [ICorDebugProcess5:: enumerateheapregions (](icordebugprocess5-enumerateheapregions-method.md) .</span><span class="sxs-lookup"><span data-stu-id="89578-113">An `ICorDebugHeapSegmentEnum` instance is populated with [COR_SEGMENT](cor-segment-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeapRegions](icordebugprocess5-enumerateheapregions-method.md) method.</span></span> <span data-ttu-id="89578-114">Los objetos [COR_SEGMENT](cor-segment-structure.md) de la colección se pueden enumerar llamando al método [Icordebugheapsegmentenum (:: Next](icordebugheapsegmentenum-next-method.md) .</span><span class="sxs-lookup"><span data-stu-id="89578-114">The [COR_SEGMENT](cor-segment-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapSegmentEnum::Next](icordebugheapsegmentenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="89578-115">Un `ICorDebugHeapSegmentEnum` objeto de colección enumera todas las regiones de memoria que pueden contener objetos administrados, pero no garantiza que los objetos administrados residan realmente en esas regiones.</span><span class="sxs-lookup"><span data-stu-id="89578-115">An `ICorDebugHeapSegmentEnum` collection object enumerates all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="89578-116">Puede incluir información sobre las regiones de memoria vacía o reservada.</span><span class="sxs-lookup"><span data-stu-id="89578-116">It may include information about empty or reserved memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89578-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="89578-117">Requirements</span></span>  

 <span data-ttu-id="89578-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89578-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89578-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="89578-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="89578-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89578-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89578-121">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89578-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89578-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="89578-122">See also</span></span>

- [<span data-ttu-id="89578-123">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="89578-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
