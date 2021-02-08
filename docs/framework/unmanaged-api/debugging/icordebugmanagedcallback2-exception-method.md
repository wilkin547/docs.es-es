---
description: 'Más información sobre: ICorDebugManagedCallback2:: Exception (método)'
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
ms.openlocfilehash: 18fd4efcfbd1f13ce527b212d7450ba0d7651a3c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790889"
---
# <a name="icordebugmanagedcallback2exception-method"></a><span data-ttu-id="fe50a-103">ICorDebugManagedCallback2::Exception (Método)</span><span class="sxs-lookup"><span data-stu-id="fe50a-103">ICorDebugManagedCallback2::Exception Method</span></span>

<span data-ttu-id="fe50a-104">Notifica al depurador que se ha iniciado una búsqueda de un controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="fe50a-104">Notifies the debugger that a search for an exception handler has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe50a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fe50a-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="fe50a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fe50a-106">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="fe50a-107">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el subproceso en el que se produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="fe50a-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread on which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="fe50a-108">de Un puntero a un objeto ICorDebugThread que representa el subproceso en el que se produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="fe50a-108">[in] A pointer to an ICorDebugThread object that represents the thread on which the exception was thrown.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="fe50a-109">de Un puntero a un objeto ICorDebugFrame que representa un marco, determinado por el `dwEventType` parámetro.</span><span class="sxs-lookup"><span data-stu-id="fe50a-109">[in] A pointer to an ICorDebugFrame object that represents a frame, as determined by the `dwEventType` parameter.</span></span> <span data-ttu-id="fe50a-110">Para obtener más información, vea la tabla de la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="fe50a-110">For more information, see the table in the Remarks section.</span></span>  
  
 `nOffset`  
 <span data-ttu-id="fe50a-111">de Un entero que especifica un desplazamiento, tal y como lo determina el `dwEventType` parámetro.</span><span class="sxs-lookup"><span data-stu-id="fe50a-111">[in] An integer that specifies an offset, as determined by the `dwEventType` parameter.</span></span> <span data-ttu-id="fe50a-112">Para obtener más información, vea la tabla de la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="fe50a-112">For more information, see the table in the Remarks section.</span></span>  
  
 `dwEventType`  
 <span data-ttu-id="fe50a-113">de Valor de la enumeración Cordebugexceptioncallbacktype (que especifica el tipo de esta devolución de llamada de excepción.</span><span class="sxs-lookup"><span data-stu-id="fe50a-113">[in] A value of the CorDebugExceptionCallbackType enumeration that specifies the type of this exception callback.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="fe50a-114">de Un valor de la enumeración [cordebugexceptionflags (](cordebugexceptionflags-enumeration.md) que especifica información adicional sobre la excepción.</span><span class="sxs-lookup"><span data-stu-id="fe50a-114">[in] A value of the [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) enumeration that specifies additional information about the exception</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe50a-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fe50a-115">Remarks</span></span>  

 <span data-ttu-id="fe50a-116">La `Exception` devolución de llamada se llama en varios puntos durante la fase de búsqueda del proceso de control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="fe50a-116">The `Exception` callback is called at various points during the search phase of the exception-handling process.</span></span> <span data-ttu-id="fe50a-117">Es decir, se puede llamar más de una vez al desenredar una excepción.</span><span class="sxs-lookup"><span data-stu-id="fe50a-117">That is, it can be called more than once while unwinding an exception.</span></span>  
  
 <span data-ttu-id="fe50a-118">La excepción que se está procesando se puede recuperar desde el objeto ICorDebugThread al que hace referencia el `pThread` parámetro.</span><span class="sxs-lookup"><span data-stu-id="fe50a-118">The exception being processed can be retrieved from the ICorDebugThread object referenced by the `pThread` parameter.</span></span>  
  
 <span data-ttu-id="fe50a-119">El parámetro y el desplazamiento concretos vienen determinados por el parámetro de la `dwEventType` siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="fe50a-119">The particular frame and offset are determined by the `dwEventType` parameter as follows:</span></span>  
  
|<span data-ttu-id="fe50a-120">Valor de `dwEventType`</span><span class="sxs-lookup"><span data-stu-id="fe50a-120">Value of `dwEventType`</span></span>|<span data-ttu-id="fe50a-121">Valor de `pFrame`</span><span class="sxs-lookup"><span data-stu-id="fe50a-121">Value of `pFrame`</span></span>|<span data-ttu-id="fe50a-122">Valor de `nOffset`</span><span class="sxs-lookup"><span data-stu-id="fe50a-122">Value of `nOffset`</span></span>|  
|----------------------------|-----------------------|------------------------|  
|<span data-ttu-id="fe50a-123">DEBUG_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="fe50a-123">DEBUG_EXCEPTION_FIRST_CHANCE</span></span>|<span data-ttu-id="fe50a-124">Marco que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="fe50a-124">The frame that threw the exception.</span></span>|<span data-ttu-id="fe50a-125">Puntero de instrucción en el marco.</span><span class="sxs-lookup"><span data-stu-id="fe50a-125">The instruction pointer in the frame.</span></span>|  
|<span data-ttu-id="fe50a-126">DEBUG_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="fe50a-126">DEBUG_EXCEPTION_USER_FIRST_CHANCE</span></span>|<span data-ttu-id="fe50a-127">Marco de código de usuario más cercano al punto de la excepción iniciada.</span><span class="sxs-lookup"><span data-stu-id="fe50a-127">The user-code frame closest to the point of the thrown exception.</span></span>|<span data-ttu-id="fe50a-128">Puntero de instrucción en el marco.</span><span class="sxs-lookup"><span data-stu-id="fe50a-128">The instruction pointer in the frame.</span></span>|  
|<span data-ttu-id="fe50a-129">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="fe50a-129">DEBUG_EXCEPTION_CATCH_HANDLER_FOUND</span></span>|<span data-ttu-id="fe50a-130">Marco que contiene el controlador Catch.</span><span class="sxs-lookup"><span data-stu-id="fe50a-130">The frame that contains the catch handler.</span></span>|<span data-ttu-id="fe50a-131">Desplazamiento del lenguaje intermedio de Microsoft (MSIL) del principio del controlador Catch.</span><span class="sxs-lookup"><span data-stu-id="fe50a-131">The Microsoft intermediate language (MSIL) offset of the beginning of the catch handler.</span></span>|  
|<span data-ttu-id="fe50a-132">DEBUG_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="fe50a-132">DEBUG_EXCEPTION_UNHANDLED</span></span>|<span data-ttu-id="fe50a-133">NULL</span><span class="sxs-lookup"><span data-stu-id="fe50a-133">NULL</span></span>|<span data-ttu-id="fe50a-134">Sin definir.</span><span class="sxs-lookup"><span data-stu-id="fe50a-134">Undefined.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fe50a-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fe50a-135">Requirements</span></span>  

 <span data-ttu-id="fe50a-136">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe50a-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe50a-137">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fe50a-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe50a-138">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe50a-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe50a-139">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe50a-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe50a-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe50a-140">See also</span></span>

- [<span data-ttu-id="fe50a-141">ICorDebugManagedCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fe50a-141">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="fe50a-142">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fe50a-142">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
