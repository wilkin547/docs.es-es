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
ms.openlocfilehash: 2c84112984e9cb7dec2a492ac16af00e14770806
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782495"
---
# <a name="icordebugheapenumnext-method"></a><span data-ttu-id="09e47-102">ICorDebugHeapEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="09e47-102">ICorDebugHeapEnum::Next Method</span></span>
<span data-ttu-id="09e47-103">Obtiene el número especificado de instancias de [COR_HEAPOBJECT](cor-heapobject-structure.md) que contienen información sobre los objetos del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="09e47-103">Gets the specified number of [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09e47-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="09e47-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_HEAPOBJECT  objects[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09e47-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="09e47-105">Parameters</span></span>  
 <span data-ttu-id="09e47-106">celt</span><span class="sxs-lookup"><span data-stu-id="09e47-106">celt</span></span>  
 <span data-ttu-id="09e47-107">[in] Número de objetos que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="09e47-107">[in] The number of objects to be retrieved.</span></span>  
  
 <span data-ttu-id="09e47-108">Azure</span><span class="sxs-lookup"><span data-stu-id="09e47-108">objects</span></span>  
 <span data-ttu-id="09e47-109">enuncia Matriz de punteros, cada uno de los cuales apunta a un [COR_HEAPOBJECT](cor-heapobject-structure.md) objeto que proporciona información sobre un objeto en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="09e47-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](cor-heapobject-structure.md) object that provides information about an object on the managed heap.</span></span>  
  
 <span data-ttu-id="09e47-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="09e47-110">pceltFetched</span></span>  
 <span data-ttu-id="09e47-111">enuncia Puntero al número de objetos [COR_HEAPOBJECT](cor-heapobject-structure.md) realmente devueltos en `objects`.</span><span class="sxs-lookup"><span data-stu-id="09e47-111">[out] A pointer to the number of [COR_HEAPOBJECT](cor-heapobject-structure.md) objects actually returned in `objects`.</span></span> <span data-ttu-id="09e47-112">Este valor puede ser `null` si `celt` es 1.</span><span class="sxs-lookup"><span data-stu-id="09e47-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09e47-113">Notas</span><span class="sxs-lookup"><span data-stu-id="09e47-113">Remarks</span></span>  
 <span data-ttu-id="09e47-114">El campo `COR_HEAPOBJECT.type` es el identificador de una interfaz COM contada como referencia anidada.</span><span class="sxs-lookup"><span data-stu-id="09e47-114">The `COR_HEAPOBJECT.type` field is the identifier of a nested reference-counted COM interface.</span></span> <span data-ttu-id="09e47-115">Esta referencia debe liberarla el llamador de `ICorDebugHeapEnum::Next`.</span><span class="sxs-lookup"><span data-stu-id="09e47-115">This reference must be released by the caller of `ICorDebugHeapEnum::Next`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09e47-116">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="09e47-116">Requirements</span></span>  
 <span data-ttu-id="09e47-117">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09e47-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09e47-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="09e47-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="09e47-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09e47-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09e47-120">**.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09e47-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09e47-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="09e47-121">See also</span></span>

- [<span data-ttu-id="09e47-122">ICorDebugHeapEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="09e47-122">ICorDebugHeapEnum Interface</span></span>](icordebugheapenum-interface.md)
- [<span data-ttu-id="09e47-123">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="09e47-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
