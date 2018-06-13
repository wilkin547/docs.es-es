---
title: ICorDebugHeapEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugHeapEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapEnum::Next
helpviewer_keywords:
- ICorDebugHeapEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 2221fd06-9e27-4113-972e-2530db8c3594
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 93c430bb7e4d14c5f6f4e0563adfd387a1900ee6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415742"
---
# <a name="icordebugheapenumnext-method"></a><span data-ttu-id="b4dcc-102">ICorDebugHeapEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="b4dcc-102">ICorDebugHeapEnum::Next Method</span></span>
<span data-ttu-id="b4dcc-103">Obtiene el número especificado de [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instancias que contienen información acerca de los objetos en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="b4dcc-103">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4dcc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b4dcc-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_HEAPOBJECT  objects[],   
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b4dcc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b4dcc-105">Parameters</span></span>  
 <span data-ttu-id="b4dcc-106">celt</span><span class="sxs-lookup"><span data-stu-id="b4dcc-106">celt</span></span>  
 <span data-ttu-id="b4dcc-107">[in] Número de objetos que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="b4dcc-107">[in] The number of objects to be retrieved.</span></span>  
  
 <span data-ttu-id="b4dcc-108">objetos</span><span class="sxs-lookup"><span data-stu-id="b4dcc-108">objects</span></span>  
 <span data-ttu-id="b4dcc-109">[out] Una matriz de punteros, cada uno de los cuales señala a un [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objeto que proporciona información sobre un objeto en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="b4dcc-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) object that provides information about an object on the managed heap.</span></span>  
  
 <span data-ttu-id="b4dcc-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="b4dcc-110">pceltFetched</span></span>  
 <span data-ttu-id="b4dcc-111">[out] Un puntero al número de [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objetos realmente devueltos en `objects`.</span><span class="sxs-lookup"><span data-stu-id="b4dcc-111">[out] A pointer to the number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects actually returned in `objects`.</span></span> <span data-ttu-id="b4dcc-112">Este valor puede ser `null` si `celt` es 1.</span><span class="sxs-lookup"><span data-stu-id="b4dcc-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4dcc-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b4dcc-113">Remarks</span></span>  
 <span data-ttu-id="b4dcc-114">El campo `COR_HEAPOBJECT.type` es el identificador de una interfaz COM contada como referencia anidada.</span><span class="sxs-lookup"><span data-stu-id="b4dcc-114">The `COR_HEAPOBJECT.type` field is the identifier of a nested reference-counted COM interface.</span></span> <span data-ttu-id="b4dcc-115">Esta referencia debe liberarla el llamador de `ICorDebugHeapEnum::Next`.</span><span class="sxs-lookup"><span data-stu-id="b4dcc-115">This reference must be released by the caller of `ICorDebugHeapEnum::Next`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4dcc-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b4dcc-116">Requirements</span></span>  
 <span data-ttu-id="b4dcc-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4dcc-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4dcc-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b4dcc-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b4dcc-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4dcc-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4dcc-120">**Versiones de .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4dcc-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4dcc-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4dcc-121">See Also</span></span>  
 [<span data-ttu-id="b4dcc-122">ICorDebugHeapEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b4dcc-122">ICorDebugHeapEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
 [<span data-ttu-id="b4dcc-123">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="b4dcc-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
