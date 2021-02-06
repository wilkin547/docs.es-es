---
description: 'Más información acerca de: ICorDebugManagedCallback:: NameChange ((método)'
title: ICorDebugManagedCallback::NameChange (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.NameChange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::NameChange
helpviewer_keywords:
- ICorDebugManagedCallback::NameChange method [.NET Framework debugging]
- NameChange method [.NET Framework debugging]
ms.assetid: a7018a0e-880e-4b68-b52a-1cd22c7aad62
topic_type:
- apiref
ms.openlocfilehash: 5f337f5e05b80c97e8b8e48f8b7bc76b3232b2c8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660419"
---
# <a name="icordebugmanagedcallbacknamechange-method"></a><span data-ttu-id="df422-103">ICorDebugManagedCallback::NameChange (Método)</span><span class="sxs-lookup"><span data-stu-id="df422-103">ICorDebugManagedCallback::NameChange Method</span></span>

<span data-ttu-id="df422-104">Notifica al depurador que ha cambiado el nombre de un dominio de aplicación o un subproceso.</span><span class="sxs-lookup"><span data-stu-id="df422-104">Notifies the debugger that the name of either an application domain or a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df422-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="df422-105">Syntax</span></span>  
  
```cpp  
HRESULT NameChange (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df422-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="df422-106">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="df422-107">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que tenía un cambio de nombre o que contiene el subproceso que tenía un cambio de nombre.</span><span class="sxs-lookup"><span data-stu-id="df422-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that either had a name change or that contains the thread that had a name change.</span></span>  
  
 `pThread`  
 <span data-ttu-id="df422-108">de Un puntero a un objeto ICorDebugThread que representa el subproceso cuyo nombre ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="df422-108">[in] A pointer to an ICorDebugThread object that represents the thread that had a name change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df422-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="df422-109">Requirements</span></span>  

 <span data-ttu-id="df422-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df422-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df422-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df422-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df422-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df422-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df422-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df422-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df422-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="df422-114">See also</span></span>

- [<span data-ttu-id="df422-115">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="df422-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
