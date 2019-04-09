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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d260fa762033e86351577d46c770543300876869
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59132553"
---
# <a name="icordebugheapsegmentenumnext-method"></a><span data-ttu-id="2619c-102">ICorDebugHeapSegmentEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="2619c-102">ICorDebugHeapSegmentEnum::Next Method</span></span>
<span data-ttu-id="2619c-103">Obtiene el número especificado de [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instancias que contienen información acerca de las regiones de memoria del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="2619c-103">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about memory regions of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2619c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2619c-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_SEGMENT segments[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2619c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2619c-105">Parameters</span></span>  
 <span data-ttu-id="2619c-106">celt</span><span class="sxs-lookup"><span data-stu-id="2619c-106">celt</span></span>  
 <span data-ttu-id="2619c-107">[in] El número de segmentos que va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="2619c-107">[in] The number of segments to be retrieved.</span></span>  
  
 <span data-ttu-id="2619c-108">segmentos</span><span class="sxs-lookup"><span data-stu-id="2619c-108">segments</span></span>  
 <span data-ttu-id="2619c-109">[out] Una matriz de punteros, cada uno de los cuales señala a un [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objeto que proporciona información acerca de una región de memoria del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="2619c-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) object that provides information about a region of memory in the managed heap.</span></span>  
  
 <span data-ttu-id="2619c-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="2619c-110">pceltFetched</span></span>  
 <span data-ttu-id="2619c-111">[out] Un puntero al número de [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) los objetos devueltos realmente en `segments`.</span><span class="sxs-lookup"><span data-stu-id="2619c-111">[out] A pointer to the number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects actually returned in `segments`.</span></span> <span data-ttu-id="2619c-112">Este valor puede ser `null` si `celt` es 1.</span><span class="sxs-lookup"><span data-stu-id="2619c-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2619c-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2619c-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2619c-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2619c-114">Requirements</span></span>  
 <span data-ttu-id="2619c-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2619c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2619c-116">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2619c-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2619c-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2619c-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="2619c-118">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="2619c-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2619c-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="2619c-119">See also</span></span>

- [<span data-ttu-id="2619c-120">ICorDebugHeapSegmentEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2619c-120">ICorDebugHeapSegmentEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)
- [<span data-ttu-id="2619c-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="2619c-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
