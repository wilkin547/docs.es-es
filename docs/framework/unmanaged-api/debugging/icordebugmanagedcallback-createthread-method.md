---
title: ICorDebugManagedCallback::CreateThread (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.CreateThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateThread method
helpviewer_keywords:
- ICorDebugManagedCallback::CreateThread method [.NET Framework debugging]
- CreateThread method [.NET Framework debugging]
ms.assetid: 6b961728-21c4-4e8d-ae81-197458be62f4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c48e92c73347957d8acc5c209f6f5473e9e18524
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988278"
---
# <a name="icordebugmanagedcallbackcreatethread-method"></a><span data-ttu-id="5fa17-102">ICorDebugManagedCallback::CreateThread (Método)</span><span class="sxs-lookup"><span data-stu-id="5fa17-102">ICorDebugManagedCallback::CreateThread Method</span></span>
<span data-ttu-id="5fa17-103">Notifica al depurador que inicia un subproceso ejecuta código administrado.</span><span class="sxs-lookup"><span data-stu-id="5fa17-103">Notifies the debugger that a thread has started executing managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fa17-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5fa17-104">Syntax</span></span>  
  
```  
HRESULT CreateThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5fa17-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5fa17-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="5fa17-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el subproceso.</span><span class="sxs-lookup"><span data-stu-id="5fa17-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="5fa17-107">[in] Un puntero a un objeto ICorDebugThread que representa el subproceso.</span><span class="sxs-lookup"><span data-stu-id="5fa17-107">[in] A pointer to an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5fa17-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5fa17-108">Remarks</span></span>  
 <span data-ttu-id="5fa17-109">El subproceso se colocará en la primera instrucción de código administrado que se ejecutará.</span><span class="sxs-lookup"><span data-stu-id="5fa17-109">The thread will be positioned at the first managed code instruction to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fa17-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5fa17-110">Requirements</span></span>  
 <span data-ttu-id="5fa17-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fa17-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fa17-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5fa17-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5fa17-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5fa17-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5fa17-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fa17-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fa17-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="5fa17-115">See also</span></span>

- [<span data-ttu-id="5fa17-116">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5fa17-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
