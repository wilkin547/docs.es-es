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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cac4ddc33bcaf07d615fd186a63d96b1f4f6464c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417737"
---
# <a name="icordebugheapsegmentenum-interface"></a><span data-ttu-id="9ec41-102">ICorDebugHeapSegmentEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9ec41-102">ICorDebugHeapSegmentEnum Interface</span></span>
<span data-ttu-id="9ec41-103">Proporciona un enumerador para las regiones de memoria del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="9ec41-103">Provides an enumerator for the memory regions of the managed heap.</span></span> <span data-ttu-id="9ec41-104">Esta interfaz es una subclase de ICorDebugEnum (interfaz).</span><span class="sxs-lookup"><span data-stu-id="9ec41-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9ec41-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="9ec41-105">Methods</span></span>  
  
|<span data-ttu-id="9ec41-106">Método</span><span class="sxs-lookup"><span data-stu-id="9ec41-106">Method</span></span>|<span data-ttu-id="9ec41-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ec41-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9ec41-108">Next (método)</span><span class="sxs-lookup"><span data-stu-id="9ec41-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md)|<span data-ttu-id="9ec41-109">Obtiene el número especificado de [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instancias que contienen información acerca de las áreas del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="9ec41-109">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about regions of the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ec41-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9ec41-110">Remarks</span></span>  
 <span data-ttu-id="9ec41-111">El `ICorDebugHeapSegmentEnum` interfaz implementa ICorDebugEnum (interfaz).</span><span class="sxs-lookup"><span data-stu-id="9ec41-111">The `ICorDebugHeapSegmentEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="9ec41-112">Un `ICorDebugHeapSegmentEnum` instancia se rellena con [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instancias mediante una llamada a la [icordebugprocess5:: Enumerateheapregions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="9ec41-112">An `ICorDebugHeapSegmentEnum` instance is populated with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) method.</span></span> <span data-ttu-id="9ec41-113">El [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) pueden enumerar objetos de la colección mediante una llamada a la [icordebugheapsegmentenum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="9ec41-113">The [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapSegmentEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="9ec41-114">Un `ICorDebugHeapSegmentEnum` objeto de colección enumera todas las regiones de memoria que pueden contener objetos administrados, pero no garantiza que los objetos administrados que residen realmente en esas regiones.</span><span class="sxs-lookup"><span data-stu-id="9ec41-114">An `ICorDebugHeapSegmentEnum` collection object enumerates all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="9ec41-115">Puede incluir información acerca de las áreas de memoria reservada o vacío.</span><span class="sxs-lookup"><span data-stu-id="9ec41-115">It may include information about empty or reserved memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ec41-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9ec41-116">Requirements</span></span>  
 <span data-ttu-id="9ec41-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ec41-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ec41-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ec41-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ec41-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ec41-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ec41-120">**Versiones de .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ec41-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ec41-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ec41-121">See Also</span></span>  
 [<span data-ttu-id="9ec41-122">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="9ec41-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
