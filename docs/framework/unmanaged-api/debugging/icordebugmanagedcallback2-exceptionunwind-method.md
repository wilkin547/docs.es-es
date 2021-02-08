---
description: 'Más información sobre: ICorDebugManagedCallback2:: ExceptionUnwind ((método)'
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
ms.openlocfilehash: 2d98fb21cdbb0db25a11761ac9b00e99e1526cc0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790856"
---
# <a name="icordebugmanagedcallback2exceptionunwind-method"></a><span data-ttu-id="ef318-103">ICorDebugManagedCallback2::ExceptionUnwind (Método)</span><span class="sxs-lookup"><span data-stu-id="ef318-103">ICorDebugManagedCallback2::ExceptionUnwind Method</span></span>

<span data-ttu-id="ef318-104">Proporciona una notificación de estado durante el proceso de desenredo de excepciones.</span><span class="sxs-lookup"><span data-stu-id="ef318-104">Provides a status notification during the exception unwinding process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef318-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef318-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwind (  
    [in] ICorDebugAppDomain                  *pAppDomain,  
    [in] ICorDebugThread                     *pThread,  
    [in] CorDebugExceptionUnwindCallbackType  dwEventType,  
    [in] DWORD                                dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef318-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ef318-106">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="ef318-107">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el subproceso en el que se produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="ef318-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread on which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="ef318-108">de Un puntero a un objeto ICorDebugThread que representa el subproceso en el que se produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="ef318-108">[in] A pointer to an ICorDebugThread object that represents the thread on which the exception was thrown.</span></span>  
  
 `dwEventType`  
 <span data-ttu-id="ef318-109">de Un valor de la enumeración CorDebugExceptionUnwindCallbackType (que especifica el evento que la devolución de llamada señala durante la fase de desenredado.</span><span class="sxs-lookup"><span data-stu-id="ef318-109">[in] A value of the CorDebugExceptionUnwindCallbackType enumeration that specifies the event that is being signaled by the callback during the unwind phase.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="ef318-110">de Un valor de la enumeración [cordebugexceptionflags (](cordebugexceptionflags-enumeration.md) que especifica información adicional sobre la excepción.</span><span class="sxs-lookup"><span data-stu-id="ef318-110">[in] A value of the [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) enumeration that specifies additional information about the exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef318-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ef318-111">Remarks</span></span>  

 <span data-ttu-id="ef318-112">`ExceptionUnwind` se llama a en varios puntos durante la fase de desenredado del proceso de control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="ef318-112">`ExceptionUnwind` is called at various points during the unwind phase of the exception-handling process.</span></span> <span data-ttu-id="ef318-113">`ExceptionUnwind` se puede llamar más de una vez al desenredar una sola excepción.</span><span class="sxs-lookup"><span data-stu-id="ef318-113">`ExceptionUnwind` can be called more than once while unwinding a single exception.</span></span>  
  
 <span data-ttu-id="ef318-114">Si `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, el puntero de instrucción estará en el marco hoja del subproceso, en el punto de secuencia anterior (puede haber varias instrucciones antes) de la instrucción que condujo a la excepción.</span><span class="sxs-lookup"><span data-stu-id="ef318-114">If `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, the instruction pointer will be in the leaf frame of the thread, at the sequence point before (this may be several instructions before) the instruction that led to the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef318-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ef318-115">Requirements</span></span>  

 <span data-ttu-id="ef318-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef318-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef318-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ef318-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ef318-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef318-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef318-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef318-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef318-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef318-120">See also</span></span>

- [<span data-ttu-id="ef318-121">ICorDebugManagedCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ef318-121">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="ef318-122">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ef318-122">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
