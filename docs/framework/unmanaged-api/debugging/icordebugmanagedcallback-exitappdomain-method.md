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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f909eddde182a73709be9ca5cafec6285db46b4c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412859"
---
# <a name="icordebugmanagedcallbackexitappdomain-method"></a><span data-ttu-id="0bb57-102">ICorDebugManagedCallback::ExitAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="0bb57-102">ICorDebugManagedCallback::ExitAppDomain Method</span></span>
<span data-ttu-id="0bb57-103">Notifica al depurador que un dominio de aplicación ha salido.</span><span class="sxs-lookup"><span data-stu-id="0bb57-103">Notifies the debugger that an application domain has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bb57-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0bb57-104">Syntax</span></span>  
  
```  
HRESULT ExitAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0bb57-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0bb57-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="0bb57-106">[in] Un puntero a un objeto ICorDebugProcess que representa el proceso que contiene el dominio de aplicación determinado.</span><span class="sxs-lookup"><span data-stu-id="0bb57-106">[in] A pointer to an ICorDebugProcess object that represents the process that contains the given application domain.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="0bb57-107">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que se ha salido.</span><span class="sxs-lookup"><span data-stu-id="0bb57-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has exited.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bb57-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0bb57-108">Requirements</span></span>  
 <span data-ttu-id="0bb57-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0bb57-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bb57-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0bb57-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0bb57-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0bb57-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0bb57-112">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bb57-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bb57-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="0bb57-113">See Also</span></span>  
 [<span data-ttu-id="0bb57-114">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0bb57-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
