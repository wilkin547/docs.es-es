---
title: Interfaz ICorDebugStepper
ms.date: 03/30/2017
api_name:
- ICorDebugStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper
helpviewer_keywords:
- ICorDebugStepper interface [.NET Framework debugging]
ms.assetid: ed8364eb-f01b-46f6-b5e3-5dda9cae2dfe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f83b9796bb692ce234a03c596387960bd879ebf3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212523"
---
# <a name="icordebugstepper-interface"></a><span data-ttu-id="a9513-102">Interfaz ICorDebugStepper</span><span class="sxs-lookup"><span data-stu-id="a9513-102">ICorDebugStepper Interface</span></span>
<span data-ttu-id="a9513-103">Representa un paso en la ejecución del código realizado por un depurador, actúa como identificador entre la emisión y la finalización de un comando, y proporciona un modo de cancelar un paso.</span><span class="sxs-lookup"><span data-stu-id="a9513-103">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a9513-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="a9513-104">Methods</span></span>  
  
|<span data-ttu-id="a9513-105">Método</span><span class="sxs-lookup"><span data-stu-id="a9513-105">Method</span></span>|<span data-ttu-id="a9513-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a9513-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a9513-107">Método Deactivate</span><span class="sxs-lookup"><span data-stu-id="a9513-107">Deactivate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md)|<span data-ttu-id="a9513-108">Hace que esta `ICorDebugStepper` para cancelar el último comando de paso que recibió.</span><span class="sxs-lookup"><span data-stu-id="a9513-108">Causes this `ICorDebugStepper` to cancel the last step command it received.</span></span>|  
|[<span data-ttu-id="a9513-109">Método IsActive</span><span class="sxs-lookup"><span data-stu-id="a9513-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-isactive-method.md)|<span data-ttu-id="a9513-110">Obtiene un valor que indica si este `ICorDebugStepper` está ejecutando un paso.</span><span class="sxs-lookup"><span data-stu-id="a9513-110">Gets a value that indicates whether this `ICorDebugStepper` is currently executing a step.</span></span>|  
|[<span data-ttu-id="a9513-111">Método SetInterceptMask</span><span class="sxs-lookup"><span data-stu-id="a9513-111">SetInterceptMask Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md)|<span data-ttu-id="a9513-112">Establece un valor CorDebugIntercept que especifica los tipos de código que se ejecutar paso a paso.</span><span class="sxs-lookup"><span data-stu-id="a9513-112">Sets a CorDebugIntercept value that specifies the types of code that are stepped into.</span></span>|  
|[<span data-ttu-id="a9513-113">Método SetRangeIL</span><span class="sxs-lookup"><span data-stu-id="a9513-113">SetRangeIL Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md)|<span data-ttu-id="a9513-114">Establece un valor que indica si las llamadas a [ICorDebugStepper:: StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) pasar los valores de argumento en relación con el código nativo o código de lenguaje intermedio (MSIL) de Microsoft del método que se está ejecutando paso a través.</span><span class="sxs-lookup"><span data-stu-id="a9513-114">Sets a value that indicates whether calls to [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) pass argument values relative to the native code or to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>|  
|[<span data-ttu-id="a9513-115">Método SetUnmappedStopMask</span><span class="sxs-lookup"><span data-stu-id="a9513-115">SetUnmappedStopMask Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)|<span data-ttu-id="a9513-116">Establece un valor CorDebugUnmappedStop que especifica el tipo de código no asignado en el que se detendrá la ejecución.</span><span class="sxs-lookup"><span data-stu-id="a9513-116">Sets a CorDebugUnmappedStop value that specifies the type of unmapped code in which execution will halt.</span></span>|  
|[<span data-ttu-id="a9513-117">Método Step</span><span class="sxs-lookup"><span data-stu-id="a9513-117">Step Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md)|<span data-ttu-id="a9513-118">Hace que esta `ICorDebugStepper` paso a paso a través del subproceso que la contiene y, opcionalmente, para continuar pasando solo a través de funciones que se llaman dentro del subproceso.</span><span class="sxs-lookup"><span data-stu-id="a9513-118">Causes this `ICorDebugStepper` to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>|  
|[<span data-ttu-id="a9513-119">Método StepOut</span><span class="sxs-lookup"><span data-stu-id="a9513-119">StepOut Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-stepout-method.md)|<span data-ttu-id="a9513-120">Hace que esta `ICorDebugStepper` paso a paso a través del subproceso que la contiene y a completa cuando el marco actual devuelve el control al marco que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="a9513-120">Causes this `ICorDebugStepper` to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>|  
|[<span data-ttu-id="a9513-121">Método StepRange</span><span class="sxs-lookup"><span data-stu-id="a9513-121">StepRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)|<span data-ttu-id="a9513-122">Hace que esta `ICorDebugStepper` paso a paso a través del subproceso que la contiene y que se devuelve cuando llegue al código más allá del último de los intervalos especificados.</span><span class="sxs-lookup"><span data-stu-id="a9513-122">Causes this `ICorDebugStepper` to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9513-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a9513-123">Remarks</span></span>  
 <span data-ttu-id="a9513-124">El `ICorDebugStepper` interfaz tiene los siguientes objetivos:</span><span class="sxs-lookup"><span data-stu-id="a9513-124">The `ICorDebugStepper` interface serves the following purposes:</span></span>  
  
-   <span data-ttu-id="a9513-125">Actúa como identificador entre un comando de paso que se emite y la finalización de ese comando.</span><span class="sxs-lookup"><span data-stu-id="a9513-125">It acts as an identifier between a step command that is issued and the completion of that command.</span></span>  
  
-   <span data-ttu-id="a9513-126">Proporciona una interfaz central para encapsular toda la ejecución paso a paso que se puede realizar.</span><span class="sxs-lookup"><span data-stu-id="a9513-126">It provides a central interface to encapsulate all the stepping that can be performed.</span></span>  
  
-   <span data-ttu-id="a9513-127">Proporciona una manera de cancelar prematuramente una operación de ejecución paso a paso.</span><span class="sxs-lookup"><span data-stu-id="a9513-127">It provides a way to prematurely cancel a stepping operation.</span></span>  
  
 <span data-ttu-id="a9513-128">Puede haber más de un motor paso a paso por subproceso.</span><span class="sxs-lookup"><span data-stu-id="a9513-128">There can be more than one stepper per thread.</span></span> <span data-ttu-id="a9513-129">Por ejemplo, se puede alcanzar un punto de interrupción durante la ejecución paso a paso a través de una función, y el usuario que desee iniciar una nueva operación de ejecución paso a paso dentro de esa función.</span><span class="sxs-lookup"><span data-stu-id="a9513-129">For example, a breakpoint may be hit while stepping over a function, and the user may wish to start a new stepping operation inside that function.</span></span> <span data-ttu-id="a9513-130">Es el depurador para determinar cómo controlar esta situación.</span><span class="sxs-lookup"><span data-stu-id="a9513-130">It is up to the debugger to determine how to handle this situation.</span></span> <span data-ttu-id="a9513-131">El depurador desear cancelar la operación de ejecución paso a paso original o anidar las dos operaciones.</span><span class="sxs-lookup"><span data-stu-id="a9513-131">The debugger may want to cancel the original stepping operation or nest the two operations.</span></span> <span data-ttu-id="a9513-132">El `ICorDebugStepper` interfaz admite ambas opciones.</span><span class="sxs-lookup"><span data-stu-id="a9513-132">The `ICorDebugStepper` interface supports both choices.</span></span>  
  
 <span data-ttu-id="a9513-133">Puede migrar un motor paso a paso entre subprocesos si common language runtime (CLR) realiza una llamada entre subprocesos, cálculo de referencias.</span><span class="sxs-lookup"><span data-stu-id="a9513-133">A stepper may migrate between threads if the common language runtime (CLR) makes a cross-threaded, marshaled call.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a9513-134">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="a9513-134">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9513-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9513-135">Requirements</span></span>  
 <span data-ttu-id="a9513-136">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9513-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9513-137">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a9513-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9513-138">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9513-138">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a9513-139">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="a9513-139">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a9513-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9513-140">See also</span></span>

- [<span data-ttu-id="a9513-141">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="a9513-141">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
