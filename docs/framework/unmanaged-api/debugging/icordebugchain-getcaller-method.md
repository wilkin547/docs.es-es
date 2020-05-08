---
title: ICorDebugChain::GetCaller (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCaller
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCaller
helpviewer_keywords:
- ICorDebugChain::GetCaller method [.NET Framework debugging]
- GetCaller method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: d0b8ab4b-d7d2-4fa0-945f-3d2b87e7e991
topic_type:
- apiref
ms.openlocfilehash: a6d26924773e6ad505975402ec3ace150d02cc3a
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894614"
---
# <a name="icordebugchaingetcaller-method"></a><span data-ttu-id="baaff-102">ICorDebugChain::GetCaller (Método)</span><span class="sxs-lookup"><span data-stu-id="baaff-102">ICorDebugChain::GetCaller Method</span></span>
<span data-ttu-id="baaff-103">Obtiene la cadena que llamó a esta cadena.</span><span class="sxs-lookup"><span data-stu-id="baaff-103">Gets the chain that called this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="baaff-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="baaff-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="baaff-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="baaff-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="baaff-106">enuncia Puntero a la dirección de un objeto ICorDebugChain que representa la cadena de llamada.</span><span class="sxs-lookup"><span data-stu-id="baaff-106">[out] A pointer to the address of an ICorDebugChain object that represents the calling chain.</span></span>  
  
 <span data-ttu-id="baaff-107">Si se llamó a esta cadena espontáneamente (como sería el caso si esta cadena o el depurador inicializara la pila de llamadas `ppChain` ), será null.</span><span class="sxs-lookup"><span data-stu-id="baaff-107">If this chain was spontaneously called (as would be the case if this chain or the debugger initialized the call stack), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="baaff-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="baaff-108">Remarks</span></span>  
 <span data-ttu-id="baaff-109">La cadena de llamada puede estar en un subproceso diferente, si se serializó la llamada entre subprocesos.</span><span class="sxs-lookup"><span data-stu-id="baaff-109">The calling chain may be on a different thread, if the call was marshaled across threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="baaff-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="baaff-110">Requirements</span></span>  
 <span data-ttu-id="baaff-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="baaff-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="baaff-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="baaff-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="baaff-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="baaff-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="baaff-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="baaff-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
