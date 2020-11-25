---
title: ICorDebugManagedCallback::Exception (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Exception
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Exception
helpviewer_keywords:
- Exception method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::Exception method [.NET Framework debugging]
ms.assetid: ab18a509-dff3-4930-b585-bd15e0414176
topic_type:
- apiref
ms.openlocfilehash: 05fed13a556cbcc3b8362e41d73c2b659b1e5eeb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731792"
---
# <a name="icordebugmanagedcallbackexception-method"></a><span data-ttu-id="046d1-102">ICorDebugManagedCallback::Exception (Método)</span><span class="sxs-lookup"><span data-stu-id="046d1-102">ICorDebugManagedCallback::Exception Method</span></span>

<span data-ttu-id="046d1-103">Notifica al depurador que se ha producido una excepción del código administrado.</span><span class="sxs-lookup"><span data-stu-id="046d1-103">Notifies the debugger that an exception has been thrown from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="046d1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="046d1-104">Syntax</span></span>  
  
```cpp  
HRESULT Exception (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] BOOL                unhandled  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="046d1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="046d1-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="046d1-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación en el que se produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="046d1-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="046d1-107">de Un puntero a un objeto ICorDebugThread que representa el subproceso en el que se produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="046d1-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the exception was thrown.</span></span>  
  
 `unhandled`  
 <span data-ttu-id="046d1-108">de Si este valor es `false` , la aplicación todavía no ha procesado la excepción; de lo contrario, la excepción no se controla y finalizará el proceso.</span><span class="sxs-lookup"><span data-stu-id="046d1-108">[in] If this value is `false`, the exception has not yet been processed by the application; otherwise, the exception is unhandled and will terminate the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="046d1-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="046d1-109">Remarks</span></span>  

 <span data-ttu-id="046d1-110">La excepción específica se puede recuperar del objeto de subproceso.</span><span class="sxs-lookup"><span data-stu-id="046d1-110">The specific exception can be retrieved from the thread object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="046d1-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="046d1-111">Requirements</span></span>  

 <span data-ttu-id="046d1-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="046d1-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="046d1-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="046d1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="046d1-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="046d1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="046d1-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="046d1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="046d1-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="046d1-116">See also</span></span>

- [<span data-ttu-id="046d1-117">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="046d1-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
