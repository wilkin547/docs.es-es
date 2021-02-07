---
description: 'Más información sobre: Icordebugheapenum (:: Next (método)'
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
ms.openlocfilehash: 22e81b9b0c4ac2027f932187b6f860d08adf6f97
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691957"
---
# <a name="icordebugheapenumnext-method"></a><span data-ttu-id="fa629-103">ICorDebugHeapEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="fa629-103">ICorDebugHeapEnum::Next Method</span></span>

<span data-ttu-id="fa629-104">Obtiene el número especificado de instancias de [COR_HEAPOBJECT](cor-heapobject-structure.md) que contienen información sobre los objetos del montón administrado.</span><span class="sxs-lookup"><span data-stu-id="fa629-104">Gets the specified number of [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa629-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa629-105">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_HEAPOBJECT  objects[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa629-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fa629-106">Parameters</span></span>  

 <span data-ttu-id="fa629-107">celt</span><span class="sxs-lookup"><span data-stu-id="fa629-107">celt</span></span>  
 <span data-ttu-id="fa629-108">[in] Número de objetos que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="fa629-108">[in] The number of objects to be retrieved.</span></span>  
  
 <span data-ttu-id="fa629-109">objetos</span><span class="sxs-lookup"><span data-stu-id="fa629-109">objects</span></span>  
 <span data-ttu-id="fa629-110">enuncia Matriz de punteros, cada uno de los cuales apunta a un [COR_HEAPOBJECT](cor-heapobject-structure.md) objeto que proporciona información sobre un objeto en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="fa629-110">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](cor-heapobject-structure.md) object that provides information about an object on the managed heap.</span></span>  
  
 <span data-ttu-id="fa629-111">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="fa629-111">pceltFetched</span></span>  
 <span data-ttu-id="fa629-112">enuncia Puntero al número de objetos [COR_HEAPOBJECT](cor-heapobject-structure.md) realmente devueltos en `objects` .</span><span class="sxs-lookup"><span data-stu-id="fa629-112">[out] A pointer to the number of [COR_HEAPOBJECT](cor-heapobject-structure.md) objects actually returned in `objects`.</span></span> <span data-ttu-id="fa629-113">Este valor puede ser `null` si `celt` es 1.</span><span class="sxs-lookup"><span data-stu-id="fa629-113">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa629-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fa629-114">Remarks</span></span>  

 <span data-ttu-id="fa629-115">El campo `COR_HEAPOBJECT.type` es el identificador de una interfaz COM contada como referencia anidada.</span><span class="sxs-lookup"><span data-stu-id="fa629-115">The `COR_HEAPOBJECT.type` field is the identifier of a nested reference-counted COM interface.</span></span> <span data-ttu-id="fa629-116">Esta referencia debe liberarla el llamador de `ICorDebugHeapEnum::Next`.</span><span class="sxs-lookup"><span data-stu-id="fa629-116">This reference must be released by the caller of `ICorDebugHeapEnum::Next`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa629-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fa629-117">Requirements</span></span>  

 <span data-ttu-id="fa629-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa629-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa629-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fa629-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fa629-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa629-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa629-121">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa629-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa629-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa629-122">See also</span></span>

- [<span data-ttu-id="fa629-123">ICorDebugHeapEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fa629-123">ICorDebugHeapEnum Interface</span></span>](icordebugheapenum-interface.md)
- [<span data-ttu-id="fa629-124">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="fa629-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
