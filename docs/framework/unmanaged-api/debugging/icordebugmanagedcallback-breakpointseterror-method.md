---
title: "ICorDebugManagedCallback::BreakpointSetError (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.BreakpointSetError
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::BreakpointSetError
helpviewer_keywords:
- BreakpointSetError method [.NET Framework debugging]
- ICorDebugManagedCallback::BreakpointSetError method [.NET Framework debugging]
ms.assetid: f2b773a4-c4d0-429c-9717-51d6e2ed86af
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ff1d3ee5d8bde9f2c1a6d3b97c42edb0b2deb6df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackbreakpointseterror-method"></a><span data-ttu-id="39e1a-102">ICorDebugManagedCallback::BreakpointSetError (Método)</span><span class="sxs-lookup"><span data-stu-id="39e1a-102">ICorDebugManagedCallback::BreakpointSetError Method</span></span>
<span data-ttu-id="39e1a-103">Notifica al depurador que common language runtime no pudo enlazar con precisión un punto de interrupción que estableció antes de que una función se compila con el compilador just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="39e1a-103">Notifies the debugger that the common language runtime was unable to accurately bind a breakpoint that was set before a function was just-in-time (JIT) compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39e1a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="39e1a-104">Syntax</span></span>  
  
```  
HRESULT BreakpointSetError (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint,  
    [in] DWORD                dwError  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="39e1a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="39e1a-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="39e1a-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el punto de interrupción sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="39e1a-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the unbound breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="39e1a-107">[in] Un puntero a un objeto ICorDebugThread que representa el subproceso que contiene el punto de interrupción sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="39e1a-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the unbound breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="39e1a-108">[in] Un puntero a un objeto ICorDebugBreakpoint que representa el punto de interrupción sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="39e1a-108">[in] A pointer to an ICorDebugBreakpoint object that represents the unbound breakpoint.</span></span>  
  
 `dwError`  
 <span data-ttu-id="39e1a-109">[in] Un entero que indica el error.</span><span class="sxs-lookup"><span data-stu-id="39e1a-109">[in] An integer that indicates the error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39e1a-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="39e1a-110">Remarks</span></span>  
 <span data-ttu-id="39e1a-111">Nunca se alcanzará el punto de interrupción especificado.</span><span class="sxs-lookup"><span data-stu-id="39e1a-111">The given breakpoint will never be hit.</span></span> <span data-ttu-id="39e1a-112">El depurador debe desactivar y enlazarlo.</span><span class="sxs-lookup"><span data-stu-id="39e1a-112">The debugger should deactivate and rebind it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39e1a-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="39e1a-113">Requirements</span></span>  
 <span data-ttu-id="39e1a-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39e1a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39e1a-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="39e1a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="39e1a-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39e1a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39e1a-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39e1a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39e1a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="39e1a-118">See Also</span></span>  
 [<span data-ttu-id="39e1a-119">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="39e1a-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
