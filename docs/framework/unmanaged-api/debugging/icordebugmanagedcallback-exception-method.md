---
title: "ICorDebugManagedCallback::Exception (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugManagedCallback.Exception
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Exception
helpviewer_keywords:
- Exception method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::Exception method [.NET Framework debugging]
ms.assetid: ab18a509-dff3-4930-b585-bd15e0414176
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b964f38501822360e6fc63600f7854c9a90f094c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackexception-method"></a><span data-ttu-id="a4aa5-102">ICorDebugManagedCallback::Exception (Método)</span><span class="sxs-lookup"><span data-stu-id="a4aa5-102">ICorDebugManagedCallback::Exception Method</span></span>
<span data-ttu-id="a4aa5-103">Notifica al depurador que se ha producido una excepción desde código administrado.</span><span class="sxs-lookup"><span data-stu-id="a4aa5-103">Notifies the debugger that an exception has been thrown from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4aa5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a4aa5-104">Syntax</span></span>  
  
```  
HRESULT Exception (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] BOOL                unhandled  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a4aa5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a4aa5-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="a4aa5-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación en el que se produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="a4aa5-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="a4aa5-107">[in] Un puntero a un objeto ICorDebugThread que representa el subproceso en el que se produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="a4aa5-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the exception was thrown.</span></span>  
  
 `unhandled`  
 <span data-ttu-id="a4aa5-108">[in] Si este valor es `false`, la excepción aún no se ha procesado por la aplicación; en caso contrario, la excepción está controlada y finalizará el proceso.</span><span class="sxs-lookup"><span data-stu-id="a4aa5-108">[in] If this value is `false`, the exception has not yet been processed by the application; otherwise, the exception is unhandled and will terminate the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4aa5-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a4aa5-109">Remarks</span></span>  
 <span data-ttu-id="a4aa5-110">La excepción concreta se puede recuperar desde el objeto de subproceso.</span><span class="sxs-lookup"><span data-stu-id="a4aa5-110">The specific exception can be retrieved from the thread object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4aa5-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a4aa5-111">Requirements</span></span>  
 <span data-ttu-id="a4aa5-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4aa5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4aa5-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a4aa5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a4aa5-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4aa5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4aa5-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4aa5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4aa5-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4aa5-116">See Also</span></span>  
 [<span data-ttu-id="a4aa5-117">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a4aa5-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
