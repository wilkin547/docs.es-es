---
title: ICorDebugExceptionDebugEvent::GetNativeIP (método)
ms.date: 03/30/2017
ms.assetid: 12e6a262-d9ac-49b8-9b80-1e653a2a3819
ms.openlocfilehash: f3b29b3ceda521afe9543588af332531aa03e84e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697420"
---
# <a name="icordebugexceptiondebugeventgetnativeip-method"></a><span data-ttu-id="9204f-102">ICorDebugExceptionDebugEvent::GetNativeIP (método)</span><span class="sxs-lookup"><span data-stu-id="9204f-102">ICorDebugExceptionDebugEvent::GetNativeIP Method</span></span>

<span data-ttu-id="9204f-103">Obtiene el puntero de instrucción nativo para este evento de depuración de la excepción.</span><span class="sxs-lookup"><span data-stu-id="9204f-103">Gets the native instruction pointer for this exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9204f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9204f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNativeIP(  
   [out]CORDB_ADDRESS *pIP  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9204f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9204f-105">Parameters</span></span>  

 `pIP`  
 <span data-ttu-id="9204f-106">[out] Puntero al puntero de instrucción para este evento de depuración de la excepción.</span><span class="sxs-lookup"><span data-stu-id="9204f-106">[out] A pointer to the instruction pointer for this exception debug event.</span></span> <span data-ttu-id="9204f-107">Vea la sección Comentarios para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9204f-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9204f-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9204f-108">Remarks</span></span>  

 <span data-ttu-id="9204f-109">El significado de este puntero de instrucción depende del tipo de evento, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="9204f-109">The meaning of this instruction pointer depends on the event type, as shown in the following table.</span></span>  
  
|<span data-ttu-id="9204f-110">Tipo de evento</span><span class="sxs-lookup"><span data-stu-id="9204f-110">Event type</span></span>|<span data-ttu-id="9204f-111">Significado del valor `pStackPointer`</span><span class="sxs-lookup"><span data-stu-id="9204f-111">Meaning of `pStackPointer` value</span></span>|  
|----------------|--------------------------------------|  
|[<span data-ttu-id="9204f-112">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="9204f-112">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="9204f-113">Dirección de la instrucción con errores.</span><span class="sxs-lookup"><span data-stu-id="9204f-113">The address of the faulting instruction.</span></span>|  
|[<span data-ttu-id="9204f-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="9204f-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="9204f-115">Dirección del código en el marco indicado por el método [GetStackPointer](icordebugexceptiondebugevent-getstackpointer-method.md) donde se reanudaría la ejecución si no se hubiera producido ninguna excepción.</span><span class="sxs-lookup"><span data-stu-id="9204f-115">The code address in the frame indicated by the [GetStackPointer](icordebugexceptiondebugevent-getstackpointer-method.md) method where execution would resume if no exception had been raised.</span></span> <span data-ttu-id="9204f-116">La excepción puede o no puede causar un código diferente, por ejemplo, un bloque catch de una cláusula `try/catch/finally`, para ejecutar en este marco.</span><span class="sxs-lookup"><span data-stu-id="9204f-116">The exception may or may not cause different code, such as the catch block of a `try/catch/finally` clause, to be executed in this frame.</span></span>|  
|[<span data-ttu-id="9204f-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="9204f-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="9204f-118">Dirección del código donde `catch` se iniciará la ejecución del controlador en el marco indicado por el método [GetStackPointer](icordebugexceptiondebugevent-getstackpointer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9204f-118">The code address where `catch` handler execution will start in the frame indicated by the [GetStackPointer](icordebugexceptiondebugevent-getstackpointer-method.md) method.</span></span>|  
|[<span data-ttu-id="9204f-119">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="9204f-119">MANAGED_EXCEPTION_UNHANDLED</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="9204f-120">`pIP` es 0.</span><span class="sxs-lookup"><span data-stu-id="9204f-120">`pIP` is 0.</span></span>|  
  
 <span data-ttu-id="9204f-121">El tipo de evento está disponible en el método [ICorDebugDebugEvent:: GetEventKind](icordebugdebugevent-geteventkind-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9204f-121">The event type is available from the [ICorDebugDebugEvent::GetEventKind](icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9204f-122">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9204f-122">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9204f-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9204f-123">Requirements</span></span>  

 <span data-ttu-id="9204f-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9204f-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9204f-125">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9204f-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9204f-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9204f-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9204f-127">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9204f-127">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9204f-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9204f-128">See also</span></span>

- [<span data-ttu-id="9204f-129">Interfaz ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="9204f-129">ICorDebugExceptionDebugEvent Interface</span></span>](icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="9204f-130">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="9204f-130">Debugging Interfaces</span></span>](debugging-interfaces.md)
