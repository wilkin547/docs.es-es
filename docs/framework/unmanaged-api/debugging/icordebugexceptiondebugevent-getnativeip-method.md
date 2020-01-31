---
title: ICorDebugExceptionDebugEvent::GetNativeIP (método)
ms.date: 03/30/2017
ms.assetid: 12e6a262-d9ac-49b8-9b80-1e653a2a3819
ms.openlocfilehash: 31af92dae47027b7285b422a05014b081d7e39a2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788685"
---
# <a name="icordebugexceptiondebugeventgetnativeip-method"></a><span data-ttu-id="5b0e1-102">ICorDebugExceptionDebugEvent::GetNativeIP (método)</span><span class="sxs-lookup"><span data-stu-id="5b0e1-102">ICorDebugExceptionDebugEvent::GetNativeIP Method</span></span>
<span data-ttu-id="5b0e1-103">Obtiene el puntero de instrucción nativo para este evento de depuración de la excepción.</span><span class="sxs-lookup"><span data-stu-id="5b0e1-103">Gets the native instruction pointer for this exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b0e1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5b0e1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNativeIP(  
   [out]CORDB_ADDRESS *pIP  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b0e1-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="5b0e1-105">Parameters</span></span>  
 `pIP`  
 <span data-ttu-id="5b0e1-106">[out] Puntero al puntero de instrucción para este evento de depuración de la excepción.</span><span class="sxs-lookup"><span data-stu-id="5b0e1-106">[out] A pointer to the instruction pointer for this exception debug event.</span></span> <span data-ttu-id="5b0e1-107">Vea la sección Comentarios para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="5b0e1-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b0e1-108">Notas</span><span class="sxs-lookup"><span data-stu-id="5b0e1-108">Remarks</span></span>  
 <span data-ttu-id="5b0e1-109">El significado de este puntero de instrucción depende del tipo de evento, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="5b0e1-109">The meaning of this instruction pointer depends on the event type, as shown in the following table.</span></span>  
  
|<span data-ttu-id="5b0e1-110">Tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="5b0e1-110">Event type</span></span>|<span data-ttu-id="5b0e1-111">Significado del valor `pStackPointer`</span><span class="sxs-lookup"><span data-stu-id="5b0e1-111">Meaning of `pStackPointer` value</span></span>|  
|----------------|--------------------------------------|  
|[<span data-ttu-id="5b0e1-112">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="5b0e1-112">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="5b0e1-113">Dirección de la instrucción con errores.</span><span class="sxs-lookup"><span data-stu-id="5b0e1-113">The address of the faulting instruction.</span></span>|  
|[<span data-ttu-id="5b0e1-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="5b0e1-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="5b0e1-115">Dirección del código en el marco indicado por el método [GetStackPointer](icordebugexceptiondebugevent-getstackpointer-method.md) donde se reanudaría la ejecución si no se hubiera producido ninguna excepción.</span><span class="sxs-lookup"><span data-stu-id="5b0e1-115">The code address in the frame indicated by the [GetStackPointer](icordebugexceptiondebugevent-getstackpointer-method.md) method where execution would resume if no exception had been raised.</span></span> <span data-ttu-id="5b0e1-116">La excepción puede o no puede causar un código diferente, por ejemplo, un bloque catch de una cláusula `try/catch/finally`, para ejecutar en este marco.</span><span class="sxs-lookup"><span data-stu-id="5b0e1-116">The exception may or may not cause different code, such as the catch block of a `try/catch/finally` clause, to be executed in this frame.</span></span>|  
|[<span data-ttu-id="5b0e1-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="5b0e1-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="5b0e1-118">Dirección del código donde se iniciará la ejecución del controlador `catch` en el marco indicado por el método [GetStackPointer](icordebugexceptiondebugevent-getstackpointer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5b0e1-118">The code address where `catch` handler execution will start in the frame indicated by the [GetStackPointer](icordebugexceptiondebugevent-getstackpointer-method.md) method.</span></span>|  
|[<span data-ttu-id="5b0e1-119">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="5b0e1-119">MANAGED_EXCEPTION_UNHANDLED</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="5b0e1-120">`pIP` es 0.</span><span class="sxs-lookup"><span data-stu-id="5b0e1-120">`pIP` is 0.</span></span>|  
  
 <span data-ttu-id="5b0e1-121">El tipo de evento está disponible en el método [ICorDebugDebugEvent:: GetEventKind](icordebugdebugevent-geteventkind-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5b0e1-121">The event type is available from the [ICorDebugDebugEvent::GetEventKind](icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5b0e1-122">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="5b0e1-122">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b0e1-123">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="5b0e1-123">Requirements</span></span>  
 <span data-ttu-id="5b0e1-124">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b0e1-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b0e1-125">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5b0e1-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5b0e1-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b0e1-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b0e1-127">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b0e1-127">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b0e1-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b0e1-128">See also</span></span>

- [<span data-ttu-id="5b0e1-129">ICorDebugExceptionDebugEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5b0e1-129">ICorDebugExceptionDebugEvent Interface</span></span>](icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="5b0e1-130">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="5b0e1-130">Debugging Interfaces</span></span>](debugging-interfaces.md)
