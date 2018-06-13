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
ms.openlocfilehash: 9e8aa71a79bee45d5a8e1f3448c781e6ba1ec605
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414143"
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a><span data-ttu-id="00a13-102">ICorDebugManagedCallback::EditAndContinueRemap (Método)</span><span class="sxs-lookup"><span data-stu-id="00a13-102">ICorDebugManagedCallback::EditAndContinueRemap Method</span></span>
<span data-ttu-id="00a13-103">Este método está en desuso.</span><span class="sxs-lookup"><span data-stu-id="00a13-103">This method has been deprecated.</span></span> <span data-ttu-id="00a13-104">Notifica al depurador que se ha enviado un evento de reasignación al entorno de desarrollo integrado (IDE).</span><span class="sxs-lookup"><span data-stu-id="00a13-104">It notifies the debugger that a remap event has been sent to the integrated development environment (IDE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00a13-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="00a13-105">Syntax</span></span>  
  
```  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="00a13-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="00a13-106">Remarks</span></span>  
 <span data-ttu-id="00a13-107">El `EditAndContinueRemap` método se llama cuando se intentó la ejecución del código en una versión anterior de una función actualizada.</span><span class="sxs-lookup"><span data-stu-id="00a13-107">The `EditAndContinueRemap` method is called when the execution of the code in an old version of an updated function has been attempted.</span></span> <span data-ttu-id="00a13-108">El common language runtime llama el `EditAndContinueRemap` método para enviar un evento de reasignación al IDE.</span><span class="sxs-lookup"><span data-stu-id="00a13-108">The common language runtime calls the `EditAndContinueRemap` method to send a remap event to the IDE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00a13-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="00a13-109">Requirements</span></span>  
 <span data-ttu-id="00a13-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00a13-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00a13-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="00a13-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="00a13-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00a13-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00a13-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00a13-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00a13-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="00a13-114">See Also</span></span>  
 [<span data-ttu-id="00a13-115">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="00a13-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
