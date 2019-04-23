---
title: ICorDebugExceptionDebugEvent::GetNativeIP (método)
ms.date: 03/30/2017
ms.assetid: d8f66a1c-16be-4264-afc5-bc2dfbb4a682
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d9d4c0a1938edd3e2fe88ea6e418b3430f1b5cb8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59163207"
---
# <a name="icordebugexceptiondebugeventgetstackpointer-method"></a><span data-ttu-id="5f9c0-102">ICorDebugExceptionDebugEvent::GetNativeIP (método)</span><span class="sxs-lookup"><span data-stu-id="5f9c0-102">ICorDebugExceptionDebugEvent::GetStackPointer Method</span></span>
<span data-ttu-id="5f9c0-103">Obtiene el puntero de pila para este evento de depuración de la excepción.</span><span class="sxs-lookup"><span data-stu-id="5f9c0-103">Gets the stack pointer for this exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f9c0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5f9c0-104">Syntax</span></span>  
  
```  
HRESULT GetStackPointer(  
   [out]CORDB_ADDRESS *pStackPointer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f9c0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5f9c0-105">Parameters</span></span>  
 `pStackPointer`  
 <span data-ttu-id="5f9c0-106">[out] Puntero a la dirección del puntero de pila para este evento de depuración de la excepción.</span><span class="sxs-lookup"><span data-stu-id="5f9c0-106">[out] A pointer to the address of the stack pointer for this exception debug event.</span></span> <span data-ttu-id="5f9c0-107">Vea la sección Comentarios para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="5f9c0-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f9c0-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5f9c0-108">Remarks</span></span>  
 <span data-ttu-id="5f9c0-109">El significado de este puntero de pila depende del tipo de evento, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="5f9c0-109">The meaning of this stack pointer depends on the event type, as shown in the following table.</span></span>  
  
|<span data-ttu-id="5f9c0-110">Tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="5f9c0-110">Event type</span></span>|<span data-ttu-id="5f9c0-111">Significado del valor `pStackPointer`</span><span class="sxs-lookup"><span data-stu-id="5f9c0-111">Meaning of `pStackPointer` value</span></span>|  
|----------------|--------------------------------------|  
|[<span data-ttu-id="5f9c0-112">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="5f9c0-112">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="5f9c0-113">Puntero de pila para el marco que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="5f9c0-113">The stack pointer for the frame that threw the exception.</span></span>|  
|[<span data-ttu-id="5f9c0-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="5f9c0-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="5f9c0-115">Puntero de pila para el marco de código de usuario más cercano al punto de la excepción generada.</span><span class="sxs-lookup"><span data-stu-id="5f9c0-115">The stack pointer for the user-code frame closest to the point of the thrown exception.</span></span>|  
|[<span data-ttu-id="5f9c0-116">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="5f9c0-116">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="5f9c0-117">Puntero de pila para el marco que contiene el controlador catch.</span><span class="sxs-lookup"><span data-stu-id="5f9c0-117">The stack pointer for the frame that contains the catch handler.</span></span>|  
|[<span data-ttu-id="5f9c0-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="5f9c0-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="5f9c0-119">`pStackPointer` es **NULL**.</span><span class="sxs-lookup"><span data-stu-id="5f9c0-119">`pStackPointer` is **null**.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="5f9c0-120">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="5f9c0-120">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="5f9c0-121">El tipo de evento está disponible en el [icordebugdebugevent:: Geteventkind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="5f9c0-121">The event type is available from the [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f9c0-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5f9c0-122">Requirements</span></span>  
 <span data-ttu-id="5f9c0-123">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f9c0-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f9c0-124">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f9c0-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f9c0-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f9c0-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f9c0-126">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f9c0-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f9c0-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f9c0-127">See also</span></span>

- [<span data-ttu-id="5f9c0-128">ICorDebugExceptionDebugEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5f9c0-128">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="5f9c0-129">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="5f9c0-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
