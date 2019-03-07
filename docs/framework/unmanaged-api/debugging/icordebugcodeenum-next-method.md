---
title: ICorDebugCodeEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugCodeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCodeEnum::Next
helpviewer_keywords:
- ICorDebugCodeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 644ece86-384d-4c63-9fba-52c789616ff7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a3aeae294d92a6dc9effc7f3baa51a35e4f2b544
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476638"
---
# <a name="icordebugcodeenumnext-method"></a><span data-ttu-id="ee74f-102">ICorDebugCodeEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="ee74f-102">ICorDebugCodeEnum::Next Method</span></span>
<span data-ttu-id="ee74f-103">Obtiene el número especificado de instancias de "ICorDebugCode" de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="ee74f-103">Gets the specified number of "ICorDebugCode" instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee74f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ee74f-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugCode *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee74f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ee74f-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="ee74f-106">[in] El número de `ICorDebugCode` instancias va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="ee74f-106">[in] The number of `ICorDebugCode` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="ee74f-107">[out] Una matriz de punteros, cada uno de los cuales señala a una `ICorDebugCode` objeto.</span><span class="sxs-lookup"><span data-stu-id="ee74f-107">[out] An array of pointers, each of which points to an `ICorDebugCode` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="ee74f-108">[out] Un puntero al número de `ICorDebugCode` instancias devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="ee74f-108">[out] A pointer to the number of `ICorDebugCode` instances actually returned.</span></span> <span data-ttu-id="ee74f-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="ee74f-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee74f-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ee74f-110">Requirements</span></span>  
 <span data-ttu-id="ee74f-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee74f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee74f-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ee74f-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee74f-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee74f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee74f-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee74f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee74f-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee74f-115">See also</span></span>


