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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85a9bde77f7c393756ec1d3e7d30b96392aa6a94
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59151806"
---
# <a name="icordebugcontrollerdetach-method"></a><span data-ttu-id="e44a6-102">ICorDebugController::Detach (Método)</span><span class="sxs-lookup"><span data-stu-id="e44a6-102">ICorDebugController::Detach Method</span></span>
<span data-ttu-id="e44a6-103">Desasocia al depurador desde el dominio de aplicación o proceso.</span><span class="sxs-lookup"><span data-stu-id="e44a6-103">Detaches the debugger from the process or application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e44a6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e44a6-104">Syntax</span></span>  
  
```  
HRESULT Detach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="e44a6-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e44a6-105">Remarks</span></span>  
 <span data-ttu-id="e44a6-106">El proceso o dominio de aplicación continúa la ejecución con normalidad, pero el objeto "ICorDebugProcess" o "ICorDebugAppDomain" ya no es válido y no se producirá ninguna devolución de llamada adicional.</span><span class="sxs-lookup"><span data-stu-id="e44a6-106">The process or application domain continues execution normally, but the "ICorDebugProcess" or "ICorDebugAppDomain" object is no longer valid and no further callbacks will occur.</span></span>  
  
 <span data-ttu-id="e44a6-107">En la versión 2.0 de .NET Framework, si está habilitada la depuración no administrada, este método se producirá un error debido a limitaciones del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="e44a6-107">In the .NET Framework version 2.0, if unmanaged debugging is enabled, this method will fail due to operating system limitations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e44a6-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e44a6-108">Requirements</span></span>  
 <span data-ttu-id="e44a6-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e44a6-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e44a6-110">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e44a6-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e44a6-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e44a6-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e44a6-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e44a6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e44a6-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="e44a6-113">See also</span></span>
