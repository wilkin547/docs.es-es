---
title: ICorDebugProcess5::EnumerateHeapRegions (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: 3ab4da3fcf43731587dae6f3a8e82ea48c5ee1ec
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129645"
---
# <a name="icordebugprocess5enumerateheapregions-method"></a><span data-ttu-id="1a6a5-102">ICorDebugProcess5::EnumerateHeapRegions (Método)</span><span class="sxs-lookup"><span data-stu-id="1a6a5-102">ICorDebugProcess5::EnumerateHeapRegions Method</span></span>
<span data-ttu-id="1a6a5-103">Obtiene un enumerador para los intervalos de memoria del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="1a6a5-103">Gets an enumerator for the memory ranges of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a6a5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1a6a5-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHeapRegions(  
   [out] ICorDebugHeapSegmentEnum **ppRegions  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a6a5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1a6a5-105">Parameters</span></span>  
 `ppRegions`  
 <span data-ttu-id="1a6a5-106">enuncia Puntero a la dirección de un objeto de interfaz [icordebugheapsegmentenum (](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) que es un enumerador para los intervalos de memoria en los que residen los objetos en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="1a6a5-106">[out] A pointer to the address of an [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) interface object that is an enumerator for the ranges of memory in which objects reside in the managed heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a6a5-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1a6a5-107">Remarks</span></span>  
 <span data-ttu-id="1a6a5-108">Antes de llamar al método `ICorDebugProcess5::EnumerateHeapRegions`, debe llamar al método [ICorDebugProcess5:: getgcheapinformation (](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) y examinar el valor del campo `areGCStructuresValid` del objeto [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) devuelto para asegurarse de que el montón de recolección de elementos no utilizados en su el estado actual es Enumerable.</span><span class="sxs-lookup"><span data-stu-id="1a6a5-108">Before calling the `ICorDebugProcess5::EnumerateHeapRegions` method, you should call the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method and examine the value of the `areGCStructuresValid` field of the returned [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) object to ensure that the garbage collection heap in its current state is enumerable.</span></span> <span data-ttu-id="1a6a5-109">Además, el método `ICorDebugProcess5::EnumerateHeapRegions` devuelve `E_FAIL` si se adjunta demasiado pronto en la duración del proceso, antes de que se creen regiones de memoria.</span><span class="sxs-lookup"><span data-stu-id="1a6a5-109">In addition, the `ICorDebugProcess5::EnumerateHeapRegions` method returns `E_FAIL` if you attach too early in the lifetime of the process, before memory regions are created.</span></span>  
  
 <span data-ttu-id="1a6a5-110">Se garantiza que este método enumera todas las regiones de memoria que pueden contener objetos administrados, pero no garantiza que los objetos administrados residen realmente en esas regiones.</span><span class="sxs-lookup"><span data-stu-id="1a6a5-110">This method is guaranteed to enumerate all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="1a6a5-111">El objeto de colección [icordebugheapsegmentenum (](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) puede incluir regiones de memoria vacías o reservadas.</span><span class="sxs-lookup"><span data-stu-id="1a6a5-111">The [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) collection object may include empty or reserved memory regions.</span></span>  
  
 <span data-ttu-id="1a6a5-112">El objeto de interfaz [icordebugheapsegmentenum (](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) es un enumerador estándar derivado de la interfaz ICorDebugEnum que le permite enumerar objetos [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="1a6a5-112">The [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) interface object is a standard enumerator derived from the ICorDebugEnum interface that allows you to enumerate [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) objects.</span></span> <span data-ttu-id="1a6a5-113">Cada objeto [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) proporciona información sobre el intervalo de memoria de un segmento determinado, junto con la generación de los objetos en ese segmento.</span><span class="sxs-lookup"><span data-stu-id="1a6a5-113">Each [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) object provides information about the memory range of a particular segment, along with the generation of the objects in that segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a6a5-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1a6a5-114">Requirements</span></span>  
 <span data-ttu-id="1a6a5-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a6a5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a6a5-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1a6a5-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1a6a5-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a6a5-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a6a5-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a6a5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a6a5-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a6a5-119">See also</span></span>

- [<span data-ttu-id="1a6a5-120">ICorDebugProcess5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1a6a5-120">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="1a6a5-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="1a6a5-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
