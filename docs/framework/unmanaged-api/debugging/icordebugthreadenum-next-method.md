---
title: "ICorDebugThreadEnum::Next (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThreadEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThreadEnum::Next
helpviewer_keywords:
- ICorDebugThreadEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugThreadEnum interface [.NET Framework debugging]
ms.assetid: f967c93d-9a7f-4aaf-99a1-a1317899ff3f
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ac9ff468f85248631ffd7f3a39a8827b1aef45b0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadenumnext-method"></a><span data-ttu-id="6633d-102">ICorDebugThreadEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="6633d-102">ICorDebugThreadEnum::Next Method</span></span>
<span data-ttu-id="6633d-103">Obtiene el número de instancias de ICorDebugThread especificadas de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="6633d-103">Gets the number of specified ICorDebugThread instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6633d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6633d-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugThread *threads[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6633d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6633d-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="6633d-106">[in] El número de `ICorDebugThread` instancias va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="6633d-106">[in] The number of `ICorDebugThread` instances to be retrieved.</span></span>  
  
 `threads`  
 <span data-ttu-id="6633d-107">[out] Una matriz de punteros, cada uno de los cuales señala a un `ICorDebugThread` objeto que representa un subproceso.</span><span class="sxs-lookup"><span data-stu-id="6633d-107">[out] An array of pointers, each of which points to an `ICorDebugThread` object that represents a thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="6633d-108">[out] Puntero al número de `ICorDebugThread` instancias realmente devueltos.</span><span class="sxs-lookup"><span data-stu-id="6633d-108">[out] Pointer to the number of `ICorDebugThread` instances actually returned.</span></span> <span data-ttu-id="6633d-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="6633d-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6633d-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6633d-110">Requirements</span></span>  
 <span data-ttu-id="6633d-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6633d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6633d-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6633d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6633d-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6633d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6633d-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6633d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
