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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59149778"
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a><span data-ttu-id="67b80-102">ICorDebugManagedCallback::EditAndContinueRemap (Método)</span><span class="sxs-lookup"><span data-stu-id="67b80-102">ICorDebugManagedCallback::EditAndContinueRemap Method</span></span>
<span data-ttu-id="67b80-103">Este método está en desuso.</span><span class="sxs-lookup"><span data-stu-id="67b80-103">This method has been deprecated.</span></span> <span data-ttu-id="67b80-104">Notifica al depurador que se ha enviado un evento de reasignación al entorno de desarrollo integrado (IDE).</span><span class="sxs-lookup"><span data-stu-id="67b80-104">It notifies the debugger that a remap event has been sent to the integrated development environment (IDE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67b80-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="67b80-105">Syntax</span></span>  
  
```  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="67b80-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="67b80-106">Remarks</span></span>  
 <span data-ttu-id="67b80-107">El `EditAndContinueRemap` se llama al método cuando se intentó realizar la ejecución del código en una versión anterior de una función actualizada.</span><span class="sxs-lookup"><span data-stu-id="67b80-107">The `EditAndContinueRemap` method is called when the execution of the code in an old version of an updated function has been attempted.</span></span> <span data-ttu-id="67b80-108">Las llamadas en tiempo de ejecución de lenguaje común el `EditAndContinueRemap` método envíe un evento de reasignación al IDE.</span><span class="sxs-lookup"><span data-stu-id="67b80-108">The common language runtime calls the `EditAndContinueRemap` method to send a remap event to the IDE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67b80-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="67b80-109">Requirements</span></span>  
 <span data-ttu-id="67b80-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67b80-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67b80-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67b80-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67b80-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67b80-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="67b80-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="67b80-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="67b80-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="67b80-114">See also</span></span>

- [<span data-ttu-id="67b80-115">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="67b80-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
