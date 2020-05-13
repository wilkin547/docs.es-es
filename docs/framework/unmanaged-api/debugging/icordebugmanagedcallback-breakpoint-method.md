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
ms.openlocfilehash: d8e62499a813419ecc30924624da553ca9f2c7b2
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213405"
---
# <a name="icordebugmanagedcallbackbreakpoint-method"></a><span data-ttu-id="44790-102">ICorDebugManagedCallback::Breakpoint (Método)</span><span class="sxs-lookup"><span data-stu-id="44790-102">ICorDebugManagedCallback::Breakpoint Method</span></span>
<span data-ttu-id="44790-103">Notifica al depurador cuando se encuentra un punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="44790-103">Notifies the debugger when a breakpoint is encountered.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44790-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="44790-104">Syntax</span></span>  
  
```cpp  
HRESULT Breakpoint (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44790-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="44790-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="44790-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="44790-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="44790-107">de Un puntero a un objeto ICorDebugThread que representa el subproceso que contiene el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="44790-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="44790-108">de Un puntero a un objeto ICorDebugBreakpoint que representa el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="44790-108">[in] A pointer to an ICorDebugBreakpoint object that represents the breakpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44790-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="44790-109">Requirements</span></span>  
 <span data-ttu-id="44790-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44790-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44790-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="44790-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="44790-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44790-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44790-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44790-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44790-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="44790-114">See also</span></span>

- [<span data-ttu-id="44790-115">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="44790-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
