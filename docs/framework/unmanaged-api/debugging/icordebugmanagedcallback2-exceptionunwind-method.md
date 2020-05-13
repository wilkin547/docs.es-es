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
ms.openlocfilehash: 8f66369d3ac5ddcfe38fe579cac728eb3a250165
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205624"
---
# <a name="icordebugmanagedcallback2exceptionunwind-method"></a><span data-ttu-id="5d014-102">ICorDebugManagedCallback2::ExceptionUnwind (Método)</span><span class="sxs-lookup"><span data-stu-id="5d014-102">ICorDebugManagedCallback2::ExceptionUnwind Method</span></span>
<span data-ttu-id="5d014-103">Proporciona una notificación de estado durante el proceso de desenredo de excepciones.</span><span class="sxs-lookup"><span data-stu-id="5d014-103">Provides a status notification during the exception unwinding process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d014-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d014-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwind (  
    [in] ICorDebugAppDomain                  *pAppDomain,  
    [in] ICorDebugThread                     *pThread,  
    [in] CorDebugExceptionUnwindCallbackType  dwEventType,  
    [in] DWORD                                dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d014-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5d014-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="5d014-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el subproceso en el que se produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="5d014-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread on which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="5d014-107">de Un puntero a un objeto ICorDebugThread que representa el subproceso en el que se produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="5d014-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the exception was thrown.</span></span>  
  
 `dwEventType`  
 <span data-ttu-id="5d014-108">de Un valor de la enumeración CorDebugExceptionUnwindCallbackType (que especifica el evento que la devolución de llamada señala durante la fase de desenredado.</span><span class="sxs-lookup"><span data-stu-id="5d014-108">[in] A value of the CorDebugExceptionUnwindCallbackType enumeration that specifies the event that is being signaled by the callback during the unwind phase.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="5d014-109">de Un valor de la enumeración [cordebugexceptionflags (](cordebugexceptionflags-enumeration.md) que especifica información adicional sobre la excepción.</span><span class="sxs-lookup"><span data-stu-id="5d014-109">[in] A value of the [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) enumeration that specifies additional information about the exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d014-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5d014-110">Remarks</span></span>  
 <span data-ttu-id="5d014-111">`ExceptionUnwind`se llama a en varios puntos durante la fase de desenredado del proceso de control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="5d014-111">`ExceptionUnwind` is called at various points during the unwind phase of the exception-handling process.</span></span> <span data-ttu-id="5d014-112">`ExceptionUnwind`se puede llamar más de una vez al desenredar una sola excepción.</span><span class="sxs-lookup"><span data-stu-id="5d014-112">`ExceptionUnwind` can be called more than once while unwinding a single exception.</span></span>  
  
 <span data-ttu-id="5d014-113">Si `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, el puntero de instrucción estará en el marco hoja del subproceso, en el punto de secuencia anterior (puede haber varias instrucciones antes) de la instrucción que condujo a la excepción.</span><span class="sxs-lookup"><span data-stu-id="5d014-113">If `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, the instruction pointer will be in the leaf frame of the thread, at the sequence point before (this may be several instructions before) the instruction that led to the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d014-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5d014-114">Requirements</span></span>  
 <span data-ttu-id="5d014-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d014-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d014-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5d014-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d014-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d014-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d014-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d014-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d014-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5d014-119">See also</span></span>

- [<span data-ttu-id="5d014-120">ICorDebugManagedCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5d014-120">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="5d014-121">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5d014-121">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
