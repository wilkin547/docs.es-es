---
title: ICorDebugValueEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugValueEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueEnum::Next
helpviewer_keywords:
- ICorDebugValueEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugValueEnum interface [.NET Framework debugging]
ms.assetid: f5ef94dd-dfee-49d3-a398-b110f8906dd8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b24507c7cb0860fc04fa519c6bd95113483f629d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59174218"
---
# <a name="icordebugvalueenumnext-method"></a><span data-ttu-id="24962-102">ICorDebugValueEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="24962-102">ICorDebugValueEnum::Next Method</span></span>
<span data-ttu-id="24962-103">Obtiene el número especificado de instancias de "ICorDebugValue" de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="24962-103">Gets the specified number of "ICorDebugValue" instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24962-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="24962-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugValue *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24962-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="24962-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="24962-106">[in] El número de `ICorDebugValue` instancias va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="24962-106">[in] The number of `ICorDebugValue` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="24962-107">[out] Una matriz de punteros, cada uno de los cuales señala a una `ICorDebugValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="24962-107">[out] An array of pointers, each of which points to an `ICorDebugValue` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="24962-108">[out] Puntero al número de `ICorDebugValue` instancias devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="24962-108">[out] Pointer to the number of `ICorDebugValue` instances actually returned.</span></span> <span data-ttu-id="24962-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="24962-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24962-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="24962-110">Requirements</span></span>  
 <span data-ttu-id="24962-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24962-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24962-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="24962-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="24962-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24962-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="24962-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="24962-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="24962-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="24962-115">See also</span></span>
