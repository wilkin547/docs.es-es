---
description: 'Más información sobre: ICorDebugExceptionDebugEvent:: Getnativeip ((método)'
title: ICorDebugExceptionDebugEvent::GetNativeIP (método)
ms.date: 03/30/2017
ms.assetid: 12e6a262-d9ac-49b8-9b80-1e653a2a3819
ms.openlocfilehash: 89bda36efc59e2462634c3d8a3a5835c9d4b3354
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693465"
---
# <a name="icordebugexceptiondebugeventgetnativeip-method"></a><span data-ttu-id="a642b-103">ICorDebugExceptionDebugEvent::GetNativeIP (método)</span><span class="sxs-lookup"><span data-stu-id="a642b-103">ICorDebugExceptionDebugEvent::GetNativeIP Method</span></span>

<span data-ttu-id="a642b-104">Obtiene el puntero de instrucción nativo para este evento de depuración de la excepción.</span><span class="sxs-lookup"><span data-stu-id="a642b-104">Gets the native instruction pointer for this exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a642b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a642b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNativeIP(  
   [out]CORDB_ADDRESS *pIP  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a642b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a642b-106">Parameters</span></span>  

 `pIP`  
 <span data-ttu-id="a642b-107">[out] Puntero al puntero de instrucción para este evento de depuración de la excepción.</span><span class="sxs-lookup"><span data-stu-id="a642b-107">[out] A pointer to the instruction pointer for this exception debug event.</span></span> <span data-ttu-id="a642b-108">Vea la sección Comentarios para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a642b-108">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a642b-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a642b-109">Remarks</span></span>  

 <span data-ttu-id="a642b-110">El significado de este puntero de instrucción depende del tipo de evento, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="a642b-110">The meaning of this instruction pointer depends on the event type, as shown in the following table.</span></span>  
  
|<span data-ttu-id="a642b-111">Tipo de evento</span><span class="sxs-lookup"><span data-stu-id="a642b-111">Event type</span></span>|<span data-ttu-id="a642b-112">Significado del valor `pStackPointer`</span><span class="sxs-lookup"><span data-stu-id="a642b-112">Meaning of `pStackPointer` value</span></span>|  
|----------------|--------------------------------------|  
|[<span data-ttu-id="a642b-113">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="a642b-113">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="a642b-114">Dirección de la instrucción con errores.</span><span class="sxs-lookup"><span data-stu-id="a642b-114">The address of the faulting instruction.</span></span>|  
|[<span data-ttu-id="a642b-115">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="a642b-115">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="a642b-116">Dirección del código en el marco indicado por el método [GetStackPointer](icordebugexceptiondebugevent-getstackpointer-method.md) donde se reanudaría la ejecución si no se hubiera producido ninguna excepción.</span><span class="sxs-lookup"><span data-stu-id="a642b-116">The code address in the frame indicated by the [GetStackPointer](icordebugexceptiondebugevent-getstackpointer-method.md) method where execution would resume if no exception had been raised.</span></span> <span data-ttu-id="a642b-117">La excepción puede o no puede causar un código diferente, por ejemplo, un bloque catch de una cláusula `try/catch/finally`, para ejecutar en este marco.</span><span class="sxs-lookup"><span data-stu-id="a642b-117">The exception may or may not cause different code, such as the catch block of a `try/catch/finally` clause, to be executed in this frame.</span></span>|  
|[<span data-ttu-id="a642b-118">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="a642b-118">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="a642b-119">Dirección del código donde `catch` se iniciará la ejecución del controlador en el marco indicado por el método [GetStackPointer](icordebugexceptiondebugevent-getstackpointer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a642b-119">The code address where `catch` handler execution will start in the frame indicated by the [GetStackPointer](icordebugexceptiondebugevent-getstackpointer-method.md) method.</span></span>|  
|[<span data-ttu-id="a642b-120">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="a642b-120">MANAGED_EXCEPTION_UNHANDLED</span></span>](cordebugrecordformat-enumeration.md)|<span data-ttu-id="a642b-121">`pIP` es 0.</span><span class="sxs-lookup"><span data-stu-id="a642b-121">`pIP` is 0.</span></span>|  
  
 <span data-ttu-id="a642b-122">El tipo de evento está disponible en el método [ICorDebugDebugEvent:: GetEventKind](icordebugdebugevent-geteventkind-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a642b-122">The event type is available from the [ICorDebugDebugEvent::GetEventKind](icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a642b-123">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a642b-123">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a642b-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a642b-124">Requirements</span></span>  

 <span data-ttu-id="a642b-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a642b-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a642b-126">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a642b-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a642b-127">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a642b-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a642b-128">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a642b-128">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a642b-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="a642b-129">See also</span></span>

- [<span data-ttu-id="a642b-130">Interfaz ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="a642b-130">ICorDebugExceptionDebugEvent Interface</span></span>](icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="a642b-131">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="a642b-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
