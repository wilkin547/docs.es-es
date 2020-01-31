---
title: ICorDebugManagedCallback::ExitAppDomain (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitAppDomain
helpviewer_keywords:
- ICorDebugManagedCallback::ExitAppDomain method [.NET Framework debugging]
- ExitAppDomain method [.NET Framework debugging]
ms.assetid: d815486e-b3bd-4fe8-ba28-02abdb4d67ba
topic_type:
- apiref
ms.openlocfilehash: 7bfa71ccff4a65e72a6b548a09d27648b67c0ae5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781851"
---
# <a name="icordebugmanagedcallbackexitappdomain-method"></a><span data-ttu-id="7355c-102">ICorDebugManagedCallback::ExitAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="7355c-102">ICorDebugManagedCallback::ExitAppDomain Method</span></span>
<span data-ttu-id="7355c-103">Notifica al depurador que se ha salido de un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="7355c-103">Notifies the debugger that an application domain has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7355c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7355c-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7355c-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="7355c-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="7355c-106">de Un puntero a un objeto ICorDebugProcess que representa el proceso que contiene el dominio de aplicación especificado.</span><span class="sxs-lookup"><span data-stu-id="7355c-106">[in] A pointer to an ICorDebugProcess object that represents the process that contains the given application domain.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="7355c-107">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que ha salido.</span><span class="sxs-lookup"><span data-stu-id="7355c-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has exited.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7355c-108">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="7355c-108">Requirements</span></span>  
 <span data-ttu-id="7355c-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7355c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7355c-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7355c-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7355c-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7355c-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7355c-112">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7355c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7355c-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="7355c-113">See also</span></span>

- [<span data-ttu-id="7355c-114">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7355c-114">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
