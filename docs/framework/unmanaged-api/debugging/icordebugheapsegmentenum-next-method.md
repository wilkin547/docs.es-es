---
description: 'Más información sobre: Icordebugheapsegmentenum (:: Next (método)'
title: ICorDebugHeapSegmentEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapSegmentEnum::Next
helpviewer_keywords:
- ICorDebugHeapSegmentEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 51625fd0-7399-49c7-b22b-5dfb05451fe6
topic_type:
- apiref
ms.openlocfilehash: 8d2ddfb4df82969fa9cf580ed8a7f903f9d6c260
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803682"
---
# <a name="icordebugheapsegmentenumnext-method"></a><span data-ttu-id="894b1-103">ICorDebugHeapSegmentEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="894b1-103">ICorDebugHeapSegmentEnum::Next Method</span></span>

<span data-ttu-id="894b1-104">Obtiene el número especificado de instancias de [COR_SEGMENT](cor-segment-structure.md) que contienen información sobre las regiones de memoria del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="894b1-104">Gets the specified number of [COR_SEGMENT](cor-segment-structure.md) instances that contain information about memory regions of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="894b1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="894b1-105">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_SEGMENT segments[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="894b1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="894b1-106">Parameters</span></span>  

 <span data-ttu-id="894b1-107">celt</span><span class="sxs-lookup"><span data-stu-id="894b1-107">celt</span></span>  
 <span data-ttu-id="894b1-108">de Número de segmentos que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="894b1-108">[in] The number of segments to be retrieved.</span></span>  
  
 <span data-ttu-id="894b1-109">segmentos</span><span class="sxs-lookup"><span data-stu-id="894b1-109">segments</span></span>  
 <span data-ttu-id="894b1-110">enuncia Matriz de punteros, cada uno de los cuales apunta a un [COR_SEGMENT](cor-segment-structure.md) objeto que proporciona información sobre una región de memoria en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="894b1-110">[out] An array of pointers, each of which points to a [COR_SEGMENT](cor-segment-structure.md) object that provides information about a region of memory in the managed heap.</span></span>  
  
 <span data-ttu-id="894b1-111">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="894b1-111">pceltFetched</span></span>  
 <span data-ttu-id="894b1-112">enuncia Puntero al número de objetos [COR_SEGMENT](cor-segment-structure.md) realmente devueltos en `segments` .</span><span class="sxs-lookup"><span data-stu-id="894b1-112">[out] A pointer to the number of [COR_SEGMENT](cor-segment-structure.md) objects actually returned in `segments`.</span></span> <span data-ttu-id="894b1-113">Este valor puede ser `null` si `celt` es 1.</span><span class="sxs-lookup"><span data-stu-id="894b1-113">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="894b1-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="894b1-114">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="894b1-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="894b1-115">Requirements</span></span>  

 <span data-ttu-id="894b1-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="894b1-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="894b1-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="894b1-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="894b1-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="894b1-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="894b1-119">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="894b1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="894b1-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="894b1-120">See also</span></span>

- [<span data-ttu-id="894b1-121">ICorDebugHeapSegmentEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="894b1-121">ICorDebugHeapSegmentEnum Interface</span></span>](icordebugheapsegmentenum-interface.md)
- [<span data-ttu-id="894b1-122">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="894b1-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
