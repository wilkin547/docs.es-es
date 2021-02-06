---
description: 'Más información sobre: ICorDebugProcess5:: Enumerateheapregions ((método)'
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
ms.openlocfilehash: 034b1ebcd003e6854fa4f308b0464aac0a8c4839
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649850"
---
# <a name="icordebugprocess5enumerateheapregions-method"></a><span data-ttu-id="8d783-103">ICorDebugProcess5::EnumerateHeapRegions (Método)</span><span class="sxs-lookup"><span data-stu-id="8d783-103">ICorDebugProcess5::EnumerateHeapRegions Method</span></span>

<span data-ttu-id="8d783-104">Obtiene un enumerador para los intervalos de memoria del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="8d783-104">Gets an enumerator for the memory ranges of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d783-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8d783-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHeapRegions(  
   [out] ICorDebugHeapSegmentEnum **ppRegions  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d783-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8d783-106">Parameters</span></span>  

 `ppRegions`  
 <span data-ttu-id="8d783-107">enuncia Puntero a la dirección de un objeto de interfaz [icordebugheapsegmentenum (](icordebugheapsegmentenum-interface.md) que es un enumerador para los intervalos de memoria en los que residen los objetos en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="8d783-107">[out] A pointer to the address of an [ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md) interface object that is an enumerator for the ranges of memory in which objects reside in the managed heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d783-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8d783-108">Remarks</span></span>  

 <span data-ttu-id="8d783-109">Antes de llamar al `ICorDebugProcess5::EnumerateHeapRegions` método, debe llamar al método [ICorDebugProcess5:: getgcheapinformation (](icordebugprocess5-getgcheapinformation-method.md) y examinar el valor del `areGCStructuresValid` campo del objeto devuelto [COR_HEAPINFO](cor-heapinfo-structure.md) para asegurarse de que el montón de recolección de elementos no utilizados en su estado actual es Enumerable.</span><span class="sxs-lookup"><span data-stu-id="8d783-109">Before calling the `ICorDebugProcess5::EnumerateHeapRegions` method, you should call the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method and examine the value of the `areGCStructuresValid` field of the returned [COR_HEAPINFO](cor-heapinfo-structure.md) object to ensure that the garbage collection heap in its current state is enumerable.</span></span> <span data-ttu-id="8d783-110">Además, el `ICorDebugProcess5::EnumerateHeapRegions` método devuelve `E_FAIL` si se adjunta demasiado pronto en la duración del proceso, antes de que se creen regiones de memoria.</span><span class="sxs-lookup"><span data-stu-id="8d783-110">In addition, the `ICorDebugProcess5::EnumerateHeapRegions` method returns `E_FAIL` if you attach too early in the lifetime of the process, before memory regions are created.</span></span>  
  
 <span data-ttu-id="8d783-111">Se garantiza que este método enumera todas las regiones de memoria que pueden contener objetos administrados, pero no garantiza que los objetos administrados residen realmente en esas regiones.</span><span class="sxs-lookup"><span data-stu-id="8d783-111">This method is guaranteed to enumerate all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="8d783-112">El objeto de colección [icordebugheapsegmentenum (](icordebugheapsegmentenum-interface.md) puede incluir regiones de memoria vacías o reservadas.</span><span class="sxs-lookup"><span data-stu-id="8d783-112">The [ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md) collection object may include empty or reserved memory regions.</span></span>  
  
 <span data-ttu-id="8d783-113">El objeto de interfaz [icordebugheapsegmentenum (](icordebugheapsegmentenum-interface.md) es un enumerador estándar derivado de la interfaz ICorDebugEnum que le permite enumerar objetos [COR_SEGMENT](cor-segment-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="8d783-113">The [ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md) interface object is a standard enumerator derived from the ICorDebugEnum interface that allows you to enumerate [COR_SEGMENT](cor-segment-structure.md) objects.</span></span> <span data-ttu-id="8d783-114">Cada objeto de [COR_SEGMENT](cor-segment-structure.md) proporciona información sobre el intervalo de memoria de un segmento determinado, junto con la generación de los objetos en ese segmento.</span><span class="sxs-lookup"><span data-stu-id="8d783-114">Each [COR_SEGMENT](cor-segment-structure.md) object provides information about the memory range of a particular segment, along with the generation of the objects in that segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d783-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8d783-115">Requirements</span></span>  

 <span data-ttu-id="8d783-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d783-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d783-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d783-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d783-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d783-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d783-119">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d783-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d783-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d783-120">See also</span></span>

- [<span data-ttu-id="8d783-121">ICorDebugProcess5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8d783-121">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="8d783-122">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="8d783-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
