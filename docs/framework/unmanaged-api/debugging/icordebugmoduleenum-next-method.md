---
title: ICorDebugModuleEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum::Next
helpviewer_keywords:
- ICorDebugModuleEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 9ff3fcd6-38fe-41f8-bfd3-f0ab6c7d77ca
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aa341c726ba84dc1d12b6c5628253a100d65a719
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59167107"
---
# <a name="icordebugmoduleenumnext-method"></a><span data-ttu-id="98093-102">ICorDebugModuleEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="98093-102">ICorDebugModuleEnum::Next Method</span></span>
<span data-ttu-id="98093-103">Obtiene el número de instancias de "ICorDebugModule" especificado por `celt` de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="98093-103">Gets the number of "ICorDebugModule" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98093-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="98093-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugModule *modules[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98093-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="98093-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="98093-106">[in] El número de `ICorDebugModule` instancias va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="98093-106">[in] The number of `ICorDebugModule` instances to be retrieved.</span></span>  
  
 `modules`  
 <span data-ttu-id="98093-107">[out] Una matriz de punteros, cada uno de los cuales señala a una `ICorDebugModule` objeto.</span><span class="sxs-lookup"><span data-stu-id="98093-107">[out] An array of pointers, each of which points to an `ICorDebugModule` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="98093-108">[out] Puntero al número de `ICorDebugModule` instancias devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="98093-108">[out] Pointer to the number of `ICorDebugModule` instances actually returned.</span></span> <span data-ttu-id="98093-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="98093-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98093-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="98093-110">Requirements</span></span>  
 <span data-ttu-id="98093-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98093-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98093-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="98093-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="98093-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98093-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98093-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98093-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98093-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="98093-115">See also</span></span>
