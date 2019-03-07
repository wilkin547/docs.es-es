---
title: ICorDebugManagedCallback2::Exception (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.Exception
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::Exception
helpviewer_keywords:
- ICorDebugManagedCallback2::Exception method [.NET Framework debugging]
- Exception method, ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: 78b0f14f-2fae-4e63-8412-4df119ee8468
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1f776f20f163df91d65509e5dbab31fe9c29a965
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492106"
---
# <a name="icordebugmanagedcallback2exception-method"></a><span data-ttu-id="ab825-102">ICorDebugManagedCallback2::Exception (Método)</span><span class="sxs-lookup"><span data-stu-id="ab825-102">ICorDebugManagedCallback2::Exception Method</span></span>
<span data-ttu-id="ab825-103">Notifica al depurador que se ha iniciado una búsqueda de un controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="ab825-103">Notifies the debugger that a search for an exception handler has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab825-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ab825-104">Syntax</span></span>  
  
```  
HRESULT Exception (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFrame       *pFrame,  
    [in] ULONG32              nOffset,  
    [in] CorDebugExceptionCallbackType dwEventType,  
    [in] DWORD                dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab825-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ab825-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="ab825-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el subproceso en el que se produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="ab825-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread on which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="ab825-107">[in] Un puntero a un objeto ICorDebugThread que representa el subproceso en el que se produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="ab825-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the exception was thrown.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="ab825-108">[in] Un puntero a un objeto ICorDebugFrame que representa un marco, según lo determinado por la `dwEventType` parámetro.</span><span class="sxs-lookup"><span data-stu-id="ab825-108">[in] A pointer to an ICorDebugFrame object that represents a frame, as determined by the `dwEventType` parameter.</span></span> <span data-ttu-id="ab825-109">Para obtener más información, vea la tabla en la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="ab825-109">For more information, see the table in the Remarks section.</span></span>  
  
 `nOffset`  
 <span data-ttu-id="ab825-110">[in] Un entero que especifica un desplazamiento, según lo determinado por la `dwEventType` parámetro.</span><span class="sxs-lookup"><span data-stu-id="ab825-110">[in] An integer that specifies an offset, as determined by the `dwEventType` parameter.</span></span> <span data-ttu-id="ab825-111">Para obtener más información, vea la tabla en la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="ab825-111">For more information, see the table in the Remarks section.</span></span>  
  
 `dwEventType`  
 <span data-ttu-id="ab825-112">[in] Un valor de la enumeración CorDebugExceptionCallbackType que especifica el tipo de devolución de llamada de esta excepción.</span><span class="sxs-lookup"><span data-stu-id="ab825-112">[in] A value of the CorDebugExceptionCallbackType enumeration that specifies the type of this exception callback.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="ab825-113">[in] Un valor de la [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) enumeración que especifica información adicional sobre la excepción</span><span class="sxs-lookup"><span data-stu-id="ab825-113">[in] A value of the [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) enumeration that specifies additional information about the exception</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab825-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ab825-114">Remarks</span></span>  
 <span data-ttu-id="ab825-115">El `Exception` devolución de llamada se llama en varios puntos durante la fase de búsqueda del proceso de control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="ab825-115">The `Exception` callback is called at various points during the search phase of the exception-handling process.</span></span> <span data-ttu-id="ab825-116">Es decir, puede llamar más de una vez mientras desenredar una excepción.</span><span class="sxs-lookup"><span data-stu-id="ab825-116">That is, it can be called more than once while unwinding an exception.</span></span>  
  
 <span data-ttu-id="ab825-117">La excepción que se está procesando se puede recuperar desde el objeto ICorDebugThread al que hace referencia el `pThread` parámetro.</span><span class="sxs-lookup"><span data-stu-id="ab825-117">The exception being processed can be retrieved from the ICorDebugThread object referenced by the `pThread` parameter.</span></span>  
  
 <span data-ttu-id="ab825-118">El marco determinado y el desplazamiento se determinan por la `dwEventType` parámetro como sigue:</span><span class="sxs-lookup"><span data-stu-id="ab825-118">The particular frame and offset are determined by the `dwEventType` parameter as follows:</span></span>  
  
|<span data-ttu-id="ab825-119">Valor de `dwEventType`</span><span class="sxs-lookup"><span data-stu-id="ab825-119">Value of `dwEventType`</span></span>|<span data-ttu-id="ab825-120">Valor de `pFrame`</span><span class="sxs-lookup"><span data-stu-id="ab825-120">Value of `pFrame`</span></span>|<span data-ttu-id="ab825-121">Valor de `nOffset`</span><span class="sxs-lookup"><span data-stu-id="ab825-121">Value of `nOffset`</span></span>|  
|----------------------------|-----------------------|------------------------|  
|<span data-ttu-id="ab825-122">DEBUG_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="ab825-122">DEBUG_EXCEPTION_FIRST_CHANCE</span></span>|<span data-ttu-id="ab825-123">El marco que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="ab825-123">The frame that threw the exception.</span></span>|<span data-ttu-id="ab825-124">El puntero de instrucción en el marco.</span><span class="sxs-lookup"><span data-stu-id="ab825-124">The instruction pointer in the frame.</span></span>|  
|<span data-ttu-id="ab825-125">DEBUG_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="ab825-125">DEBUG_EXCEPTION_USER_FIRST_CHANCE</span></span>|<span data-ttu-id="ab825-126">El marco de código de usuario más cercano al punto de la excepción generada.</span><span class="sxs-lookup"><span data-stu-id="ab825-126">The user-code frame closest to the point of the thrown exception.</span></span>|<span data-ttu-id="ab825-127">El puntero de instrucción en el marco.</span><span class="sxs-lookup"><span data-stu-id="ab825-127">The instruction pointer in the frame.</span></span>|  
|<span data-ttu-id="ab825-128">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="ab825-128">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND</span></span>|<span data-ttu-id="ab825-129">El marco que contiene el controlador catch.</span><span class="sxs-lookup"><span data-stu-id="ab825-129">The frame that contains the catch handler.</span></span>|<span data-ttu-id="ab825-130">El desplazamiento de lenguaje intermedio (MSIL) de Microsoft del principio de que el controlador catch.</span><span class="sxs-lookup"><span data-stu-id="ab825-130">The Microsoft intermediate language (MSIL) offset of the beginning of the catch handler.</span></span>|  
|<span data-ttu-id="ab825-131">DEBUG_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="ab825-131">DEBUG_EXCEPTION_UNHANDLED</span></span>|<span data-ttu-id="ab825-132">NULL</span><span class="sxs-lookup"><span data-stu-id="ab825-132">NULL</span></span>|<span data-ttu-id="ab825-133">Sin definir.</span><span class="sxs-lookup"><span data-stu-id="ab825-133">Undefined.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ab825-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ab825-134">Requirements</span></span>  
 <span data-ttu-id="ab825-135">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab825-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab825-136">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ab825-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab825-137">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab825-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab825-138">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab825-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab825-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab825-139">See also</span></span>
- [<span data-ttu-id="ab825-140">ICorDebugManagedCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ab825-140">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="ab825-141">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ab825-141">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
