---
description: 'Más información sobre: ICorDebugExceptionDebugEvent:: GetStackPointer (método)'
title: ICorDebugExceptionDebugEvent::GetNativeIP (método)
ms.date: 03/30/2017
ms.assetid: d8f66a1c-16be-4264-afc5-bc2dfbb4a682
ms.openlocfilehash: 5a62a5eb54fff1e94beebc222e3f18cc4655040f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693452"
---
# <a name="icordebugexceptiondebugeventgetstackpointer-method"></a><span data-ttu-id="3563c-103">ICorDebugExceptionDebugEvent::GetNativeIP (método)</span><span class="sxs-lookup"><span data-stu-id="3563c-103">ICorDebugExceptionDebugEvent::GetStackPointer Method</span></span>

<span data-ttu-id="3563c-104">Obtiene el puntero de pila para este evento de depuración de la excepción.</span><span class="sxs-lookup"><span data-stu-id="3563c-104">Gets the stack pointer for this exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3563c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3563c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStackPointer(  
   [out]CORDB_ADDRESS *pStackPointer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3563c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3563c-106">Parameters</span></span>  

 `pStackPointer`  
 <span data-ttu-id="3563c-107">[out] Puntero a la dirección del puntero de pila para este evento de depuración de la excepción.</span><span class="sxs-lookup"><span data-stu-id="3563c-107">[out] A pointer to the address of the stack pointer for this exception debug event.</span></span> <span data-ttu-id="3563c-108">Vea la sección Comentarios para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="3563c-108">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3563c-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3563c-109">Remarks</span></span>  

 <span data-ttu-id="3563c-110">El significado de este puntero de pila depende del tipo de evento, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="3563c-110">The meaning of this stack pointer depends on the event type, as shown in the following table.</span></span>  
  
|<span data-ttu-id="3563c-111">Tipo de evento</span><span class="sxs-lookup"><span data-stu-id="3563c-111">Event type</span></span>|<span data-ttu-id="3563c-112">Significado del valor `pStackPointer`</span><span class="sxs-lookup"><span data-stu-id="3563c-112">Meaning of `pStackPointer` value</span></span>|  
|----------------|--------------------------------------|  
|[<span data-ttu-id="3563c-113">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="3563c-113">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="3563c-114">Puntero de pila para el marco que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="3563c-114">The stack pointer for the frame that threw the exception.</span></span>|  
|[<span data-ttu-id="3563c-115">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="3563c-115">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="3563c-116">Puntero de pila para el marco de código de usuario más cercano al punto de la excepción generada.</span><span class="sxs-lookup"><span data-stu-id="3563c-116">The stack pointer for the user-code frame closest to the point of the thrown exception.</span></span>|  
|[<span data-ttu-id="3563c-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="3563c-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="3563c-118">Puntero de pila para el marco que contiene el controlador catch.</span><span class="sxs-lookup"><span data-stu-id="3563c-118">The stack pointer for the frame that contains the catch handler.</span></span>|  
|[<span data-ttu-id="3563c-119">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="3563c-119">MANAGED_EXCEPTION_UNHANDLED</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="3563c-120">`pStackPointer` es **NULL**.</span><span class="sxs-lookup"><span data-stu-id="3563c-120">`pStackPointer` is **null**.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="3563c-121">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="3563c-121">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="3563c-122">El tipo de evento está disponible en el método [ICorDebugDebugEvent:: GetEventKind](icordebugdebugevent-geteventkind-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3563c-122">The event type is available from the [ICorDebugDebugEvent::GetEventKind](icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3563c-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3563c-123">Requirements</span></span>  

 <span data-ttu-id="3563c-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3563c-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3563c-125">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3563c-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3563c-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3563c-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3563c-127">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3563c-127">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3563c-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="3563c-128">See also</span></span>

- [<span data-ttu-id="3563c-129">Interfaz ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="3563c-129">ICorDebugExceptionDebugEvent Interface</span></span>](icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="3563c-130">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="3563c-130">Debugging Interfaces</span></span>](debugging-interfaces.md)
