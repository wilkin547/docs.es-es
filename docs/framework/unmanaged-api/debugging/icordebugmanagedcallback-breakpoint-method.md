---
description: 'Más información acerca de: ICorDebugManagedCallback:: Breakpoint (método)'
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
ms.openlocfilehash: dd4339294d8c4061c89bbb0ba7023b313e06102f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660605"
---
# <a name="icordebugmanagedcallbackbreakpoint-method"></a><span data-ttu-id="87595-103">ICorDebugManagedCallback::Breakpoint (Método)</span><span class="sxs-lookup"><span data-stu-id="87595-103">ICorDebugManagedCallback::Breakpoint Method</span></span>

<span data-ttu-id="87595-104">Notifica al depurador cuando se encuentra un punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="87595-104">Notifies the debugger when a breakpoint is encountered.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87595-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="87595-105">Syntax</span></span>  
  
```cpp  
HRESULT Breakpoint (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87595-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="87595-106">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="87595-107">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="87595-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="87595-108">de Un puntero a un objeto ICorDebugThread que representa el subproceso que contiene el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="87595-108">[in] A pointer to an ICorDebugThread object that represents the thread that contains the breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="87595-109">de Un puntero a un objeto ICorDebugBreakpoint que representa el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="87595-109">[in] A pointer to an ICorDebugBreakpoint object that represents the breakpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87595-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="87595-110">Requirements</span></span>  

 <span data-ttu-id="87595-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87595-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87595-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="87595-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="87595-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87595-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87595-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87595-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87595-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="87595-115">See also</span></span>

- [<span data-ttu-id="87595-116">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="87595-116">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
