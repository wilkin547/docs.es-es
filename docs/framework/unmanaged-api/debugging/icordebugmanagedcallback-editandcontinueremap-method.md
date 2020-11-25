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
ms.openlocfilehash: 1d8aa2cca9dbbeaa9e03813b177ca59125770803
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721288"
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a><span data-ttu-id="fef79-102">ICorDebugManagedCallback::EditAndContinueRemap (Método)</span><span class="sxs-lookup"><span data-stu-id="fef79-102">ICorDebugManagedCallback::EditAndContinueRemap Method</span></span>

<span data-ttu-id="fef79-103">Este método está en desuso.</span><span class="sxs-lookup"><span data-stu-id="fef79-103">This method has been deprecated.</span></span> <span data-ttu-id="fef79-104">Notifica al depurador que se ha enviado un evento de reasignación al entorno de desarrollo integrado (IDE).</span><span class="sxs-lookup"><span data-stu-id="fef79-104">It notifies the debugger that a remap event has been sent to the integrated development environment (IDE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fef79-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fef79-105">Syntax</span></span>  
  
```cpp  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="fef79-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fef79-106">Remarks</span></span>  

 <span data-ttu-id="fef79-107">`EditAndContinueRemap`Se llama al método cuando se ha intentado ejecutar el código en una versión anterior de una función actualizada.</span><span class="sxs-lookup"><span data-stu-id="fef79-107">The `EditAndContinueRemap` method is called when the execution of the code in an old version of an updated function has been attempted.</span></span> <span data-ttu-id="fef79-108">El Common Language Runtime llama al `EditAndContinueRemap` método para enviar un evento de reasignación al IDE.</span><span class="sxs-lookup"><span data-stu-id="fef79-108">The common language runtime calls the `EditAndContinueRemap` method to send a remap event to the IDE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fef79-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fef79-109">Requirements</span></span>  

 <span data-ttu-id="fef79-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fef79-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fef79-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fef79-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fef79-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fef79-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fef79-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fef79-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fef79-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fef79-114">See also</span></span>

- [<span data-ttu-id="fef79-115">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fef79-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
