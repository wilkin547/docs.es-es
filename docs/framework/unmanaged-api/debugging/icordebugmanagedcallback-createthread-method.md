---
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
ms.openlocfilehash: 5fa3bafd35912a7729833896f7e6f0bb2ff9b121
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212391"
---
# <a name="icordebugmanagedcallbackcreatethread-method"></a><span data-ttu-id="602fb-102">ICorDebugManagedCallback::CreateThread (Método)</span><span class="sxs-lookup"><span data-stu-id="602fb-102">ICorDebugManagedCallback::CreateThread Method</span></span>
<span data-ttu-id="602fb-103">Notifica al depurador que un subproceso ha empezado a ejecutar código administrado.</span><span class="sxs-lookup"><span data-stu-id="602fb-103">Notifies the debugger that a thread has started executing managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="602fb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="602fb-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="602fb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="602fb-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="602fb-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el subproceso.</span><span class="sxs-lookup"><span data-stu-id="602fb-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="602fb-107">de Un puntero a un objeto ICorDebugThread que representa el subproceso.</span><span class="sxs-lookup"><span data-stu-id="602fb-107">[in] A pointer to an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="602fb-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="602fb-108">Remarks</span></span>  
 <span data-ttu-id="602fb-109">El subproceso se colocará en la primera instrucción de código administrado que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="602fb-109">The thread will be positioned at the first managed code instruction to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="602fb-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="602fb-110">Requirements</span></span>  
 <span data-ttu-id="602fb-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="602fb-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="602fb-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="602fb-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="602fb-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="602fb-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="602fb-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="602fb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="602fb-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="602fb-115">See also</span></span>

- [<span data-ttu-id="602fb-116">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="602fb-116">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
