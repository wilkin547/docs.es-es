---
title: ICorDebugChain::GetCallee (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCallee method
helpviewer_keywords:
- ICorDebugChain::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 19560c79-abdc-4bdf-a5fe-eb362a59edc0
topic_type:
- apiref
ms.openlocfilehash: a28da34cd3080826f346b8957aa6ba38258b924f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730128"
---
# <a name="icordebugchaingetcallee-method"></a><span data-ttu-id="b5e2b-102">ICorDebugChain::GetCallee (Método)</span><span class="sxs-lookup"><span data-stu-id="b5e2b-102">ICorDebugChain::GetCallee Method</span></span>

<span data-ttu-id="b5e2b-103">Obtiene la cadena a la que llamó esta cadena.</span><span class="sxs-lookup"><span data-stu-id="b5e2b-103">Gets the chain that was called by this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5e2b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b5e2b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5e2b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b5e2b-105">Parameters</span></span>  

 `ppChain`  
 <span data-ttu-id="b5e2b-106">enuncia Puntero a la dirección de un objeto ICorDebugChain que representa la cadena a la que se ha llamado.</span><span class="sxs-lookup"><span data-stu-id="b5e2b-106">[out] A pointer to the address of an ICorDebugChain object that represents the called chain.</span></span> <span data-ttu-id="b5e2b-107">Si esta cadena se está ejecutando actualmente (es decir, si esta cadena no está esperando a que devuelva una cadena llamada), `ppChain` será null.</span><span class="sxs-lookup"><span data-stu-id="b5e2b-107">If this chain is currently executing (that is, if this chain is not waiting for a called chain to return), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5e2b-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b5e2b-108">Remarks</span></span>  

 <span data-ttu-id="b5e2b-109">Esta cadena esperará a que se devuelva la cadena llamada antes de reanudar la ejecución.</span><span class="sxs-lookup"><span data-stu-id="b5e2b-109">This chain will wait for the called chain to return before it resumes execution.</span></span> <span data-ttu-id="b5e2b-110">La cadena llamada puede estar en otro subproceso en el caso de las llamadas de serialización entre subprocesos.</span><span class="sxs-lookup"><span data-stu-id="b5e2b-110">The called chain may be on another thread in the case of cross-thread marshaled calls.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5e2b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b5e2b-111">Requirements</span></span>  

 <span data-ttu-id="b5e2b-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5e2b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5e2b-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b5e2b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b5e2b-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5e2b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5e2b-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5e2b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
