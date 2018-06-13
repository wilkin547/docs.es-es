---
title: ICorDebugTypeEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugTypeEnum::Next
helpviewer_keywords:
- ICorDebugTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugTypeEnum interface [.NET Framework debugging]
ms.assetid: d0fdeba3-c195-4ece-8caf-79b1f40025d2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9812fa4248533ccb898c98082e42e288c091f776
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420591"
---
# <a name="icordebugtypeenumnext-method"></a><span data-ttu-id="73426-102">ICorDebugTypeEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="73426-102">ICorDebugTypeEnum::Next Method</span></span>
<span data-ttu-id="73426-103">Obtiene el número de instancias de "ICorDebugType" especificada por `celt` de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="73426-103">Gets the number of "ICorDebugType" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73426-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="73426-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugType *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="73426-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="73426-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="73426-106">[in] El número de `ICorDebugType` instancias va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="73426-106">[in] The number of `ICorDebugType` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="73426-107">[out] Una matriz de punteros, cada uno de los cuales señala a un `ICorDebugType` objeto.</span><span class="sxs-lookup"><span data-stu-id="73426-107">[out] An array of pointers, each of which points to an `ICorDebugType` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="73426-108">[out] Puntero al número de `ICorDebugType` instancias realmente devueltos.</span><span class="sxs-lookup"><span data-stu-id="73426-108">[out] Pointer to the number of `ICorDebugType` instances actually returned.</span></span> <span data-ttu-id="73426-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="73426-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73426-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="73426-110">Requirements</span></span>  
 <span data-ttu-id="73426-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73426-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73426-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="73426-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="73426-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="73426-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="73426-114">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73426-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73426-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="73426-115">See Also</span></span>  
 
