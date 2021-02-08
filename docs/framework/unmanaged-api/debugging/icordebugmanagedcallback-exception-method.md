---
description: 'Más información acerca de: ICorDebugManagedCallback:: Exception (método)'
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
ms.openlocfilehash: f738c328e1f6edfeb61a1d5e2ba8f9dd827d05dd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790976"
---
# <a name="icordebugmanagedcallbackexception-method"></a><span data-ttu-id="91a46-103">ICorDebugManagedCallback::Exception (Método)</span><span class="sxs-lookup"><span data-stu-id="91a46-103">ICorDebugManagedCallback::Exception Method</span></span>

<span data-ttu-id="91a46-104">Notifica al depurador que se ha producido una excepción del código administrado.</span><span class="sxs-lookup"><span data-stu-id="91a46-104">Notifies the debugger that an exception has been thrown from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91a46-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="91a46-105">Syntax</span></span>  
  
```cpp  
HRESULT Exception (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] BOOL                unhandled  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91a46-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="91a46-106">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="91a46-107">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación en el que se produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="91a46-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="91a46-108">de Un puntero a un objeto ICorDebugThread que representa el subproceso en el que se produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="91a46-108">[in] A pointer to an ICorDebugThread object that represents the thread in which the exception was thrown.</span></span>  
  
 `unhandled`  
 <span data-ttu-id="91a46-109">de Si este valor es `false` , la aplicación todavía no ha procesado la excepción; de lo contrario, la excepción no se controla y finalizará el proceso.</span><span class="sxs-lookup"><span data-stu-id="91a46-109">[in] If this value is `false`, the exception has not yet been processed by the application; otherwise, the exception is unhandled and will terminate the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91a46-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="91a46-110">Remarks</span></span>  

 <span data-ttu-id="91a46-111">La excepción específica se puede recuperar del objeto de subproceso.</span><span class="sxs-lookup"><span data-stu-id="91a46-111">The specific exception can be retrieved from the thread object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91a46-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="91a46-112">Requirements</span></span>  

 <span data-ttu-id="91a46-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91a46-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91a46-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="91a46-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="91a46-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91a46-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91a46-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91a46-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91a46-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="91a46-117">See also</span></span>

- [<span data-ttu-id="91a46-118">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="91a46-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
