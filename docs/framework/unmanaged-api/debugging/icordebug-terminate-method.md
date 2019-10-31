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
ms.openlocfilehash: 78838e9002cb3f5263395af9de255c54de47b6ae
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134017"
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="5f7bb-102">ICorDebug::Terminate (Método)</span><span class="sxs-lookup"><span data-stu-id="5f7bb-102">ICorDebug::Terminate Method</span></span>
<span data-ttu-id="5f7bb-103">Finaliza el objeto `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="5f7bb-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5f7bb-104">no se debe llamar a `Terminate` hasta que se haya recibido una devolución de llamada [ICorDebugManagedCallback:: ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) para todos los procesos que se están depurando.</span><span class="sxs-lookup"><span data-stu-id="5f7bb-104">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f7bb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5f7bb-105">Syntax</span></span>  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="5f7bb-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5f7bb-106">Remarks</span></span>  
 <span data-ttu-id="5f7bb-107">se debe llamar a `Terminate` cuando ya no se necesita el objeto `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="5f7bb-107">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f7bb-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5f7bb-108">Requirements</span></span>  
 <span data-ttu-id="5f7bb-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f7bb-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f7bb-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f7bb-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f7bb-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f7bb-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f7bb-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f7bb-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f7bb-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f7bb-113">See also</span></span>

- [<span data-ttu-id="5f7bb-114">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5f7bb-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
