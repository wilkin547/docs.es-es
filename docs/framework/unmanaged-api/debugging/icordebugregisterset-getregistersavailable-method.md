---
title: "ICorDebugRegisterSet::GetRegistersAvailable (Método)"
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
- ICorDebugRegisterSet.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable
helpviewer_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable method [.NET Framework debugging]
- GetRegistersAvailable method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 4ba08ffa-55a2-4662-9d6d-4738f1db60c9
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fd7ff2b711d81ba1fe8fda9422587ec265dd88dd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugregistersetgetregistersavailable-method"></a><span data-ttu-id="c2a2d-102">ICorDebugRegisterSet::GetRegistersAvailable (Método)</span><span class="sxs-lookup"><span data-stu-id="c2a2d-102">ICorDebugRegisterSet::GetRegistersAvailable Method</span></span>
<span data-ttu-id="c2a2d-103">Obtiene un poco de máscara que indica que se registra en esta [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) están disponibles actualmente.</span><span class="sxs-lookup"><span data-stu-id="c2a2d-103">Gets a bit mask indicating which registers in this [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) are currently available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2a2d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c2a2d-104">Syntax</span></span>  
  
```  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c2a2d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c2a2d-105">Parameters</span></span>  
 `pAvailable`  
 <span data-ttu-id="c2a2d-106">[out] Una máscara de bits que indica qué registros están disponibles actualmente.</span><span class="sxs-lookup"><span data-stu-id="c2a2d-106">[out] A bit mask that indicates which registers are currently available.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2a2d-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c2a2d-107">Remarks</span></span>  
 <span data-ttu-id="c2a2d-108">Un registro no esté disponible si no se puede determinar su valor para la situación determinada.</span><span class="sxs-lookup"><span data-stu-id="c2a2d-108">A register may be unavailable if its value cannot be determined for the given situation.</span></span>  
  
 <span data-ttu-id="c2a2d-109">La máscara devuelta contiene un bit por cada registro (1 << el índice de registro).</span><span class="sxs-lookup"><span data-stu-id="c2a2d-109">The returned mask contains a bit for each register (1 << the register index).</span></span> <span data-ttu-id="c2a2d-110">El valor de bit es 1 si el registro está disponible, o 0 si no está disponible.</span><span class="sxs-lookup"><span data-stu-id="c2a2d-110">The bit value is 1 if the register is available, or 0 if it is not available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2a2d-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c2a2d-111">Requirements</span></span>  
 <span data-ttu-id="c2a2d-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2a2d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2a2d-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c2a2d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c2a2d-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2a2d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2a2d-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2a2d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2a2d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c2a2d-116">See Also</span></span>  
 [<span data-ttu-id="c2a2d-117">ICorDebugRegisterSet (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c2a2d-117">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 [<span data-ttu-id="c2a2d-118">ICorDebugRegisterSet2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c2a2d-118">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
