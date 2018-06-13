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
ms.openlocfilehash: 9721d88c8ce138b19c98f113d9eb034c5e1c55dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417695"
---
# <a name="icordebugmanagedcallbackcreatethread-method"></a><span data-ttu-id="470cb-102">ICorDebugManagedCallback::CreateThread (Método)</span><span class="sxs-lookup"><span data-stu-id="470cb-102">ICorDebugManagedCallback::CreateThread Method</span></span>
<span data-ttu-id="470cb-103">Notifica al depurador que un subproceso ha iniciado la ejecución de código administrado.</span><span class="sxs-lookup"><span data-stu-id="470cb-103">Notifies the debugger that a thread has started executing managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="470cb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="470cb-104">Syntax</span></span>  
  
```  
HRESULT CreateThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="470cb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="470cb-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="470cb-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el subproceso.</span><span class="sxs-lookup"><span data-stu-id="470cb-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="470cb-107">[in] Un puntero a un objeto ICorDebugThread que representa el subproceso.</span><span class="sxs-lookup"><span data-stu-id="470cb-107">[in] A pointer to an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="470cb-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="470cb-108">Remarks</span></span>  
 <span data-ttu-id="470cb-109">El subproceso se colocará en la primera instrucción de código administrado que se ejecute.</span><span class="sxs-lookup"><span data-stu-id="470cb-109">The thread will be positioned at the first managed code instruction to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="470cb-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="470cb-110">Requirements</span></span>  
 <span data-ttu-id="470cb-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="470cb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="470cb-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="470cb-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="470cb-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="470cb-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="470cb-114">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="470cb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="470cb-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="470cb-115">See Also</span></span>  
 [<span data-ttu-id="470cb-116">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="470cb-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
