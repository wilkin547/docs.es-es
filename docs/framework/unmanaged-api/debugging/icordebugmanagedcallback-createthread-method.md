---
description: 'Más información acerca de: ICorDebugManagedCallback:: CreateThread (método)'
title: ICorDebugManagedCallback::CreateThread (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.CreateThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateThread method
helpviewer_keywords:
- ICorDebugManagedCallback::CreateThread method [.NET Framework debugging]
- CreateThread method [.NET Framework debugging]
ms.assetid: 6b961728-21c4-4e8d-ae81-197458be62f4
topic_type:
- apiref
ms.openlocfilehash: 20d5ce9da34e7082502252eeece2ab34b1f2e902
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791039"
---
# <a name="icordebugmanagedcallbackcreatethread-method"></a><span data-ttu-id="28955-103">ICorDebugManagedCallback::CreateThread (Método)</span><span class="sxs-lookup"><span data-stu-id="28955-103">ICorDebugManagedCallback::CreateThread Method</span></span>

<span data-ttu-id="28955-104">Notifica al depurador que un subproceso ha empezado a ejecutar código administrado.</span><span class="sxs-lookup"><span data-stu-id="28955-104">Notifies the debugger that a thread has started executing managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28955-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="28955-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28955-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="28955-106">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="28955-107">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el subproceso.</span><span class="sxs-lookup"><span data-stu-id="28955-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="28955-108">de Un puntero a un objeto ICorDebugThread que representa el subproceso.</span><span class="sxs-lookup"><span data-stu-id="28955-108">[in] A pointer to an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28955-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="28955-109">Remarks</span></span>  

 <span data-ttu-id="28955-110">El subproceso se colocará en la primera instrucción de código administrado que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="28955-110">The thread will be positioned at the first managed code instruction to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28955-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="28955-111">Requirements</span></span>  

 <span data-ttu-id="28955-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28955-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28955-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="28955-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="28955-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28955-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28955-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28955-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28955-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="28955-116">See also</span></span>

- [<span data-ttu-id="28955-117">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="28955-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
