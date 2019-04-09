---
title: ICorDebug::Terminate (Método)
ms.date: 03/30/2017
api_name:
- ICorDebug.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::Terminate
helpviewer_keywords:
- Terminate method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Terminate method [.NET Framework debugging]
ms.assetid: fffe5616-0896-4426-ab5e-21869b514883
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 321298ce942b35d11a861c87cdf6b8714179ea97
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080844"
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="a99f3-102">ICorDebug::Terminate (Método)</span><span class="sxs-lookup"><span data-stu-id="a99f3-102">ICorDebug::Terminate Method</span></span>
<span data-ttu-id="a99f3-103">Finaliza el `ICorDebug` objeto.</span><span class="sxs-lookup"><span data-stu-id="a99f3-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
>  `Terminate` <span data-ttu-id="a99f3-104">no debe llamarse hasta un [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) se ha recibido la devolución de llamada para todos los procesos que se está depurados.</span><span class="sxs-lookup"><span data-stu-id="a99f3-104">should not be called until an [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a99f3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a99f3-105">Syntax</span></span>  
  
```  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="a99f3-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a99f3-106">Remarks</span></span>  
 `Terminate` <span data-ttu-id="a99f3-107">debe llamarse cuando la `ICorDebug` objeto ya no es necesario.</span><span class="sxs-lookup"><span data-stu-id="a99f3-107">must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a99f3-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a99f3-108">Requirements</span></span>  
 <span data-ttu-id="a99f3-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a99f3-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a99f3-110">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a99f3-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a99f3-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a99f3-111">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a99f3-112">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="a99f3-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a99f3-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="a99f3-113">See also</span></span>

- [<span data-ttu-id="a99f3-114">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a99f3-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
