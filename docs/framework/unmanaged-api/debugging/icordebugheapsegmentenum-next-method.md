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
ms.openlocfilehash: 897fb56cacb51e98cf8f1778c3529617decb5ecb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138441"
---
# <a name="icordebugheapsegmentenumnext-method"></a><span data-ttu-id="0e2f2-102">ICorDebugHeapSegmentEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="0e2f2-102">ICorDebugHeapSegmentEnum::Next Method</span></span>
<span data-ttu-id="0e2f2-103">Obtiene el número especificado de instancias de [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) que contienen información sobre las regiones de memoria del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="0e2f2-103">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about memory regions of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e2f2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0e2f2-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_SEGMENT segments[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e2f2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0e2f2-105">Parameters</span></span>  
 <span data-ttu-id="0e2f2-106">celt</span><span class="sxs-lookup"><span data-stu-id="0e2f2-106">celt</span></span>  
 <span data-ttu-id="0e2f2-107">de Número de segmentos que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="0e2f2-107">[in] The number of segments to be retrieved.</span></span>  
  
 <span data-ttu-id="0e2f2-108">segmentos</span><span class="sxs-lookup"><span data-stu-id="0e2f2-108">segments</span></span>  
 <span data-ttu-id="0e2f2-109">enuncia Una matriz de punteros, cada uno de los cuales apunta a un objeto [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) que proporciona información sobre una región de memoria en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="0e2f2-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) object that provides information about a region of memory in the managed heap.</span></span>  
  
 <span data-ttu-id="0e2f2-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="0e2f2-110">pceltFetched</span></span>  
 <span data-ttu-id="0e2f2-111">enuncia Puntero al número de objetos [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) realmente devueltos en `segments`.</span><span class="sxs-lookup"><span data-stu-id="0e2f2-111">[out] A pointer to the number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects actually returned in `segments`.</span></span> <span data-ttu-id="0e2f2-112">Este valor puede ser `null` si `celt` es 1.</span><span class="sxs-lookup"><span data-stu-id="0e2f2-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e2f2-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0e2f2-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e2f2-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0e2f2-114">Requirements</span></span>  
 <span data-ttu-id="0e2f2-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e2f2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e2f2-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0e2f2-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e2f2-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e2f2-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e2f2-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e2f2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e2f2-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e2f2-119">See also</span></span>

- [<span data-ttu-id="0e2f2-120">ICorDebugHeapSegmentEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0e2f2-120">ICorDebugHeapSegmentEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)
- [<span data-ttu-id="0e2f2-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="0e2f2-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
