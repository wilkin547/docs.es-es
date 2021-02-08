---
description: 'Más información acerca de: ICorDebugManagedCallback:: Breakpointseterror ((método)'
title: ICorDebugManagedCallback::BreakpointSetError (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.BreakpointSetError
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::BreakpointSetError
helpviewer_keywords:
- BreakpointSetError method [.NET Framework debugging]
- ICorDebugManagedCallback::BreakpointSetError method [.NET Framework debugging]
ms.assetid: f2b773a4-c4d0-429c-9717-51d6e2ed86af
topic_type:
- apiref
ms.openlocfilehash: cf78b4dc06a71b6ac0eb4f653a00c1b3c6ae464b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791093"
---
# <a name="icordebugmanagedcallbackbreakpointseterror-method"></a><span data-ttu-id="f9f49-103">ICorDebugManagedCallback::BreakpointSetError (Método)</span><span class="sxs-lookup"><span data-stu-id="f9f49-103">ICorDebugManagedCallback::BreakpointSetError Method</span></span>

<span data-ttu-id="f9f49-104">Notifica al depurador que el Common Language Runtime no pudo enlazar con precisión un punto de interrupción establecido antes de que una función se compilara Just-in-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="f9f49-104">Notifies the debugger that the common language runtime was unable to accurately bind a breakpoint that was set before a function was just-in-time (JIT) compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9f49-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f9f49-105">Syntax</span></span>  
  
```cpp  
HRESULT BreakpointSetError (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint,  
    [in] DWORD                dwError  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9f49-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f9f49-106">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="f9f49-107">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el punto de interrupción sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="f9f49-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the unbound breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="f9f49-108">de Un puntero a un objeto ICorDebugThread que representa el subproceso que contiene el punto de interrupción sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="f9f49-108">[in] A pointer to an ICorDebugThread object that represents the thread that contains the unbound breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="f9f49-109">de Un puntero a un objeto ICorDebugBreakpoint que representa el punto de interrupción sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="f9f49-109">[in] A pointer to an ICorDebugBreakpoint object that represents the unbound breakpoint.</span></span>  
  
 `dwError`  
 <span data-ttu-id="f9f49-110">de Entero que indica el error.</span><span class="sxs-lookup"><span data-stu-id="f9f49-110">[in] An integer that indicates the error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9f49-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f9f49-111">Remarks</span></span>  

 <span data-ttu-id="f9f49-112">Nunca se alcanzará el punto de interrupción dado.</span><span class="sxs-lookup"><span data-stu-id="f9f49-112">The given breakpoint will never be hit.</span></span> <span data-ttu-id="f9f49-113">El depurador debe desactivarlo y volver a enlazarlo.</span><span class="sxs-lookup"><span data-stu-id="f9f49-113">The debugger should deactivate and rebind it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9f49-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f9f49-114">Requirements</span></span>  

 <span data-ttu-id="f9f49-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9f49-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9f49-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f9f49-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f9f49-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f9f49-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f9f49-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9f49-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9f49-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9f49-119">See also</span></span>

- [<span data-ttu-id="f9f49-120">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f9f49-120">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
