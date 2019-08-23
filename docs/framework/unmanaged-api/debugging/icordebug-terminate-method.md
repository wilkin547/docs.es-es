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
ms.openlocfilehash: de37bb34aee9b6536ff892ac30855761bcc69445
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963128"
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="e3679-102">ICorDebug::Terminate (Método)</span><span class="sxs-lookup"><span data-stu-id="e3679-102">ICorDebug::Terminate Method</span></span>
<span data-ttu-id="e3679-103">Finaliza el `ICorDebug` objeto.</span><span class="sxs-lookup"><span data-stu-id="e3679-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e3679-104">`Terminate`no debe llamarse hasta que se haya recibido una devolución de llamada [ICorDebugManagedCallback:: ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) para todos los procesos que se están depurando.</span><span class="sxs-lookup"><span data-stu-id="e3679-104">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3679-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e3679-105">Syntax</span></span>  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="e3679-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e3679-106">Remarks</span></span>  
 <span data-ttu-id="e3679-107">`Terminate`se debe llamar a cuando `ICorDebug` el objeto ya no se necesita.</span><span class="sxs-lookup"><span data-stu-id="e3679-107">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3679-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e3679-108">Requirements</span></span>  
 <span data-ttu-id="e3679-109">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3679-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3679-110">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="e3679-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e3679-111">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3679-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3679-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3679-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3679-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3679-113">See also</span></span>

- [<span data-ttu-id="e3679-114">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e3679-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
