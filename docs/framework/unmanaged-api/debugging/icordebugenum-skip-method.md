---
title: "ICorDebugEnum::Skip (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugEnum.Skip
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::Skip
helpviewer_keywords:
- ICorDebugEnum::Skip method [.NET Framework debugging]
- Skip method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: e925d88a-67a5-4f76-88b8-09cedeed0232
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0c2e0065b8dd16e32ed624dd073276e7885c1a52
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugenumskip-method"></a><span data-ttu-id="a9ef6-102">ICorDebugEnum::Skip (Método)</span><span class="sxs-lookup"><span data-stu-id="a9ef6-102">ICorDebugEnum::Skip Method</span></span>
<span data-ttu-id="a9ef6-103">Mueve el cursor hacia delante en la enumeración el número especificado de elementos.</span><span class="sxs-lookup"><span data-stu-id="a9ef6-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9ef6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9ef6-104">Syntax</span></span>  
  
```  
HRESULT Skip (  
    [in] ULONG celt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a9ef6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a9ef6-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="a9ef6-106">[in] El número de elementos por el que se va a mover el cursor hacia delante.</span><span class="sxs-lookup"><span data-stu-id="a9ef6-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9ef6-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9ef6-107">Requirements</span></span>  
 <span data-ttu-id="a9ef6-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9ef6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9ef6-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a9ef6-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9ef6-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9ef6-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9ef6-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9ef6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9ef6-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9ef6-112">See Also</span></span>  
 [<span data-ttu-id="a9ef6-113">ICorDebugEnum (interfaz1)</span><span class="sxs-lookup"><span data-stu-id="a9ef6-113">ICorDebugEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-interface1.md)
