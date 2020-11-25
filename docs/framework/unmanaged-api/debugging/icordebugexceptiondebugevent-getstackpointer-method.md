---
title: ICorDebugExceptionDebugEvent::GetNativeIP (método)
ms.date: 03/30/2017
ms.assetid: d8f66a1c-16be-4264-afc5-bc2dfbb4a682
ms.openlocfilehash: 46906e7d3ce7f257eb776e50dc6097946eb77d1f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697407"
---
# <a name="icordebugexceptiondebugeventgetstackpointer-method"></a><span data-ttu-id="d2804-102">ICorDebugExceptionDebugEvent::GetNativeIP (método)</span><span class="sxs-lookup"><span data-stu-id="d2804-102">ICorDebugExceptionDebugEvent::GetStackPointer Method</span></span>

<span data-ttu-id="d2804-103">Obtiene el puntero de pila para este evento de depuración de la excepción.</span><span class="sxs-lookup"><span data-stu-id="d2804-103">Gets the stack pointer for this exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2804-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d2804-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackPointer(  
   [out]CORDB_ADDRESS *pStackPointer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2804-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d2804-105">Parameters</span></span>  

 `pStackPointer`  
 <span data-ttu-id="d2804-106">[out] Puntero a la dirección del puntero de pila para este evento de depuración de la excepción.</span><span class="sxs-lookup"><span data-stu-id="d2804-106">[out] A pointer to the address of the stack pointer for this exception debug event.</span></span> <span data-ttu-id="d2804-107">Vea la sección Comentarios para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d2804-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2804-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d2804-108">Remarks</span></span>  

 <span data-ttu-id="d2804-109">El significado de este puntero de pila depende del tipo de evento, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="d2804-109">The meaning of this stack pointer depends on the event type, as shown in the following table.</span></span>  
  
|<span data-ttu-id="d2804-110">Tipo de evento</span><span class="sxs-lookup"><span data-stu-id="d2804-110">Event type</span></span>|<span data-ttu-id="d2804-111">Significado del valor `pStackPointer`</span><span class="sxs-lookup"><span data-stu-id="d2804-111">Meaning of `pStackPointer` value</span></span>|  
|----------------|--------------------------------------|  
|[<span data-ttu-id="d2804-112">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="d2804-112">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="d2804-113">Puntero de pila para el marco que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="d2804-113">The stack pointer for the frame that threw the exception.</span></span>|  
|[<span data-ttu-id="d2804-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="d2804-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="d2804-115">Puntero de pila para el marco de código de usuario más cercano al punto de la excepción generada.</span><span class="sxs-lookup"><span data-stu-id="d2804-115">The stack pointer for the user-code frame closest to the point of the thrown exception.</span></span>|  
|[<span data-ttu-id="d2804-116">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="d2804-116">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="d2804-117">Puntero de pila para el marco que contiene el controlador catch.</span><span class="sxs-lookup"><span data-stu-id="d2804-117">The stack pointer for the frame that contains the catch handler.</span></span>|  
|[<span data-ttu-id="d2804-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="d2804-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="d2804-119">`pStackPointer` es **NULL**.</span><span class="sxs-lookup"><span data-stu-id="d2804-119">`pStackPointer` is **null**.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="d2804-120">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d2804-120">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="d2804-121">El tipo de evento está disponible en el método [ICorDebugDebugEvent:: GetEventKind](icordebugdebugevent-geteventkind-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d2804-121">The event type is available from the [ICorDebugDebugEvent::GetEventKind](icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2804-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d2804-122">Requirements</span></span>  

 <span data-ttu-id="d2804-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2804-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2804-124">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d2804-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d2804-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2804-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2804-126">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2804-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2804-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d2804-127">See also</span></span>

- [<span data-ttu-id="d2804-128">Interfaz ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="d2804-128">ICorDebugExceptionDebugEvent Interface</span></span>](icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="d2804-129">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="d2804-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
