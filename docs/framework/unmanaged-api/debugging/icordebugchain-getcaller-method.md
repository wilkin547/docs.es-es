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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd65de77209f5a981c0a4c291f8573a61cf6335b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645284"
---
# <a name="icordebugchaingetcaller-method"></a><span data-ttu-id="5e199-102">ICorDebugChain::GetCaller (Método)</span><span class="sxs-lookup"><span data-stu-id="5e199-102">ICorDebugChain::GetCaller Method</span></span>
<span data-ttu-id="5e199-103">Obtiene la cadena que llamó esta cadena.</span><span class="sxs-lookup"><span data-stu-id="5e199-103">Gets the chain that called this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e199-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5e199-104">Syntax</span></span>  
  
```  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e199-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5e199-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="5e199-106">[out] Un puntero a la dirección de un objeto ICorDebugChain que representa la cadena de llamada.</span><span class="sxs-lookup"><span data-stu-id="5e199-106">[out] A pointer to the address of an ICorDebugChain object that represents the calling chain.</span></span>  
  
 <span data-ttu-id="5e199-107">Si esta cadena se llamó espontáneamente (como sería el caso si esta cadena o el depurador de inicializa la pila de llamadas), `ppChain` será null.</span><span class="sxs-lookup"><span data-stu-id="5e199-107">If this chain was spontaneously called (as would be the case if this chain or the debugger initialized the call stack), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e199-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5e199-108">Remarks</span></span>  
 <span data-ttu-id="5e199-109">La cadena de llamada puede ser en un subproceso diferente, si se calculan las referencias de la llamada a través de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="5e199-109">The calling chain may be on a different thread, if the call was marshaled across threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e199-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5e199-110">Requirements</span></span>  
 <span data-ttu-id="5e199-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e199-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e199-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e199-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e199-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e199-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e199-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e199-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
