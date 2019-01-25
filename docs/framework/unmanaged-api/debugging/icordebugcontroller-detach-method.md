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
ms.openlocfilehash: 4f2dae147f8667a73036dbcf873e2082996b2755
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54666990"
---
# <a name="icordebugcontrollerdetach-method"></a><span data-ttu-id="5b5f8-102">ICorDebugController::Detach (Método)</span><span class="sxs-lookup"><span data-stu-id="5b5f8-102">ICorDebugController::Detach Method</span></span>
<span data-ttu-id="5b5f8-103">Desasocia al depurador desde el dominio de aplicación o proceso.</span><span class="sxs-lookup"><span data-stu-id="5b5f8-103">Detaches the debugger from the process or application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b5f8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5b5f8-104">Syntax</span></span>  
  
```  
HRESULT Detach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="5b5f8-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5b5f8-105">Remarks</span></span>  
 <span data-ttu-id="5b5f8-106">El proceso o dominio de aplicación continúa la ejecución con normalidad, pero el objeto "ICorDebugProcess" o "ICorDebugAppDomain" ya no es válido y no se producirá ninguna devolución de llamada adicional.</span><span class="sxs-lookup"><span data-stu-id="5b5f8-106">The process or application domain continues execution normally, but the "ICorDebugProcess" or "ICorDebugAppDomain" object is no longer valid and no further callbacks will occur.</span></span>  
  
 <span data-ttu-id="5b5f8-107">En la versión 2.0 de .NET Framework, si está habilitada la depuración no administrada, este método se producirá un error debido a limitaciones del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="5b5f8-107">In the .NET Framework version 2.0, if unmanaged debugging is enabled, this method will fail due to operating system limitations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b5f8-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5b5f8-108">Requirements</span></span>  
 <span data-ttu-id="5b5f8-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b5f8-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b5f8-110">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5b5f8-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5b5f8-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b5f8-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b5f8-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b5f8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b5f8-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b5f8-113">See also</span></span>

