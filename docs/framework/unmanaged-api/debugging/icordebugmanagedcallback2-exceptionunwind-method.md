---
title: "ICorDebugManagedCallback2::ExceptionUnwind (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugManagedCallback2.ExceptionUnwind
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::ExceptionUnwind
helpviewer_keywords:
- ICorDebugManagedCallback2::ExceptionUnwind method [.NET Framework debugging]
- ExceptionUnwind method [.NET Framework debugging]
ms.assetid: aaf5938d-179c-4eaa-8d35-8523a4fadded
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 64b85311f625e39dd25c48a60dde2fbaf66a957f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallback2exceptionunwind-method"></a><span data-ttu-id="ec690-102">ICorDebugManagedCallback2::ExceptionUnwind (Método)</span><span class="sxs-lookup"><span data-stu-id="ec690-102">ICorDebugManagedCallback2::ExceptionUnwind Method</span></span>
<span data-ttu-id="ec690-103">Proporciona una notificación de estado durante el proceso de desenredo de la excepción.</span><span class="sxs-lookup"><span data-stu-id="ec690-103">Provides a status notification during the exception unwinding process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec690-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ec690-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwind (  
    [in] ICorDebugAppDomain                  *pAppDomain,  
    [in] ICorDebugThread                     *pThread,  
    [in] CorDebugExceptionUnwindCallbackType  dwEventType,  
    [in] DWORD                                dwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ec690-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ec690-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="ec690-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el subproceso en el que se produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="ec690-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread on which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="ec690-107">[in] Un puntero a un objeto ICorDebugThread que representa el subproceso en el que se produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="ec690-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the exception was thrown.</span></span>  
  
 `dwEventType`  
 <span data-ttu-id="ec690-108">[in] Un valor de la enumeración CorDebugExceptionUnwindCallbackType que especifica el evento que está siendo señalado por la devolución de llamada durante la fase de desenredo.</span><span class="sxs-lookup"><span data-stu-id="ec690-108">[in] A value of the CorDebugExceptionUnwindCallbackType enumeration that specifies the event that is being signaled by the callback during the unwind phase.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="ec690-109">[in] Un valor de la [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) enumeración que especifica información adicional sobre la excepción.</span><span class="sxs-lookup"><span data-stu-id="ec690-109">[in] A value of the [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) enumeration that specifies additional information about the exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec690-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ec690-110">Remarks</span></span>  
 <span data-ttu-id="ec690-111">`ExceptionUnwind`se llama en varios puntos durante la fase de desenredo del proceso de control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="ec690-111">`ExceptionUnwind` is called at various points during the unwind phase of the exception-handling process.</span></span> <span data-ttu-id="ec690-112">`ExceptionUnwind`se puede llamar varias veces mientras se desenreda una sola excepción.</span><span class="sxs-lookup"><span data-stu-id="ec690-112">`ExceptionUnwind` can be called more than once while unwinding a single exception.</span></span>  
  
 <span data-ttu-id="ec690-113">Si `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, el puntero de instrucción estará en el marco de hoja del subproceso, desde el punto de secuencia anterior (pueden ser varias instrucciones antes) la instrucción que ha provocado la excepción.</span><span class="sxs-lookup"><span data-stu-id="ec690-113">If `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, the instruction pointer will be in the leaf frame of the thread, at the sequence point before (this may be several instructions before) the instruction that led to the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec690-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ec690-114">Requirements</span></span>  
 <span data-ttu-id="ec690-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec690-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec690-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ec690-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ec690-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec690-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec690-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec690-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec690-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec690-119">See Also</span></span>  
 [<span data-ttu-id="ec690-120">ICorDebugManagedCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ec690-120">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="ec690-121">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ec690-121">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
