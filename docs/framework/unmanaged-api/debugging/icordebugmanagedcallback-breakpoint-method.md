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
ms.openlocfilehash: 381fdecfb2cb194cd1eb00a5b55db6fb89eeebbc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413922"
---
# <a name="icordebugmanagedcallbackbreakpoint-method"></a><span data-ttu-id="20a2d-102">ICorDebugManagedCallback::Breakpoint (Método)</span><span class="sxs-lookup"><span data-stu-id="20a2d-102">ICorDebugManagedCallback::Breakpoint Method</span></span>
<span data-ttu-id="20a2d-103">Notifica al depurador cuando se encuentra un punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="20a2d-103">Notifies the debugger when a breakpoint is encountered.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20a2d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="20a2d-104">Syntax</span></span>  
  
```  
HRESULT Breakpoint (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="20a2d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="20a2d-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="20a2d-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="20a2d-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="20a2d-107">[in] Un puntero a un objeto ICorDebugThread que representa el subproceso que contiene el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="20a2d-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="20a2d-108">[in] Un puntero a un objeto ICorDebugBreakpoint que representa el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="20a2d-108">[in] A pointer to an ICorDebugBreakpoint object that represents the breakpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20a2d-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="20a2d-109">Requirements</span></span>  
 <span data-ttu-id="20a2d-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20a2d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20a2d-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="20a2d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="20a2d-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20a2d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20a2d-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20a2d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20a2d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="20a2d-114">See Also</span></span>  
 [<span data-ttu-id="20a2d-115">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="20a2d-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
