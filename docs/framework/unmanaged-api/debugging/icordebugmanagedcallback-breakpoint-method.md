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
ms.openlocfilehash: ac91a9c662a82c5ab870d01cb4b5d87c7af6b6ba
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782075"
---
# <a name="icordebugmanagedcallbackbreakpoint-method"></a><span data-ttu-id="6de52-102">ICorDebugManagedCallback::Breakpoint (Método)</span><span class="sxs-lookup"><span data-stu-id="6de52-102">ICorDebugManagedCallback::Breakpoint Method</span></span>
<span data-ttu-id="6de52-103">Notifica al depurador cuando se encuentra un punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="6de52-103">Notifies the debugger when a breakpoint is encountered.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6de52-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6de52-104">Syntax</span></span>  
  
```cpp  
HRESULT Breakpoint (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6de52-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="6de52-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="6de52-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="6de52-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="6de52-107">de Un puntero a un objeto ICorDebugThread que representa el subproceso que contiene el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="6de52-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="6de52-108">de Un puntero a un objeto ICorDebugBreakpoint que representa el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="6de52-108">[in] A pointer to an ICorDebugBreakpoint object that represents the breakpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6de52-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="6de52-109">Requirements</span></span>  
 <span data-ttu-id="6de52-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6de52-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6de52-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6de52-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6de52-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6de52-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6de52-113">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6de52-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6de52-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="6de52-114">See also</span></span>

- [<span data-ttu-id="6de52-115">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6de52-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
