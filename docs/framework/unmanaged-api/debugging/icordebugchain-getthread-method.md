---
title: ICorDebugChain::GetThread (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetThread
helpviewer_keywords:
- GetThread method, ICorDebugChain interface [.NET Framework debugging]
- ICorDebugChain::GetThread method [.NET Framework debugging]
ms.assetid: b3390319-6366-418c-ba80-b552ac4dfc1e
topic_type:
- apiref
ms.openlocfilehash: ad220289b45078130a0a41e67373fd3384ae9682
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724421"
---
# <a name="icordebugchaingetthread-method"></a><span data-ttu-id="8904b-102">ICorDebugChain::GetThread (Método)</span><span class="sxs-lookup"><span data-stu-id="8904b-102">ICorDebugChain::GetThread Method</span></span>

<span data-ttu-id="8904b-103">Obtiene el subproceso físico del que forma parte esta cadena de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8904b-103">Gets the physical thread this call chain is part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8904b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8904b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread (  
    [out] ICorDebugThread    **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8904b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8904b-105">Parameters</span></span>  

 `ppThread`  
 <span data-ttu-id="8904b-106">enuncia Un puntero a un objeto ICorDebugThread que representa el subproceso físico del que forma parte esta cadena de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8904b-106">[out] A pointer to an ICorDebugThread object that represents the physical thread this call chain is part of.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8904b-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8904b-107">Requirements</span></span>  

 <span data-ttu-id="8904b-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8904b-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8904b-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8904b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8904b-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8904b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8904b-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8904b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
