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
ms.openlocfilehash: 5efc83152763c5ef8b65a1fad33460c5354c0dc5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772423"
---
# <a name="icordebugtypeenumnext-method"></a><span data-ttu-id="37cf4-102">ICorDebugTypeEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="37cf4-102">ICorDebugTypeEnum::Next Method</span></span>
<span data-ttu-id="37cf4-103">Obtiene el número de instancias de "ICorDebugType" especificado por `celt` de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="37cf4-103">Gets the number of "ICorDebugType" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37cf4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="37cf4-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugType *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37cf4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="37cf4-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="37cf4-106">[in] El número de `ICorDebugType` instancias va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="37cf4-106">[in] The number of `ICorDebugType` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="37cf4-107">[out] Una matriz de punteros, cada uno de los cuales señala a una `ICorDebugType` objeto.</span><span class="sxs-lookup"><span data-stu-id="37cf4-107">[out] An array of pointers, each of which points to an `ICorDebugType` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="37cf4-108">[out] Puntero al número de `ICorDebugType` instancias devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="37cf4-108">[out] Pointer to the number of `ICorDebugType` instances actually returned.</span></span> <span data-ttu-id="37cf4-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="37cf4-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37cf4-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="37cf4-110">Requirements</span></span>  
 <span data-ttu-id="37cf4-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37cf4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37cf4-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="37cf4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="37cf4-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37cf4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37cf4-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37cf4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37cf4-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="37cf4-115">See also</span></span>
