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
ms.openlocfilehash: f5af8e559b4fbfeb60530372185ca10104ade987
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178852"
---
# <a name="icordebugheapenumnext-method"></a><span data-ttu-id="b4a7c-102">ICorDebugHeapEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="b4a7c-102">ICorDebugHeapEnum::Next Method</span></span>
<span data-ttu-id="b4a7c-103">Obtiene el número especificado de [instancias de COR_HEAPOBJECT](cor-heapobject-structure.md) que contienen información sobre los objetos del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="b4a7c-103">Gets the specified number of [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4a7c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b4a7c-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_HEAPOBJECT  objects[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4a7c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b4a7c-105">Parameters</span></span>  
 <span data-ttu-id="b4a7c-106">celt</span><span class="sxs-lookup"><span data-stu-id="b4a7c-106">celt</span></span>  
 <span data-ttu-id="b4a7c-107">[in] Número de objetos que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="b4a7c-107">[in] The number of objects to be retrieved.</span></span>  
  
 <span data-ttu-id="b4a7c-108">objetos</span><span class="sxs-lookup"><span data-stu-id="b4a7c-108">objects</span></span>  
 <span data-ttu-id="b4a7c-109">[fuera] Matriz de punteros, cada uno de los cuales apunta a un [objeto COR_HEAPOBJECT](cor-heapobject-structure.md) que proporciona información sobre un objeto en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="b4a7c-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](cor-heapobject-structure.md) object that provides information about an object on the managed heap.</span></span>  
  
 <span data-ttu-id="b4a7c-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="b4a7c-110">pceltFetched</span></span>  
 <span data-ttu-id="b4a7c-111">[fuera] Puntero al número de [objetos](cor-heapobject-structure.md) `objects`COR_HEAPOBJECT realmente devueltos en .</span><span class="sxs-lookup"><span data-stu-id="b4a7c-111">[out] A pointer to the number of [COR_HEAPOBJECT](cor-heapobject-structure.md) objects actually returned in `objects`.</span></span> <span data-ttu-id="b4a7c-112">Este valor puede ser `null` si `celt` es 1.</span><span class="sxs-lookup"><span data-stu-id="b4a7c-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4a7c-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b4a7c-113">Remarks</span></span>  
 <span data-ttu-id="b4a7c-114">El campo `COR_HEAPOBJECT.type` es el identificador de una interfaz COM contada como referencia anidada.</span><span class="sxs-lookup"><span data-stu-id="b4a7c-114">The `COR_HEAPOBJECT.type` field is the identifier of a nested reference-counted COM interface.</span></span> <span data-ttu-id="b4a7c-115">Esta referencia debe liberarla el llamador de `ICorDebugHeapEnum::Next`.</span><span class="sxs-lookup"><span data-stu-id="b4a7c-115">This reference must be released by the caller of `ICorDebugHeapEnum::Next`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4a7c-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b4a7c-116">Requirements</span></span>  
 <span data-ttu-id="b4a7c-117">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4a7c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4a7c-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b4a7c-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b4a7c-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4a7c-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4a7c-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4a7c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4a7c-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b4a7c-121">See also</span></span>

- [<span data-ttu-id="b4a7c-122">ICorDebugHeapEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b4a7c-122">ICorDebugHeapEnum Interface</span></span>](icordebugheapenum-interface.md)
- [<span data-ttu-id="b4a7c-123">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="b4a7c-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
