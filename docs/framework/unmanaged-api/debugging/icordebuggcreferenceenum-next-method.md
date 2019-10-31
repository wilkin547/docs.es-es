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
ms.openlocfilehash: 43408486fec9cd50222eed08ec2d3397bc11bc18
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134617"
---
# <a name="icordebuggcreferenceenumnext-method"></a><span data-ttu-id="e6bde-102">ICorDebugGCReferenceEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="e6bde-102">ICorDebugGCReferenceEnum::Next Method</span></span>
<span data-ttu-id="e6bde-103">Obtiene el número especificado de instancias de [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) que contienen información sobre los objetos que se van a recolectar como elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="e6bde-103">Gets the specified number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6bde-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e6bde-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_GC_REFERENCE roots[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6bde-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e6bde-105">Parameters</span></span>  
 <span data-ttu-id="e6bde-106">celt</span><span class="sxs-lookup"><span data-stu-id="e6bde-106">celt</span></span>  
 <span data-ttu-id="e6bde-107">de Número de raíces que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="e6bde-107">[in] The number of roots to be retrieved.</span></span>  
  
 <span data-ttu-id="e6bde-108">raíces</span><span class="sxs-lookup"><span data-stu-id="e6bde-108">roots</span></span>  
 <span data-ttu-id="e6bde-109">enuncia Matriz de punteros, cada uno de los cuales apunta a un objeto [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) que representa la raíz de un objeto que se va a recolectar como elemento no utilizado.</span><span class="sxs-lookup"><span data-stu-id="e6bde-109">[out] An array of pointers, each of which points to a [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) object that represents the root of an object to be garbage-collected.</span></span>  
  
 <span data-ttu-id="e6bde-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="e6bde-110">pceltFetched</span></span>  
 <span data-ttu-id="e6bde-111">enuncia Puntero al número de objetos [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) realmente devueltos en `roots`.</span><span class="sxs-lookup"><span data-stu-id="e6bde-111">[out] A pointer to the number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects actually returned in `roots`.</span></span> <span data-ttu-id="e6bde-112">Este valor puede ser `null` si `celt` es 1.</span><span class="sxs-lookup"><span data-stu-id="e6bde-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6bde-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e6bde-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6bde-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e6bde-114">Requirements</span></span>  
 <span data-ttu-id="e6bde-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6bde-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6bde-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e6bde-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e6bde-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6bde-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6bde-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6bde-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6bde-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6bde-119">See also</span></span>

- [<span data-ttu-id="e6bde-120">ICorDebugGCReferenceEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e6bde-120">ICorDebugGCReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)
- [<span data-ttu-id="e6bde-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="e6bde-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
