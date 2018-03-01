---
title: "ICorDebugManagedCallback::ExitThread (Método)"
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
- ICorDebugManagedCallback.ExitThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitThread
helpviewer_keywords:
- ExitThread method [.NET Framework debugging]
- ICorDebugManagedCallback::ExitThread method [.NET Framework debugging]
ms.assetid: 62db708b-6cf0-45c5-b897-4b5c75bd2505
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6c39a8c92a8c0be8d0607663a833ac7307ca26d3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackexitthread-method"></a><span data-ttu-id="f5afa-102">ICorDebugManagedCallback::ExitThread (Método)</span><span class="sxs-lookup"><span data-stu-id="f5afa-102">ICorDebugManagedCallback::ExitThread Method</span></span>
<span data-ttu-id="f5afa-103">Notifica al depurador que un subproceso que se estaba ejecutando código administrado ha terminado.</span><span class="sxs-lookup"><span data-stu-id="f5afa-103">Notifies the debugger that a thread that was executing managed code has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5afa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f5afa-104">Syntax</span></span>  
  
```  
HRESULT ExitThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f5afa-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f5afa-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="f5afa-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el subproceso administrado.</span><span class="sxs-lookup"><span data-stu-id="f5afa-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="f5afa-107">[in] Un puntero a un objeto ICorDebugThread que representa el subproceso administrado.</span><span class="sxs-lookup"><span data-stu-id="f5afa-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5afa-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f5afa-108">Remarks</span></span>  
 <span data-ttu-id="f5afa-109">Una vez el `ExitThread` se desencadena la devolución de llamada, el subproceso ya no aparecerá en las enumeraciones de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="f5afa-109">Once the `ExitThread` callback is fired, the thread will no longer appear in thread enumerations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5afa-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f5afa-110">Requirements</span></span>  
 <span data-ttu-id="f5afa-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5afa-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5afa-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f5afa-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f5afa-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5afa-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5afa-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5afa-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5afa-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5afa-115">See Also</span></span>  
 [<span data-ttu-id="f5afa-116">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f5afa-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
