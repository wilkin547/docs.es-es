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
ms.openlocfilehash: 2d0461709accf1a9300c072b62bd58734cb33fb8
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209818"
---
# <a name="icordebugmanagedcallbackexception-method"></a><span data-ttu-id="d817b-102">ICorDebugManagedCallback::Exception (Método)</span><span class="sxs-lookup"><span data-stu-id="d817b-102">ICorDebugManagedCallback::Exception Method</span></span>
<span data-ttu-id="d817b-103">Notifica al depurador que se ha producido una excepción del código administrado.</span><span class="sxs-lookup"><span data-stu-id="d817b-103">Notifies the debugger that an exception has been thrown from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d817b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d817b-104">Syntax</span></span>  
  
```cpp  
HRESULT Exception (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] BOOL                unhandled  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d817b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d817b-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="d817b-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación en el que se produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="d817b-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="d817b-107">de Un puntero a un objeto ICorDebugThread que representa el subproceso en el que se produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="d817b-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the exception was thrown.</span></span>  
  
 `unhandled`  
 <span data-ttu-id="d817b-108">de Si este valor es `false` , la aplicación todavía no ha procesado la excepción; de lo contrario, la excepción no se controla y finalizará el proceso.</span><span class="sxs-lookup"><span data-stu-id="d817b-108">[in] If this value is `false`, the exception has not yet been processed by the application; otherwise, the exception is unhandled and will terminate the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d817b-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d817b-109">Remarks</span></span>  
 <span data-ttu-id="d817b-110">La excepción específica se puede recuperar del objeto de subproceso.</span><span class="sxs-lookup"><span data-stu-id="d817b-110">The specific exception can be retrieved from the thread object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d817b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d817b-111">Requirements</span></span>  
 <span data-ttu-id="d817b-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d817b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d817b-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d817b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d817b-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d817b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d817b-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d817b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d817b-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d817b-116">See also</span></span>

- [<span data-ttu-id="d817b-117">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d817b-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
