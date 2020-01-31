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
ms.openlocfilehash: e7125d923fb1d3757bb4ca53f5a7db806b241dd9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781526"
---
# <a name="icordebugmanagedcallback2exception-method"></a><span data-ttu-id="303e8-102">ICorDebugManagedCallback2::Exception (Método)</span><span class="sxs-lookup"><span data-stu-id="303e8-102">ICorDebugManagedCallback2::Exception Method</span></span>
<span data-ttu-id="303e8-103">Notifica al depurador que se ha iniciado una búsqueda de un controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="303e8-103">Notifies the debugger that a search for an exception handler has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="303e8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="303e8-104">Syntax</span></span>  
  
```cpp  
HRESULT Exception (  
    [in] ICorDebugAppDomain   *pAppDomain,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugFrame       *pFrame,  
    [in] ULONG32              nOffset,  
    [in] CorDebugExceptionCallbackType dwEventType,  
    [in] DWORD                dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="303e8-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="303e8-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="303e8-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el subproceso en el que se produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="303e8-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread on which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="303e8-107">de Un puntero a un objeto ICorDebugThread que representa el subproceso en el que se produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="303e8-107">[in] A pointer to an ICorDebugThread object that represents the thread on which the exception was thrown.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="303e8-108">de Un puntero a un objeto ICorDebugFrame que representa un marco, determinado por el parámetro `dwEventType`.</span><span class="sxs-lookup"><span data-stu-id="303e8-108">[in] A pointer to an ICorDebugFrame object that represents a frame, as determined by the `dwEventType` parameter.</span></span> <span data-ttu-id="303e8-109">Para obtener más información, vea la tabla de la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="303e8-109">For more information, see the table in the Remarks section.</span></span>  
  
 `nOffset`  
 <span data-ttu-id="303e8-110">de Un entero que especifica un desplazamiento, según lo determinado por el parámetro `dwEventType`.</span><span class="sxs-lookup"><span data-stu-id="303e8-110">[in] An integer that specifies an offset, as determined by the `dwEventType` parameter.</span></span> <span data-ttu-id="303e8-111">Para obtener más información, vea la tabla de la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="303e8-111">For more information, see the table in the Remarks section.</span></span>  
  
 `dwEventType`  
 <span data-ttu-id="303e8-112">de Valor de la enumeración Cordebugexceptioncallbacktype (que especifica el tipo de esta devolución de llamada de excepción.</span><span class="sxs-lookup"><span data-stu-id="303e8-112">[in] A value of the CorDebugExceptionCallbackType enumeration that specifies the type of this exception callback.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="303e8-113">de Un valor de la enumeración [cordebugexceptionflags (](cordebugexceptionflags-enumeration.md) que especifica información adicional sobre la excepción.</span><span class="sxs-lookup"><span data-stu-id="303e8-113">[in] A value of the [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) enumeration that specifies additional information about the exception</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="303e8-114">Notas</span><span class="sxs-lookup"><span data-stu-id="303e8-114">Remarks</span></span>  
 <span data-ttu-id="303e8-115">La devolución de llamada de `Exception` se llama en varios puntos durante la fase de búsqueda del proceso de control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="303e8-115">The `Exception` callback is called at various points during the search phase of the exception-handling process.</span></span> <span data-ttu-id="303e8-116">Es decir, se puede llamar más de una vez al desenredar una excepción.</span><span class="sxs-lookup"><span data-stu-id="303e8-116">That is, it can be called more than once while unwinding an exception.</span></span>  
  
 <span data-ttu-id="303e8-117">La excepción que se está procesando se puede recuperar desde el objeto ICorDebugThread al que hace referencia el parámetro `pThread`.</span><span class="sxs-lookup"><span data-stu-id="303e8-117">The exception being processed can be retrieved from the ICorDebugThread object referenced by the `pThread` parameter.</span></span>  
  
 <span data-ttu-id="303e8-118">El determinado marco y desplazamiento vienen determinados por el parámetro `dwEventType` como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="303e8-118">The particular frame and offset are determined by the `dwEventType` parameter as follows:</span></span>  
  
|<span data-ttu-id="303e8-119">Valor de `dwEventType`</span><span class="sxs-lookup"><span data-stu-id="303e8-119">Value of `dwEventType`</span></span>|<span data-ttu-id="303e8-120">Valor de `pFrame`</span><span class="sxs-lookup"><span data-stu-id="303e8-120">Value of `pFrame`</span></span>|<span data-ttu-id="303e8-121">Valor de `nOffset`</span><span class="sxs-lookup"><span data-stu-id="303e8-121">Value of `nOffset`</span></span>|  
|----------------------------|-----------------------|------------------------|  
|<span data-ttu-id="303e8-122">DEBUG_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="303e8-122">DEBUG_EXCEPTION_FIRST_CHANCE</span></span>|<span data-ttu-id="303e8-123">Marco que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="303e8-123">The frame that threw the exception.</span></span>|<span data-ttu-id="303e8-124">Puntero de instrucción en el marco.</span><span class="sxs-lookup"><span data-stu-id="303e8-124">The instruction pointer in the frame.</span></span>|  
|<span data-ttu-id="303e8-125">DEBUG_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="303e8-125">DEBUG_EXCEPTION_USER_FIRST_CHANCE</span></span>|<span data-ttu-id="303e8-126">Marco de código de usuario más cercano al punto de la excepción iniciada.</span><span class="sxs-lookup"><span data-stu-id="303e8-126">The user-code frame closest to the point of the thrown exception.</span></span>|<span data-ttu-id="303e8-127">Puntero de instrucción en el marco.</span><span class="sxs-lookup"><span data-stu-id="303e8-127">The instruction pointer in the frame.</span></span>|  
|<span data-ttu-id="303e8-128">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="303e8-128">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND</span></span>|<span data-ttu-id="303e8-129">Marco que contiene el controlador Catch.</span><span class="sxs-lookup"><span data-stu-id="303e8-129">The frame that contains the catch handler.</span></span>|<span data-ttu-id="303e8-130">Desplazamiento del lenguaje intermedio de Microsoft (MSIL) del principio del controlador Catch.</span><span class="sxs-lookup"><span data-stu-id="303e8-130">The Microsoft intermediate language (MSIL) offset of the beginning of the catch handler.</span></span>|  
|<span data-ttu-id="303e8-131">DEBUG_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="303e8-131">DEBUG_EXCEPTION_UNHANDLED</span></span>|<span data-ttu-id="303e8-132">NULL</span><span class="sxs-lookup"><span data-stu-id="303e8-132">NULL</span></span>|<span data-ttu-id="303e8-133">Indefinido.</span><span class="sxs-lookup"><span data-stu-id="303e8-133">Undefined.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="303e8-134">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="303e8-134">Requirements</span></span>  
 <span data-ttu-id="303e8-135">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="303e8-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="303e8-136">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="303e8-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="303e8-137">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="303e8-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="303e8-138">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="303e8-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="303e8-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="303e8-139">See also</span></span>

- [<span data-ttu-id="303e8-140">ICorDebugManagedCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="303e8-140">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="303e8-141">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="303e8-141">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
