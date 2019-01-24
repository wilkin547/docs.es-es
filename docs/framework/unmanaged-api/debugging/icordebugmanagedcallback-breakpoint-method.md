---
title: ICorDebugManagedCallback::Breakpoint (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Breakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Breakpoint
helpviewer_keywords:
- ICorDebugManagedCallback::Breakpoint method [.NET Framework debugging]
- Breakpoint method [.NET Framework debugging]
ms.assetid: 60b279b0-a726-46d2-8c53-76986a007ebb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a1df57e82309d42092c38dfcdd8b65ccc2797f9a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54743289"
---
# <a name="icordebugmanagedcallbackbreakpoint-method"></a><span data-ttu-id="2a2f9-102">ICorDebugManagedCallback::Breakpoint (Método)</span><span class="sxs-lookup"><span data-stu-id="2a2f9-102">ICorDebugManagedCallback::Breakpoint Method</span></span>
<span data-ttu-id="2a2f9-103">Notifica al depurador cuando se encuentra un punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="2a2f9-103">Notifies the debugger when a breakpoint is encountered.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a2f9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2a2f9-104">Syntax</span></span>  
  
```  
HRESULT Breakpoint (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2a2f9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2a2f9-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="2a2f9-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="2a2f9-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="2a2f9-107">[in] Un puntero a un objeto ICorDebugThread que representa el subproceso que contiene el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="2a2f9-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="2a2f9-108">[in] Un puntero a un objeto ICorDebugBreakpoint que representa el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="2a2f9-108">[in] A pointer to an ICorDebugBreakpoint object that represents the breakpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a2f9-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2a2f9-109">Requirements</span></span>  
 <span data-ttu-id="2a2f9-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a2f9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a2f9-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2a2f9-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2a2f9-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a2f9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a2f9-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a2f9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a2f9-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a2f9-114">See also</span></span>
- [<span data-ttu-id="2a2f9-115">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2a2f9-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
