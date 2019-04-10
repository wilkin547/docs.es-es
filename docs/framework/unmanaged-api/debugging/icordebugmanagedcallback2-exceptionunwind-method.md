---
title: ICorDebugManagedCallback2::ExceptionUnwind (Método)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: faba9631e85ac84ff1517b64e9a3f5567ee7c9dc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59214800"
---
# <a name="icordebugmanagedcallback2exceptionunwind-method"></a><span data-ttu-id="fb499-102">ICorDebugManagedCallback2::ExceptionUnwind (Método)</span><span class="sxs-lookup"><span data-stu-id="fb499-102">ICorDebugManagedCallback2::ExceptionUnwind Method</span></span>
<span data-ttu-id="fb499-103">Proporciona una notificación de estado durante el proceso de desenredo de excepciones.</span><span class="sxs-lookup"><span data-stu-id="fb499-103">Provides a status notification during the exception unwinding process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb499-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fb499-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwind (  
    [in] ICorDebugAppDomain                  *pAppDomain,  
    [in] ICorDebugThread                     *pThread,  
    [in] CorDebugExceptionUnwindCallbackType  dwEventType,  
    [in] DWORD                                dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb499-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fb499-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="fb499-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el subproceso en el que se produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="fb499-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread on which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="fb499-107">[in] Un puntero a un objeto ICorDebugThread que representa el subproceso en el que se produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="fb499-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the exception was thrown.</span></span>  
  
 `dwEventType`  
 <span data-ttu-id="fb499-108">[in] Un valor de la enumeración CorDebugExceptionUnwindCallbackType que especifica el evento que está siendo señalado por la devolución de llamada durante la fase de desenredo.</span><span class="sxs-lookup"><span data-stu-id="fb499-108">[in] A value of the CorDebugExceptionUnwindCallbackType enumeration that specifies the event that is being signaled by the callback during the unwind phase.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="fb499-109">[in] Un valor de la [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) enumeración que especifica información adicional sobre la excepción.</span><span class="sxs-lookup"><span data-stu-id="fb499-109">[in] A value of the [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) enumeration that specifies additional information about the exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb499-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fb499-110">Remarks</span></span>  
 `ExceptionUnwind` <span data-ttu-id="fb499-111">se llama en varios puntos durante la fase de desenredo del proceso de control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="fb499-111">is called at various points during the unwind phase of the exception-handling process.</span></span> `ExceptionUnwind` <span data-ttu-id="fb499-112">puede llamarse varias veces mientras se desenreda una excepción.</span><span class="sxs-lookup"><span data-stu-id="fb499-112">can be called more than once while unwinding a single exception.</span></span>  
  
 <span data-ttu-id="fb499-113">Si `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, el puntero de instrucción estará en el marco de hoja del subproceso, desde el punto de secuencia anterior (puede ser varias instrucciones antes) la instrucción que produjeron la excepción.</span><span class="sxs-lookup"><span data-stu-id="fb499-113">If `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, the instruction pointer will be in the leaf frame of the thread, at the sequence point before (this may be several instructions before) the instruction that led to the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb499-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fb499-114">Requirements</span></span>  
 <span data-ttu-id="fb499-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb499-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb499-116">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fb499-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fb499-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb499-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="fb499-118">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="fb499-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fb499-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb499-119">See also</span></span>

- [<span data-ttu-id="fb499-120">ICorDebugManagedCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fb499-120">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="fb499-121">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fb499-121">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
