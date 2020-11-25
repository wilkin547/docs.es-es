---
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
ms.openlocfilehash: cac8393408de626efe2360999e259780eac29f38
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721340"
---
# <a name="icordebugmanagedcallbackbreakpointseterror-method"></a><span data-ttu-id="05aba-102">ICorDebugManagedCallback::BreakpointSetError (Método)</span><span class="sxs-lookup"><span data-stu-id="05aba-102">ICorDebugManagedCallback::BreakpointSetError Method</span></span>

<span data-ttu-id="05aba-103">Notifica al depurador que el Common Language Runtime no pudo enlazar con precisión un punto de interrupción establecido antes de que una función se compilara Just-in-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="05aba-103">Notifies the debugger that the common language runtime was unable to accurately bind a breakpoint that was set before a function was just-in-time (JIT) compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05aba-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="05aba-104">Syntax</span></span>  
  
```cpp  
HRESULT BreakpointSetError (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint,  
    [in] DWORD                dwError  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05aba-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="05aba-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="05aba-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el punto de interrupción sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="05aba-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the unbound breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="05aba-107">de Un puntero a un objeto ICorDebugThread que representa el subproceso que contiene el punto de interrupción sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="05aba-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the unbound breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="05aba-108">de Un puntero a un objeto ICorDebugBreakpoint que representa el punto de interrupción sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="05aba-108">[in] A pointer to an ICorDebugBreakpoint object that represents the unbound breakpoint.</span></span>  
  
 `dwError`  
 <span data-ttu-id="05aba-109">de Entero que indica el error.</span><span class="sxs-lookup"><span data-stu-id="05aba-109">[in] An integer that indicates the error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05aba-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="05aba-110">Remarks</span></span>  

 <span data-ttu-id="05aba-111">Nunca se alcanzará el punto de interrupción dado.</span><span class="sxs-lookup"><span data-stu-id="05aba-111">The given breakpoint will never be hit.</span></span> <span data-ttu-id="05aba-112">El depurador debe desactivarlo y volver a enlazarlo.</span><span class="sxs-lookup"><span data-stu-id="05aba-112">The debugger should deactivate and rebind it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05aba-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="05aba-113">Requirements</span></span>  

 <span data-ttu-id="05aba-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05aba-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05aba-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="05aba-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="05aba-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05aba-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05aba-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05aba-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05aba-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="05aba-118">See also</span></span>

- [<span data-ttu-id="05aba-119">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="05aba-119">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
