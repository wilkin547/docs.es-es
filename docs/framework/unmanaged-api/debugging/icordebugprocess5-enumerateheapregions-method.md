---
title: "ICorDebugProcess5::EnumerateHeapRegions (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugProcess5.EnumerateHeapRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHeapRegions
helpviewer_keywords:
- EnumerateHeapRegions method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeapRegions method [.NET Framework debugging]
ms.assetid: b1edba68-9c36-4f69-be9f-678ce0b33480
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 478a8490e57946a08670d9f86e1f6ebcc67703a6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess5enumerateheapregions-method"></a><span data-ttu-id="da24f-102">ICorDebugProcess5::EnumerateHeapRegions (Método)</span><span class="sxs-lookup"><span data-stu-id="da24f-102">ICorDebugProcess5::EnumerateHeapRegions Method</span></span>
<span data-ttu-id="da24f-103">Obtiene un enumerador para los intervalos de memoria del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="da24f-103">Gets an enumerator for the memory ranges of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da24f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="da24f-104">Syntax</span></span>  
  
```  
HRESULT EnumerateHeapRegions(  
   [out] ICorDebugHeapSegmentEnum **ppRegions  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="da24f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="da24f-105">Parameters</span></span>  
 `ppRegions`  
 <span data-ttu-id="da24f-106">[out] Un puntero a la dirección de un [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) objeto de interfaz que es un enumerador para los intervalos de memoria en el que los objetos residan en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="da24f-106">[out] A pointer to the address of an [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) interface object that is an enumerator for the ranges of memory in which objects reside in the managed heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da24f-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="da24f-107">Remarks</span></span>  
 <span data-ttu-id="da24f-108">Antes de llamar a la `ICorDebugProcess5::EnumerateHeapRegions` método, debe llamar a la [icordebugprocess5:: Getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) (método) y examine el valor de la `areGCStructuresValid` campo devuelto [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) objeto para asegurarse de que el montón de elementos no utilizados en su estado actual es enumerable.</span><span class="sxs-lookup"><span data-stu-id="da24f-108">Before calling the `ICorDebugProcess5::EnumerateHeapRegions` method, you should call the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method and examine the value of the `areGCStructuresValid` field of the returned [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) object to ensure that the garbage collection heap in its current state is enumerable.</span></span> <span data-ttu-id="da24f-109">Además, el `ICorDebugProcess5::EnumerateHeapRegions` método `E_FAIL` si adjunta demasiado pronto en la duración del proceso, antes que la memoria se crean las regiones.</span><span class="sxs-lookup"><span data-stu-id="da24f-109">In addition, the `ICorDebugProcess5::EnumerateHeapRegions` method returns `E_FAIL` if you attach too early in the lifetime of the process, before memory regions are created.</span></span>  
  
 <span data-ttu-id="da24f-110">Este método se garantiza para enumerar todas las regiones de memoria que pueden contener objetos administrados, pero no garantiza que los objetos administrados que residen realmente en esas regiones.</span><span class="sxs-lookup"><span data-stu-id="da24f-110">This method is guaranteed to enumerate all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="da24f-111">El [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) objeto de colección puede incluir las regiones de memoria reservada o vacío.</span><span class="sxs-lookup"><span data-stu-id="da24f-111">The [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) collection object may include empty or reserved memory regions.</span></span>  
  
 <span data-ttu-id="da24f-112">El [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) objeto de interfaz es un enumerador estándar que se deriva de la interfaz de ICorDebugEnum que permite enumerar [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) objetos.</span><span class="sxs-lookup"><span data-stu-id="da24f-112">The [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) interface object is a standard enumerator derived from the ICorDebugEnum interface that allows you to enumerate [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) objects.</span></span> <span data-ttu-id="da24f-113">Cada [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) objeto proporciona información acerca del intervalo de memoria de un segmento en particular, junto con la generación de los objetos de ese segmento.</span><span class="sxs-lookup"><span data-stu-id="da24f-113">Each [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) object provides information about the memory range of a particular segment, along with the generation of the objects in that segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da24f-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="da24f-114">Requirements</span></span>  
 <span data-ttu-id="da24f-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da24f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da24f-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="da24f-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="da24f-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da24f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da24f-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da24f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da24f-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="da24f-119">See Also</span></span>  
 [<span data-ttu-id="da24f-120">ICorDebugProcess5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="da24f-120">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="da24f-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="da24f-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
