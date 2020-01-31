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
ms.openlocfilehash: 3a8e967a3ecc452ebda08872d8bcd9e9d08c766f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777692"
---
# <a name="icordebuggcreferenceenumnext-method"></a><span data-ttu-id="84e09-102">ICorDebugGCReferenceEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="84e09-102">ICorDebugGCReferenceEnum::Next Method</span></span>
<span data-ttu-id="84e09-103">Obtiene el número especificado de instancias de [COR_GC_REFERENCE](cor-gc-reference-structure.md) que contienen información sobre los objetos que se van a recolectar como elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="84e09-103">Gets the specified number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84e09-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="84e09-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_GC_REFERENCE roots[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84e09-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="84e09-105">Parameters</span></span>  
 <span data-ttu-id="84e09-106">celt</span><span class="sxs-lookup"><span data-stu-id="84e09-106">celt</span></span>  
 <span data-ttu-id="84e09-107">de Número de raíces que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="84e09-107">[in] The number of roots to be retrieved.</span></span>  
  
 <span data-ttu-id="84e09-108">raíces</span><span class="sxs-lookup"><span data-stu-id="84e09-108">roots</span></span>  
 <span data-ttu-id="84e09-109">enuncia Matriz de punteros, cada uno de los cuales apunta a un [COR_GC_REFERENCE](cor-gc-reference-structure.md) objeto que representa la raíz de un objeto que se va a recolectar como elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="84e09-109">[out] An array of pointers, each of which points to a [COR_GC_REFERENCE](cor-gc-reference-structure.md) object that represents the root of an object to be garbage-collected.</span></span>  
  
 <span data-ttu-id="84e09-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="84e09-110">pceltFetched</span></span>  
 <span data-ttu-id="84e09-111">enuncia Puntero al número de objetos [COR_GC_REFERENCE](cor-gc-reference-structure.md) realmente devueltos en `roots`.</span><span class="sxs-lookup"><span data-stu-id="84e09-111">[out] A pointer to the number of [COR_GC_REFERENCE](cor-gc-reference-structure.md) objects actually returned in `roots`.</span></span> <span data-ttu-id="84e09-112">Este valor puede ser `null` si `celt` es 1.</span><span class="sxs-lookup"><span data-stu-id="84e09-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84e09-113">Notas</span><span class="sxs-lookup"><span data-stu-id="84e09-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84e09-114">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="84e09-114">Requirements</span></span>  
 <span data-ttu-id="84e09-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84e09-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84e09-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84e09-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84e09-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84e09-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84e09-118">**.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84e09-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84e09-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="84e09-119">See also</span></span>

- [<span data-ttu-id="84e09-120">ICorDebugGCReferenceEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="84e09-120">ICorDebugGCReferenceEnum Interface</span></span>](icordebuggcreferenceenum-interface.md)
- [<span data-ttu-id="84e09-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="84e09-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
