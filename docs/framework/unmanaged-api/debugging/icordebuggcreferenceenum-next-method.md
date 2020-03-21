---
title: ICorDebugGCReferenceEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugGCReferenceEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum::Next
helpviewer_keywords:
- Next method, ICorDebugGCReferenceEnum interface [.NET Framework debugging]
- ICorDebugGCReferenceEnum::Next method [.NET Framework debugging]
ms.assetid: 91b1345c-a94f-4ef8-9696-3823d06c6d05
topic_type:
- apiref
ms.openlocfilehash: d87f414e9dfd05a519b60efc7ecdd5328a6dd86f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178865"
---
# <a name="icordebuggcreferenceenumnext-method"></a><span data-ttu-id="6b8dc-102">ICorDebugGCReferenceEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="6b8dc-102">ICorDebugGCReferenceEnum::Next Method</span></span>
<span data-ttu-id="6b8dc-103">Obtiene el número especificado de [instancias de COR_GC_REFERENCE](cor-gc-reference-structure.md) que contienen información sobre los objetos que se recopilarán como elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="6b8dc-103">Gets the specified number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b8dc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6b8dc-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_GC_REFERENCE roots[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b8dc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6b8dc-105">Parameters</span></span>  
 <span data-ttu-id="6b8dc-106">celt</span><span class="sxs-lookup"><span data-stu-id="6b8dc-106">celt</span></span>  
 <span data-ttu-id="6b8dc-107">[en] El número de raíces que se recuperarán.</span><span class="sxs-lookup"><span data-stu-id="6b8dc-107">[in] The number of roots to be retrieved.</span></span>  
  
 <span data-ttu-id="6b8dc-108">Raíces</span><span class="sxs-lookup"><span data-stu-id="6b8dc-108">roots</span></span>  
 <span data-ttu-id="6b8dc-109">[fuera] Matriz de punteros, cada uno de los cuales apunta a un [objeto COR_GC_REFERENCE](cor-gc-reference-structure.md) que representa la raíz de un objeto que se va a recopilar como elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="6b8dc-109">[out] An array of pointers, each of which points to a [COR_GC_REFERENCE](cor-gc-reference-structure.md) object that represents the root of an object to be garbage-collected.</span></span>  
  
 <span data-ttu-id="6b8dc-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="6b8dc-110">pceltFetched</span></span>  
 <span data-ttu-id="6b8dc-111">[fuera] Puntero al número de [objetos](cor-gc-reference-structure.md) `roots`COR_GC_REFERENCE realmente devueltos en .</span><span class="sxs-lookup"><span data-stu-id="6b8dc-111">[out] A pointer to the number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) objects actually returned in `roots`.</span></span> <span data-ttu-id="6b8dc-112">Este valor puede ser `null` si `celt` es 1.</span><span class="sxs-lookup"><span data-stu-id="6b8dc-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b8dc-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6b8dc-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b8dc-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6b8dc-114">Requirements</span></span>  
 <span data-ttu-id="6b8dc-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b8dc-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b8dc-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6b8dc-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b8dc-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b8dc-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b8dc-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b8dc-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b8dc-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6b8dc-119">See also</span></span>

- [<span data-ttu-id="6b8dc-120">ICorDebugGCReferenceEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6b8dc-120">ICorDebugGCReferenceEnum Interface</span></span>](icordebuggcreferenceenum-interface.md)
- [<span data-ttu-id="6b8dc-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="6b8dc-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
