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
ms.openlocfilehash: 51beed47e7187d6fa22e60baed16598a8ad73adb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688996"
---
# <a name="icordebugmanagedcallbackexitappdomain-method"></a><span data-ttu-id="3719b-102">ICorDebugManagedCallback::ExitAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="3719b-102">ICorDebugManagedCallback::ExitAppDomain Method</span></span>

<span data-ttu-id="3719b-103">Notifica al depurador que se ha salido de un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="3719b-103">Notifies the debugger that an application domain has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3719b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3719b-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3719b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3719b-105">Parameters</span></span>  

 `pProcess`  
 <span data-ttu-id="3719b-106">de Un puntero a un objeto ICorDebugProcess que representa el proceso que contiene el dominio de aplicación especificado.</span><span class="sxs-lookup"><span data-stu-id="3719b-106">[in] A pointer to an ICorDebugProcess object that represents the process that contains the given application domain.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="3719b-107">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que ha salido.</span><span class="sxs-lookup"><span data-stu-id="3719b-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has exited.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3719b-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3719b-108">Requirements</span></span>  

 <span data-ttu-id="3719b-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3719b-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3719b-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3719b-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3719b-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3719b-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3719b-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3719b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3719b-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3719b-113">See also</span></span>

- [<span data-ttu-id="3719b-114">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3719b-114">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
