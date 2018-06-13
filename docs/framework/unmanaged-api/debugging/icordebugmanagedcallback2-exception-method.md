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
ms.openlocfilehash: faefff879142d66c4c596f1b30a25e349a4014b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421806"
---
# <a name="icordebugmanagedcallback2exception-method"></a><span data-ttu-id="e43ae-102">ICorDebugManagedCallback2::Exception (Método)</span><span class="sxs-lookup"><span data-stu-id="e43ae-102">ICorDebugManagedCallback2::Exception Method</span></span>
<span data-ttu-id="e43ae-103">Notifica al depurador que se ha iniciado una búsqueda de un controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="e43ae-103">Notifies the debugger that a search for an exception handler has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e43ae-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e43ae-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="e43ae-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e43ae-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="e43ae-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el subproceso en el que se produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="e43ae-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread on which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="e43ae-107">[in] Un puntero a un objeto ICorDebugThread que representa el subproceso en el que se produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="e43ae-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the exception was thrown.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="e43ae-108">[in] Un puntero a un objeto ICorDebugFrame que representa un marco, según lo determinado por la `dwEventType` parámetro.</span><span class="sxs-lookup"><span data-stu-id="e43ae-108">[in] A pointer to an ICorDebugFrame object that represents a frame, as determined by the `dwEventType` parameter.</span></span> <span data-ttu-id="e43ae-109">Para obtener más información, vea la tabla en la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="e43ae-109">For more information, see the table in the Remarks section.</span></span>  
  
 `nOffset`  
 <span data-ttu-id="e43ae-110">[in] Un entero que especifica un desplazamiento, según lo determinado por la `dwEventType` parámetro.</span><span class="sxs-lookup"><span data-stu-id="e43ae-110">[in] An integer that specifies an offset, as determined by the `dwEventType` parameter.</span></span> <span data-ttu-id="e43ae-111">Para obtener más información, vea la tabla en la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="e43ae-111">For more information, see the table in the Remarks section.</span></span>  
  
 `dwEventType`  
 <span data-ttu-id="e43ae-112">[in] Un valor de la enumeración CorDebugExceptionCallbackType que especifica el tipo de esta devolución de llamada de excepción.</span><span class="sxs-lookup"><span data-stu-id="e43ae-112">[in] A value of the CorDebugExceptionCallbackType enumeration that specifies the type of this exception callback.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e43ae-113">[in] Un valor de la [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) enumeración que especifica información adicional sobre la excepción</span><span class="sxs-lookup"><span data-stu-id="e43ae-113">[in] A value of the [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) enumeration that specifies additional information about the exception</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e43ae-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e43ae-114">Remarks</span></span>  
 <span data-ttu-id="e43ae-115">El `Exception` devolución de llamada se denomina en varios puntos durante la fase de búsqueda del proceso de control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="e43ae-115">The `Exception` callback is called at various points during the search phase of the exception-handling process.</span></span> <span data-ttu-id="e43ae-116">Es decir, puede llamar más de una vez mientras desenreda una excepción.</span><span class="sxs-lookup"><span data-stu-id="e43ae-116">That is, it can be called more than once while unwinding an exception.</span></span>  
  
 <span data-ttu-id="e43ae-117">La excepción que se está procesando se puede recuperar del objeto ICorDebugThread al que hace referencia el `pThread` parámetro.</span><span class="sxs-lookup"><span data-stu-id="e43ae-117">The exception being processed can be retrieved from the ICorDebugThread object referenced by the `pThread` parameter.</span></span>  
  
 <span data-ttu-id="e43ae-118">El marco determinado y el desplazamiento se determinan por la `dwEventType` parámetro como sigue:</span><span class="sxs-lookup"><span data-stu-id="e43ae-118">The particular frame and offset are determined by the `dwEventType` parameter as follows:</span></span>  
  
|<span data-ttu-id="e43ae-119">Valor de `dwEventType`</span><span class="sxs-lookup"><span data-stu-id="e43ae-119">Value of `dwEventType`</span></span>|<span data-ttu-id="e43ae-120">Valor de `pFrame`</span><span class="sxs-lookup"><span data-stu-id="e43ae-120">Value of `pFrame`</span></span>|<span data-ttu-id="e43ae-121">Valor de `nOffset`</span><span class="sxs-lookup"><span data-stu-id="e43ae-121">Value of `nOffset`</span></span>|  
|----------------------------|-----------------------|------------------------|  
|<span data-ttu-id="e43ae-122">DEBUG_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="e43ae-122">DEBUG_EXCEPTION_FIRST_CHANCE</span></span>|<span data-ttu-id="e43ae-123">El marco que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="e43ae-123">The frame that threw the exception.</span></span>|<span data-ttu-id="e43ae-124">El puntero de instrucción en el marco.</span><span class="sxs-lookup"><span data-stu-id="e43ae-124">The instruction pointer in the frame.</span></span>|  
|<span data-ttu-id="e43ae-125">DEBUG_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="e43ae-125">DEBUG_EXCEPTION_USER_FIRST_CHANCE</span></span>|<span data-ttu-id="e43ae-126">El marco de código de usuario más cercano al punto de la excepción generada.</span><span class="sxs-lookup"><span data-stu-id="e43ae-126">The user-code frame closest to the point of the thrown exception.</span></span>|<span data-ttu-id="e43ae-127">El puntero de instrucción en el marco.</span><span class="sxs-lookup"><span data-stu-id="e43ae-127">The instruction pointer in the frame.</span></span>|  
|<span data-ttu-id="e43ae-128">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="e43ae-128">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND</span></span>|<span data-ttu-id="e43ae-129">El marco que contiene el controlador catch.</span><span class="sxs-lookup"><span data-stu-id="e43ae-129">The frame that contains the catch handler.</span></span>|<span data-ttu-id="e43ae-130">El desplazamiento de lenguaje intermedio (MSIL) de Microsoft del principio del controlador catch.</span><span class="sxs-lookup"><span data-stu-id="e43ae-130">The Microsoft intermediate language (MSIL) offset of the beginning of the catch handler.</span></span>|  
|<span data-ttu-id="e43ae-131">DEBUG_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="e43ae-131">DEBUG_EXCEPTION_UNHANDLED</span></span>|<span data-ttu-id="e43ae-132">NULL</span><span class="sxs-lookup"><span data-stu-id="e43ae-132">NULL</span></span>|<span data-ttu-id="e43ae-133">Sin definir.</span><span class="sxs-lookup"><span data-stu-id="e43ae-133">Undefined.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e43ae-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e43ae-134">Requirements</span></span>  
 <span data-ttu-id="e43ae-135">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e43ae-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e43ae-136">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e43ae-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e43ae-137">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e43ae-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e43ae-138">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e43ae-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e43ae-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="e43ae-139">See Also</span></span>  
 [<span data-ttu-id="e43ae-140">ICorDebugManagedCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e43ae-140">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="e43ae-141">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e43ae-141">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
