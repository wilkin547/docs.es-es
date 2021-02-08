---
description: 'Más información acerca de: ICorDebugManagedCallback:: Editandcontinueremap ((método)'
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
ms.openlocfilehash: ad8932e41236cdb8ed213024efb4175292a5d5f7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791015"
---
# <a name="icordebugmanagedcallbackeditandcontinueremap-method"></a><span data-ttu-id="77d57-103">ICorDebugManagedCallback::EditAndContinueRemap (Método)</span><span class="sxs-lookup"><span data-stu-id="77d57-103">ICorDebugManagedCallback::EditAndContinueRemap Method</span></span>

<span data-ttu-id="77d57-104">Este método está en desuso.</span><span class="sxs-lookup"><span data-stu-id="77d57-104">This method has been deprecated.</span></span> <span data-ttu-id="77d57-105">Notifica al depurador que se ha enviado un evento de reasignación al entorno de desarrollo integrado (IDE).</span><span class="sxs-lookup"><span data-stu-id="77d57-105">It notifies the debugger that a remap event has been sent to the integrated development environment (IDE).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77d57-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="77d57-106">Syntax</span></span>  
  
```cpp  
HRESULT EditAndContinueRemap (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread *pThread,  
    [in] ICorDebugFunction *pFunction,  
    [in] BOOL fAccurate  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="77d57-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="77d57-107">Remarks</span></span>  

 <span data-ttu-id="77d57-108">`EditAndContinueRemap`Se llama al método cuando se ha intentado ejecutar el código en una versión anterior de una función actualizada.</span><span class="sxs-lookup"><span data-stu-id="77d57-108">The `EditAndContinueRemap` method is called when the execution of the code in an old version of an updated function has been attempted.</span></span> <span data-ttu-id="77d57-109">El Common Language Runtime llama al `EditAndContinueRemap` método para enviar un evento de reasignación al IDE.</span><span class="sxs-lookup"><span data-stu-id="77d57-109">The common language runtime calls the `EditAndContinueRemap` method to send a remap event to the IDE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77d57-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="77d57-110">Requirements</span></span>  

 <span data-ttu-id="77d57-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77d57-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77d57-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77d57-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77d57-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77d57-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77d57-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77d57-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77d57-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="77d57-115">See also</span></span>

- [<span data-ttu-id="77d57-116">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="77d57-116">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
