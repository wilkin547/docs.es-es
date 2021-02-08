---
description: 'Más información acerca de: ICorDebugManagedCallback:: Exitappdomain ((método)'
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
ms.openlocfilehash: a08f29c6c4c8196b968118433c31afb715935aec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803625"
---
# <a name="icordebugmanagedcallbackexitappdomain-method"></a><span data-ttu-id="b3ef8-103">ICorDebugManagedCallback::ExitAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="b3ef8-103">ICorDebugManagedCallback::ExitAppDomain Method</span></span>

<span data-ttu-id="b3ef8-104">Notifica al depurador que se ha salido de un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b3ef8-104">Notifies the debugger that an application domain has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3ef8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b3ef8-105">Syntax</span></span>  
  
```cpp  
HRESULT ExitAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3ef8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b3ef8-106">Parameters</span></span>  

 `pProcess`  
 <span data-ttu-id="b3ef8-107">de Un puntero a un objeto ICorDebugProcess que representa el proceso que contiene el dominio de aplicación especificado.</span><span class="sxs-lookup"><span data-stu-id="b3ef8-107">[in] A pointer to an ICorDebugProcess object that represents the process that contains the given application domain.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="b3ef8-108">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que ha salido.</span><span class="sxs-lookup"><span data-stu-id="b3ef8-108">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has exited.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3ef8-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b3ef8-109">Requirements</span></span>  

 <span data-ttu-id="b3ef8-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3ef8-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3ef8-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b3ef8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b3ef8-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3ef8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b3ef8-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3ef8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3ef8-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3ef8-114">See also</span></span>

- [<span data-ttu-id="b3ef8-115">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b3ef8-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
