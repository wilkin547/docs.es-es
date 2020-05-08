---
title: ICorDebugController::Detach (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugController.Detach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Detach
helpviewer_keywords:
- Detach method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Detach method [.NET Framework debugging]
ms.assetid: 06fae364-f2c6-4a50-aa7e-3da9f2684dc3
topic_type:
- apiref
ms.openlocfilehash: 480fec4897dac73594515ba8bc0f0e96ceb79ace
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892913"
---
# <a name="icordebugcontrollerdetach-method"></a><span data-ttu-id="4cabd-102">ICorDebugController::Detach (Método)</span><span class="sxs-lookup"><span data-stu-id="4cabd-102">ICorDebugController::Detach Method</span></span>
<span data-ttu-id="4cabd-103">Desasocia el depurador del dominio del proceso o de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4cabd-103">Detaches the debugger from the process or application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cabd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4cabd-104">Syntax</span></span>  
  
```cpp  
HRESULT Detach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="4cabd-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4cabd-105">Remarks</span></span>  
 <span data-ttu-id="4cabd-106">El dominio del proceso o de la aplicación continúa la ejecución con normalidad, pero el objeto "ICorDebugProcess" o "ICorDebugAppDomain" ya no es válido y no se producirán más devoluciones de llamada.</span><span class="sxs-lookup"><span data-stu-id="4cabd-106">The process or application domain continues execution normally, but the "ICorDebugProcess" or "ICorDebugAppDomain" object is no longer valid and no further callbacks will occur.</span></span>  
  
 <span data-ttu-id="4cabd-107">En la versión .NET Framework 2,0, si está habilitada la depuración no administrada, este método producirá un error debido a las limitaciones del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="4cabd-107">In the .NET Framework version 2.0, if unmanaged debugging is enabled, this method will fail due to operating system limitations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cabd-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4cabd-108">Requirements</span></span>  
 <span data-ttu-id="4cabd-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4cabd-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cabd-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4cabd-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4cabd-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4cabd-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4cabd-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cabd-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cabd-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4cabd-113">See also</span></span>
