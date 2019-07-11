---
title: ICorDebugManagedCallback::EditAndContinueRemap (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.EditAndContinueRemap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::EditAndContinueRemap
helpviewer_keywords:
- EditAndContinueRemap method [.NET Framework debugging]
- ICorDebugManagedCallback::EditAndContinueRemap method [.NET Framework debugging]
ms.assetid: 24a8fcce-317e-48ff-aefc-d86123ada935
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 100688ece4ebb984d3d03823ab01bbaae7d395db
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760272"
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a><span data-ttu-id="83bc8-102">ICorDebugManagedCallback::EditAndContinueRemap (Método)</span><span class="sxs-lookup"><span data-stu-id="83bc8-102">ICorDebugManagedCallback::EditAndContinueRemap Method</span></span>
<span data-ttu-id="83bc8-103">Este método está en desuso.</span><span class="sxs-lookup"><span data-stu-id="83bc8-103">This method has been deprecated.</span></span> <span data-ttu-id="83bc8-104">Notifica al depurador que se ha enviado un evento de reasignación al entorno de desarrollo integrado (IDE).</span><span class="sxs-lookup"><span data-stu-id="83bc8-104">It notifies the debugger that a remap event has been sent to the integrated development environment (IDE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83bc8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="83bc8-105">Syntax</span></span>  
  
```cpp  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="83bc8-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="83bc8-106">Remarks</span></span>  
 <span data-ttu-id="83bc8-107">El `EditAndContinueRemap` se llama al método cuando se intentó realizar la ejecución del código en una versión anterior de una función actualizada.</span><span class="sxs-lookup"><span data-stu-id="83bc8-107">The `EditAndContinueRemap` method is called when the execution of the code in an old version of an updated function has been attempted.</span></span> <span data-ttu-id="83bc8-108">Las llamadas en tiempo de ejecución de lenguaje común el `EditAndContinueRemap` método envíe un evento de reasignación al IDE.</span><span class="sxs-lookup"><span data-stu-id="83bc8-108">The common language runtime calls the `EditAndContinueRemap` method to send a remap event to the IDE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83bc8-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="83bc8-109">Requirements</span></span>  
 <span data-ttu-id="83bc8-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83bc8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83bc8-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="83bc8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="83bc8-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83bc8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83bc8-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83bc8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83bc8-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="83bc8-114">See also</span></span>

- [<span data-ttu-id="83bc8-115">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="83bc8-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
