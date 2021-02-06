---
description: 'Más información sobre: ICorDebugChain:: Getcallee ((método)'
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
ms.openlocfilehash: 4787893c86804c648dae14bf2e6f7425808104b7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661433"
---
# <a name="icordebugchaingetcallee-method"></a><span data-ttu-id="33d80-103">ICorDebugChain::GetCallee (Método)</span><span class="sxs-lookup"><span data-stu-id="33d80-103">ICorDebugChain::GetCallee Method</span></span>

<span data-ttu-id="33d80-104">Obtiene la cadena a la que llamó esta cadena.</span><span class="sxs-lookup"><span data-stu-id="33d80-104">Gets the chain that was called by this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33d80-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33d80-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33d80-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="33d80-106">Parameters</span></span>  

 `ppChain`  
 <span data-ttu-id="33d80-107">enuncia Puntero a la dirección de un objeto ICorDebugChain que representa la cadena a la que se ha llamado.</span><span class="sxs-lookup"><span data-stu-id="33d80-107">[out] A pointer to the address of an ICorDebugChain object that represents the called chain.</span></span> <span data-ttu-id="33d80-108">Si esta cadena se está ejecutando actualmente (es decir, si esta cadena no está esperando a que devuelva una cadena llamada), `ppChain` será null.</span><span class="sxs-lookup"><span data-stu-id="33d80-108">If this chain is currently executing (that is, if this chain is not waiting for a called chain to return), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33d80-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="33d80-109">Remarks</span></span>  

 <span data-ttu-id="33d80-110">Esta cadena esperará a que se devuelva la cadena llamada antes de reanudar la ejecución.</span><span class="sxs-lookup"><span data-stu-id="33d80-110">This chain will wait for the called chain to return before it resumes execution.</span></span> <span data-ttu-id="33d80-111">La cadena llamada puede estar en otro subproceso en el caso de las llamadas de serialización entre subprocesos.</span><span class="sxs-lookup"><span data-stu-id="33d80-111">The called chain may be on another thread in the case of cross-thread marshaled calls.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33d80-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="33d80-112">Requirements</span></span>  

 <span data-ttu-id="33d80-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33d80-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33d80-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="33d80-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="33d80-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33d80-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33d80-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33d80-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
