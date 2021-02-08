---
description: 'Más información acerca de: ICorDebugManagedCallback:: ExitThread (método)'
title: ICorDebugManagedCallback::ExitThread (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitThread
helpviewer_keywords:
- ExitThread method [.NET Framework debugging]
- ICorDebugManagedCallback::ExitThread method [.NET Framework debugging]
ms.assetid: 62db708b-6cf0-45c5-b897-4b5c75bd2505
topic_type:
- apiref
ms.openlocfilehash: 4c9472d6377246833c7c30f072549da9c44f05d8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790950"
---
# <a name="icordebugmanagedcallbackexitthread-method"></a><span data-ttu-id="87710-103">ICorDebugManagedCallback::ExitThread (Método)</span><span class="sxs-lookup"><span data-stu-id="87710-103">ICorDebugManagedCallback::ExitThread Method</span></span>

<span data-ttu-id="87710-104">Notifica al depurador que un subproceso que estaba ejecutando código administrado ha salido.</span><span class="sxs-lookup"><span data-stu-id="87710-104">Notifies the debugger that a thread that was executing managed code has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87710-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="87710-105">Syntax</span></span>  
  
```cpp  
HRESULT ExitThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87710-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="87710-106">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="87710-107">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el subproceso administrado.</span><span class="sxs-lookup"><span data-stu-id="87710-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="87710-108">de Un puntero a un objeto ICorDebugThread que representa el subproceso administrado.</span><span class="sxs-lookup"><span data-stu-id="87710-108">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87710-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="87710-109">Remarks</span></span>  

 <span data-ttu-id="87710-110">Una vez que `ExitThread` se activa la devolución de llamada, el subproceso ya no aparecerá en las enumeraciones de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="87710-110">Once the `ExitThread` callback is fired, the thread will no longer appear in thread enumerations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87710-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="87710-111">Requirements</span></span>  

 <span data-ttu-id="87710-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87710-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87710-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="87710-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="87710-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87710-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87710-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87710-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87710-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="87710-116">See also</span></span>

- [<span data-ttu-id="87710-117">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="87710-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
