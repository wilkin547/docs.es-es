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
ms.openlocfilehash: d1bdb14e8c3a61a2b94cef778660eeb5c85c34df
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59149778"
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a><span data-ttu-id="94e2a-102">ICorDebugManagedCallback::EditAndContinueRemap (Método)</span><span class="sxs-lookup"><span data-stu-id="94e2a-102">ICorDebugManagedCallback::EditAndContinueRemap Method</span></span>
<span data-ttu-id="94e2a-103">Este método está en desuso.</span><span class="sxs-lookup"><span data-stu-id="94e2a-103">This method has been deprecated.</span></span> <span data-ttu-id="94e2a-104">Notifica al depurador que se ha enviado un evento de reasignación al entorno de desarrollo integrado (IDE).</span><span class="sxs-lookup"><span data-stu-id="94e2a-104">It notifies the debugger that a remap event has been sent to the integrated development environment (IDE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94e2a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="94e2a-105">Syntax</span></span>  
  
```  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="94e2a-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="94e2a-106">Remarks</span></span>  
 <span data-ttu-id="94e2a-107">El `EditAndContinueRemap` se llama al método cuando se intentó realizar la ejecución del código en una versión anterior de una función actualizada.</span><span class="sxs-lookup"><span data-stu-id="94e2a-107">The `EditAndContinueRemap` method is called when the execution of the code in an old version of an updated function has been attempted.</span></span> <span data-ttu-id="94e2a-108">Las llamadas en tiempo de ejecución de lenguaje común el `EditAndContinueRemap` método envíe un evento de reasignación al IDE.</span><span class="sxs-lookup"><span data-stu-id="94e2a-108">The common language runtime calls the `EditAndContinueRemap` method to send a remap event to the IDE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94e2a-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="94e2a-109">Requirements</span></span>  
 <span data-ttu-id="94e2a-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94e2a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94e2a-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94e2a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94e2a-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94e2a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94e2a-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94e2a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94e2a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="94e2a-114">See also</span></span>

- [<span data-ttu-id="94e2a-115">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="94e2a-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
