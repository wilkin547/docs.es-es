---
title: ICorDebugThreadEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThreadEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThreadEnum::Next
helpviewer_keywords:
- ICorDebugThreadEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugThreadEnum interface [.NET Framework debugging]
ms.assetid: f967c93d-9a7f-4aaf-99a1-a1317899ff3f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e9e33e65b1cdeabe203c67ee4d4f259e2f7ac99
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770068"
---
# <a name="icordebugthreadenumnext-method"></a><span data-ttu-id="ce52c-102">ICorDebugThreadEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="ce52c-102">ICorDebugThreadEnum::Next Method</span></span>
<span data-ttu-id="ce52c-103">Obtiene el número de instancias ICorDebugThread especificadas de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="ce52c-103">Gets the number of specified ICorDebugThread instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce52c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ce52c-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugThread *threads[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce52c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ce52c-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="ce52c-106">[in] El número de `ICorDebugThread` instancias va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="ce52c-106">[in] The number of `ICorDebugThread` instances to be retrieved.</span></span>  
  
 `threads`  
 <span data-ttu-id="ce52c-107">[out] Una matriz de punteros, cada uno de los cuales señala a una `ICorDebugThread` objeto que representa un subproceso.</span><span class="sxs-lookup"><span data-stu-id="ce52c-107">[out] An array of pointers, each of which points to an `ICorDebugThread` object that represents a thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="ce52c-108">[out] Puntero al número de `ICorDebugThread` instancias devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="ce52c-108">[out] Pointer to the number of `ICorDebugThread` instances actually returned.</span></span> <span data-ttu-id="ce52c-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="ce52c-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce52c-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ce52c-110">Requirements</span></span>  
 <span data-ttu-id="ce52c-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce52c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce52c-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ce52c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ce52c-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce52c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce52c-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce52c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
