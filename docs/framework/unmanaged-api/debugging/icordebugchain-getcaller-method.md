---
description: 'Más información sobre: ICorDebugChain:: GetCaller ((método)'
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
ms.openlocfilehash: 5af2132b7fec9e70704db980b95221db6eb273f8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99695026"
---
# <a name="icordebugchaingetcaller-method"></a><span data-ttu-id="40b6b-103">ICorDebugChain::GetCaller (Método)</span><span class="sxs-lookup"><span data-stu-id="40b6b-103">ICorDebugChain::GetCaller Method</span></span>

<span data-ttu-id="40b6b-104">Obtiene la cadena que llamó a esta cadena.</span><span class="sxs-lookup"><span data-stu-id="40b6b-104">Gets the chain that called this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40b6b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="40b6b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40b6b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="40b6b-106">Parameters</span></span>  

 `ppChain`  
 <span data-ttu-id="40b6b-107">enuncia Puntero a la dirección de un objeto ICorDebugChain que representa la cadena de llamada.</span><span class="sxs-lookup"><span data-stu-id="40b6b-107">[out] A pointer to the address of an ICorDebugChain object that represents the calling chain.</span></span>  
  
 <span data-ttu-id="40b6b-108">Si se llamó a esta cadena espontáneamente (como sería el caso si esta cadena o el depurador inicializara la pila de llamadas), `ppChain` será null.</span><span class="sxs-lookup"><span data-stu-id="40b6b-108">If this chain was spontaneously called (as would be the case if this chain or the debugger initialized the call stack), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40b6b-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="40b6b-109">Remarks</span></span>  

 <span data-ttu-id="40b6b-110">La cadena de llamada puede estar en un subproceso diferente, si se serializó la llamada entre subprocesos.</span><span class="sxs-lookup"><span data-stu-id="40b6b-110">The calling chain may be on a different thread, if the call was marshaled across threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40b6b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="40b6b-111">Requirements</span></span>  

 <span data-ttu-id="40b6b-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40b6b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40b6b-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="40b6b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="40b6b-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40b6b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40b6b-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40b6b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
