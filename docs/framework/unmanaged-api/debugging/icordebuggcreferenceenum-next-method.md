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
ms.openlocfilehash: 1cf6f9c5fe8777f3333e449a804a3c3a0a64ff19
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213093"
---
# <a name="icordebuggcreferenceenumnext-method"></a><span data-ttu-id="a05aa-102">ICorDebugGCReferenceEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="a05aa-102">ICorDebugGCReferenceEnum::Next Method</span></span>
<span data-ttu-id="a05aa-103">Obtiene el número especificado de instancias de [COR_GC_REFERENCE](cor-gc-reference-structure.md) que contienen información sobre los objetos que se van a recolectar como elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="a05aa-103">Gets the specified number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a05aa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a05aa-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_GC_REFERENCE roots[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a05aa-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a05aa-105">Parameters</span></span>  
 <span data-ttu-id="a05aa-106">celt</span><span class="sxs-lookup"><span data-stu-id="a05aa-106">celt</span></span>  
 <span data-ttu-id="a05aa-107">de Número de raíces que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="a05aa-107">[in] The number of roots to be retrieved.</span></span>  
  
 <span data-ttu-id="a05aa-108">raíces</span><span class="sxs-lookup"><span data-stu-id="a05aa-108">roots</span></span>  
 <span data-ttu-id="a05aa-109">enuncia Matriz de punteros, cada uno de los cuales apunta a un [COR_GC_REFERENCE](cor-gc-reference-structure.md) objeto que representa la raíz de un objeto que se va a recolectar como elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="a05aa-109">[out] An array of pointers, each of which points to a [COR_GC_REFERENCE](cor-gc-reference-structure.md) object that represents the root of an object to be garbage-collected.</span></span>  
  
 <span data-ttu-id="a05aa-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="a05aa-110">pceltFetched</span></span>  
 <span data-ttu-id="a05aa-111">enuncia Puntero al número de objetos [COR_GC_REFERENCE](cor-gc-reference-structure.md) realmente devueltos en `roots` .</span><span class="sxs-lookup"><span data-stu-id="a05aa-111">[out] A pointer to the number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) objects actually returned in `roots`.</span></span> <span data-ttu-id="a05aa-112">Este valor puede ser `null` si `celt` es 1.</span><span class="sxs-lookup"><span data-stu-id="a05aa-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a05aa-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a05aa-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a05aa-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a05aa-114">Requirements</span></span>  
 <span data-ttu-id="a05aa-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a05aa-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a05aa-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a05aa-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a05aa-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a05aa-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a05aa-118">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a05aa-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a05aa-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a05aa-119">See also</span></span>

- [<span data-ttu-id="a05aa-120">ICorDebugGCReferenceEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a05aa-120">ICorDebugGCReferenceEnum Interface</span></span>](icordebuggcreferenceenum-interface.md)
- [<span data-ttu-id="a05aa-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="a05aa-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
