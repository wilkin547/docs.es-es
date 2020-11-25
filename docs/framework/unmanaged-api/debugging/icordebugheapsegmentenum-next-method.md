---
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
ms.openlocfilehash: 6398fa2962b347a260e23e4fed8cf272a2916a9e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704622"
---
# <a name="icordebugheapsegmentenumnext-method"></a><span data-ttu-id="fdfe6-102">ICorDebugHeapSegmentEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="fdfe6-102">ICorDebugHeapSegmentEnum::Next Method</span></span>

<span data-ttu-id="fdfe6-103">Obtiene el número especificado de instancias de [COR_SEGMENT](cor-segment-structure.md) que contienen información sobre las regiones de memoria del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="fdfe6-103">Gets the specified number of [COR_SEGMENT](cor-segment-structure.md) instances that contain information about memory regions of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdfe6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fdfe6-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_SEGMENT segments[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fdfe6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fdfe6-105">Parameters</span></span>  

 <span data-ttu-id="fdfe6-106">celt</span><span class="sxs-lookup"><span data-stu-id="fdfe6-106">celt</span></span>  
 <span data-ttu-id="fdfe6-107">de Número de segmentos que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="fdfe6-107">[in] The number of segments to be retrieved.</span></span>  
  
 <span data-ttu-id="fdfe6-108">segmentos</span><span class="sxs-lookup"><span data-stu-id="fdfe6-108">segments</span></span>  
 <span data-ttu-id="fdfe6-109">enuncia Matriz de punteros, cada uno de los cuales apunta a un [COR_SEGMENT](cor-segment-structure.md) objeto que proporciona información sobre una región de memoria en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="fdfe6-109">[out] An array of pointers, each of which points to a [COR_SEGMENT](cor-segment-structure.md) object that provides information about a region of memory in the managed heap.</span></span>  
  
 <span data-ttu-id="fdfe6-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="fdfe6-110">pceltFetched</span></span>  
 <span data-ttu-id="fdfe6-111">enuncia Puntero al número de objetos [COR_SEGMENT](cor-segment-structure.md) realmente devueltos en `segments` .</span><span class="sxs-lookup"><span data-stu-id="fdfe6-111">[out] A pointer to the number of [COR_SEGMENT](cor-segment-structure.md) objects actually returned in `segments`.</span></span> <span data-ttu-id="fdfe6-112">Este valor puede ser `null` si `celt` es 1.</span><span class="sxs-lookup"><span data-stu-id="fdfe6-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fdfe6-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fdfe6-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdfe6-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fdfe6-114">Requirements</span></span>  

 <span data-ttu-id="fdfe6-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fdfe6-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdfe6-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fdfe6-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fdfe6-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fdfe6-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fdfe6-118">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdfe6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdfe6-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fdfe6-119">See also</span></span>

- [<span data-ttu-id="fdfe6-120">ICorDebugHeapSegmentEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fdfe6-120">ICorDebugHeapSegmentEnum Interface</span></span>](icordebugheapsegmentenum-interface.md)
- [<span data-ttu-id="fdfe6-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="fdfe6-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
