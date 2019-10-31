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
ms.openlocfilehash: 5ba6ce4e59057442a9f17338ec7bfff787bd5d05
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130790"
---
# <a name="icordebugmanagedcallbackexitappdomain-method"></a><span data-ttu-id="d3454-102">ICorDebugManagedCallback::ExitAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="d3454-102">ICorDebugManagedCallback::ExitAppDomain Method</span></span>
<span data-ttu-id="d3454-103">Notifica al depurador que se ha salido de un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d3454-103">Notifies the debugger that an application domain has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3454-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d3454-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3454-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d3454-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="d3454-106">de Un puntero a un objeto ICorDebugProcess que representa el proceso que contiene el dominio de aplicación especificado.</span><span class="sxs-lookup"><span data-stu-id="d3454-106">[in] A pointer to an ICorDebugProcess object that represents the process that contains the given application domain.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="d3454-107">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que ha salido.</span><span class="sxs-lookup"><span data-stu-id="d3454-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has exited.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3454-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d3454-108">Requirements</span></span>  
 <span data-ttu-id="d3454-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3454-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3454-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d3454-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d3454-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3454-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d3454-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3454-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3454-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3454-113">See also</span></span>

- [<span data-ttu-id="d3454-114">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d3454-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
