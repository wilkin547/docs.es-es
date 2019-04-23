---
title: ICorDebugManagedCallback::ExitThread (Método)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37815d8aead1ec89826c13db6f012f2cd17bc792
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59132449"
---
# <a name="icordebugmanagedcallbackexitthread-method"></a><span data-ttu-id="19de0-102">ICorDebugManagedCallback::ExitThread (Método)</span><span class="sxs-lookup"><span data-stu-id="19de0-102">ICorDebugManagedCallback::ExitThread Method</span></span>
<span data-ttu-id="19de0-103">Notifica al depurador que ha salido de un subproceso que se estaba ejecutando código administrado.</span><span class="sxs-lookup"><span data-stu-id="19de0-103">Notifies the debugger that a thread that was executing managed code has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19de0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="19de0-104">Syntax</span></span>  
  
```  
HRESULT ExitThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19de0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="19de0-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="19de0-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el subproceso administrado.</span><span class="sxs-lookup"><span data-stu-id="19de0-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="19de0-107">[in] Un puntero a un objeto ICorDebugThread que representa el subproceso administrado.</span><span class="sxs-lookup"><span data-stu-id="19de0-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19de0-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="19de0-108">Remarks</span></span>  
 <span data-ttu-id="19de0-109">Una vez el `ExitThread` se desencadena la devolución de llamada, el subproceso ya no aparecerá en las enumeraciones de subproceso.</span><span class="sxs-lookup"><span data-stu-id="19de0-109">Once the `ExitThread` callback is fired, the thread will no longer appear in thread enumerations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19de0-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="19de0-110">Requirements</span></span>  
 <span data-ttu-id="19de0-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19de0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19de0-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="19de0-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="19de0-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19de0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19de0-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19de0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19de0-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="19de0-115">See also</span></span>

- [<span data-ttu-id="19de0-116">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="19de0-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
