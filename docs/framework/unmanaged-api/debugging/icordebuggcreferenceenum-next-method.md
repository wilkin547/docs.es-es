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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 829d114c4aa2b2ce292ff2ae365af77784d49b52
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54673849"
---
# <a name="icordebuggcreferenceenumnext-method"></a><span data-ttu-id="9fcad-102">ICorDebugGCReferenceEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="9fcad-102">ICorDebugGCReferenceEnum::Next Method</span></span>
<span data-ttu-id="9fcad-103">Obtiene el número especificado de [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instancias que contienen información sobre los objetos que se pueden recolectar.</span><span class="sxs-lookup"><span data-stu-id="9fcad-103">Gets the specified number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fcad-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9fcad-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_GC_REFERENCE roots[],   
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9fcad-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9fcad-105">Parameters</span></span>  
 <span data-ttu-id="9fcad-106">celt</span><span class="sxs-lookup"><span data-stu-id="9fcad-106">celt</span></span>  
 <span data-ttu-id="9fcad-107">[in] El número de raíces va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="9fcad-107">[in] The number of roots to be retrieved.</span></span>  
  
 <span data-ttu-id="9fcad-108">raíces</span><span class="sxs-lookup"><span data-stu-id="9fcad-108">roots</span></span>  
 <span data-ttu-id="9fcad-109">[out] Una matriz de punteros, cada uno de los cuales señala a un [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objeto que representa la raíz de un objeto para recopilar los elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="9fcad-109">[out] An array of pointers, each of which points to a [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) object that represents the root of an object to be garbage-collected.</span></span>  
  
 <span data-ttu-id="9fcad-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="9fcad-110">pceltFetched</span></span>  
 <span data-ttu-id="9fcad-111">[out] Un puntero al número de [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) los objetos devueltos realmente en `roots`.</span><span class="sxs-lookup"><span data-stu-id="9fcad-111">[out] A pointer to the number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects actually returned in `roots`.</span></span> <span data-ttu-id="9fcad-112">Este valor puede ser `null` si `celt` es 1.</span><span class="sxs-lookup"><span data-stu-id="9fcad-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9fcad-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9fcad-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fcad-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9fcad-114">Requirements</span></span>  
 <span data-ttu-id="9fcad-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9fcad-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fcad-116">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9fcad-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9fcad-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9fcad-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9fcad-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fcad-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fcad-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="9fcad-119">See also</span></span>
- [<span data-ttu-id="9fcad-120">ICorDebugGCReferenceEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9fcad-120">ICorDebugGCReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)
- [<span data-ttu-id="9fcad-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="9fcad-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
