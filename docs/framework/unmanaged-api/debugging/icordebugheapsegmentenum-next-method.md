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
ms.openlocfilehash: 8a267ec7123edb73ad51f0781a78344119ec6f21
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178891"
---
# <a name="icordebugheapsegmentenumnext-method"></a><span data-ttu-id="2b564-102">ICorDebugHeapSegmentEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="2b564-102">ICorDebugHeapSegmentEnum::Next Method</span></span>
<span data-ttu-id="2b564-103">Obtiene el número especificado de [instancias de COR_HEAPOBJECT](cor-heapobject-structure.md) que contienen información sobre las regiones de memoria del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="2b564-103">Gets the specified number of [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that contain information about memory regions of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b564-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2b564-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_SEGMENT segments[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b564-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2b564-105">Parameters</span></span>  
 <span data-ttu-id="2b564-106">celt</span><span class="sxs-lookup"><span data-stu-id="2b564-106">celt</span></span>  
 <span data-ttu-id="2b564-107">[en] El número de segmentos que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="2b564-107">[in] The number of segments to be retrieved.</span></span>  
  
 <span data-ttu-id="2b564-108">segmentos</span><span class="sxs-lookup"><span data-stu-id="2b564-108">segments</span></span>  
 <span data-ttu-id="2b564-109">[fuera] Matriz de punteros, cada uno de los cuales apunta a un objeto [COR_HEAPOBJECT](cor-heapobject-structure.md) que proporciona información sobre una región de memoria en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="2b564-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](cor-heapobject-structure.md) object that provides information about a region of memory in the managed heap.</span></span>  
  
 <span data-ttu-id="2b564-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="2b564-110">pceltFetched</span></span>  
 <span data-ttu-id="2b564-111">[fuera] Puntero al número de [objetos](cor-heapobject-structure.md) `segments`COR_HEAPOBJECT realmente devueltos en .</span><span class="sxs-lookup"><span data-stu-id="2b564-111">[out] A pointer to the number of [COR_HEAPOBJECT](cor-heapobject-structure.md) objects actually returned in `segments`.</span></span> <span data-ttu-id="2b564-112">Este valor puede ser `null` si `celt` es 1.</span><span class="sxs-lookup"><span data-stu-id="2b564-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b564-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2b564-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b564-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2b564-114">Requirements</span></span>  
 <span data-ttu-id="2b564-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b564-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b564-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b564-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b564-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b564-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b564-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b564-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b564-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2b564-119">See also</span></span>

- [<span data-ttu-id="2b564-120">ICorDebugHeapSegmentEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2b564-120">ICorDebugHeapSegmentEnum Interface</span></span>](icordebugheapsegmentenum-interface.md)
- [<span data-ttu-id="2b564-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="2b564-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
