---
title: ICorDebugChain::IsManaged (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugChain.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::IsManaged
helpviewer_keywords:
- ICorDebugChain::IsManaged method [.NET Framework debugging]
- IsManaged method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 17b389a0-1a4d-4e8a-8613-9bc1769930f9
topic_type:
- apiref
ms.openlocfilehash: cfe884c3d26e7a52618eb9945f0af9a167132f05
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724382"
---
# <a name="icordebugchainismanaged-method"></a><span data-ttu-id="5a90f-102">ICorDebugChain::IsManaged (Método)</span><span class="sxs-lookup"><span data-stu-id="5a90f-102">ICorDebugChain::IsManaged Method</span></span>

<span data-ttu-id="5a90f-103">Obtiene un valor que indica si esta cadena ejecuta código administrado.</span><span class="sxs-lookup"><span data-stu-id="5a90f-103">Gets a value that indicates whether this chain is running managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a90f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a90f-104">Syntax</span></span>  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL               *pManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a90f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5a90f-105">Parameters</span></span>  

 `pManaged`  
 <span data-ttu-id="5a90f-106">[out] `true` Si esta cadena ejecuta código administrado; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="5a90f-106">[out] `true` if this chain is running managed code; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a90f-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a90f-107">Requirements</span></span>  

 <span data-ttu-id="5a90f-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a90f-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a90f-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5a90f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5a90f-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a90f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a90f-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a90f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
