---
title: ICorDebugStepper Interfaz1
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
ms.openlocfilehash: 339b823e5e9f38ffd175c79e379e28ccc3565c11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423291"
---
# <a name="icordebugstepper-interface1"></a><span data-ttu-id="a4231-102">ICorDebugStepper Interfaz1</span><span class="sxs-lookup"><span data-stu-id="a4231-102">ICorDebugStepper Interface1</span></span>
<span data-ttu-id="a4231-103">Representa un paso en la ejecución del código realizado por un depurador, actúa como identificador entre la emisión y la finalización de un comando, y proporciona un modo de cancelar un paso.</span><span class="sxs-lookup"><span data-stu-id="a4231-103">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a4231-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="a4231-104">Methods</span></span>  
  
|<span data-ttu-id="a4231-105">Método</span><span class="sxs-lookup"><span data-stu-id="a4231-105">Method</span></span>|<span data-ttu-id="a4231-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a4231-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a4231-107">Deactivate (método)</span><span class="sxs-lookup"><span data-stu-id="a4231-107">Deactivate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md)|<span data-ttu-id="a4231-108">Hace que esta `ICorDebugStepper` para cancelar el último comando de paso que recibió.</span><span class="sxs-lookup"><span data-stu-id="a4231-108">Causes this `ICorDebugStepper` to cancel the last step command it received.</span></span>|  
|[<span data-ttu-id="a4231-109">IsActive (método)</span><span class="sxs-lookup"><span data-stu-id="a4231-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-isactive-method.md)|<span data-ttu-id="a4231-110">Obtiene un valor que indica si esta `ICorDebugStepper` se está ejecutando actualmente un paso.</span><span class="sxs-lookup"><span data-stu-id="a4231-110">Gets a value that indicates whether this `ICorDebugStepper` is currently executing a step.</span></span>|  
|[<span data-ttu-id="a4231-111">SetInterceptMask (método)</span><span class="sxs-lookup"><span data-stu-id="a4231-111">SetInterceptMask Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md)|<span data-ttu-id="a4231-112">Establece un valor de CorDebugIntercept que especifica los tipos de código que se recorren paso a paso.</span><span class="sxs-lookup"><span data-stu-id="a4231-112">Sets a CorDebugIntercept value that specifies the types of code that are stepped into.</span></span>|  
|[<span data-ttu-id="a4231-113">SetRangeIL (método)</span><span class="sxs-lookup"><span data-stu-id="a4231-113">SetRangeIL Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md)|<span data-ttu-id="a4231-114">Establece un valor que indica si las llamadas a [ICorDebugStepper:: StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) pasan valores de argumento en relación con el código nativo o al código de lenguaje intermedio (MSIL) de Microsoft del método que se está ejecutando en el paso a paso.</span><span class="sxs-lookup"><span data-stu-id="a4231-114">Sets a value that indicates whether calls to [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) pass argument values relative to the native code or to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>|  
|[<span data-ttu-id="a4231-115">SetUnmappedStopMask (método)</span><span class="sxs-lookup"><span data-stu-id="a4231-115">SetUnmappedStopMask Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)|<span data-ttu-id="a4231-116">Establece un valor de CorDebugUnmappedStop que especifica el tipo de código no asignado en el que se detendrá la ejecución.</span><span class="sxs-lookup"><span data-stu-id="a4231-116">Sets a CorDebugUnmappedStop value that specifies the type of unmapped code in which execution will halt.</span></span>|  
|[<span data-ttu-id="a4231-117">Step (método)</span><span class="sxs-lookup"><span data-stu-id="a4231-117">Step Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md)|<span data-ttu-id="a4231-118">Hace que esta `ICorDebugStepper` paso a paso a través de un subproceso que lo contiene y, opcionalmente, para seguir paso único a través de funciones que se llaman desde el subproceso.</span><span class="sxs-lookup"><span data-stu-id="a4231-118">Causes this `ICorDebugStepper` to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>|  
|[<span data-ttu-id="a4231-119">StepOut (método)</span><span class="sxs-lookup"><span data-stu-id="a4231-119">StepOut Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-stepout-method.md)|<span data-ttu-id="a4231-120">Hace que esta `ICorDebugStepper` paso a paso a través de un subproceso que lo contiene y completado cuando el marco actual devuelve el control al marco que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="a4231-120">Causes this `ICorDebugStepper` to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>|  
|[<span data-ttu-id="a4231-121">StepRange (método)</span><span class="sxs-lookup"><span data-stu-id="a4231-121">StepRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)|<span data-ttu-id="a4231-122">Hace que esta `ICorDebugStepper` paso a paso a través de un subproceso que lo contiene y para devolver cuando llegue al código situado más allá del último de los intervalos especificados.</span><span class="sxs-lookup"><span data-stu-id="a4231-122">Causes this `ICorDebugStepper` to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4231-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a4231-123">Remarks</span></span>  
 <span data-ttu-id="a4231-124">La `ICorDebugStepper` interfaz tiene los siguientes objetivos:</span><span class="sxs-lookup"><span data-stu-id="a4231-124">The `ICorDebugStepper` interface serves the following purposes:</span></span>  
  
-   <span data-ttu-id="a4231-125">Actúa como identificador entre un comando de paso emitido y la finalización de ese comando.</span><span class="sxs-lookup"><span data-stu-id="a4231-125">It acts as an identifier between a step command that is issued and the completion of that command.</span></span>  
  
-   <span data-ttu-id="a4231-126">Proporciona una interfaz central para encapsular la versión que se pueden realizar.</span><span class="sxs-lookup"><span data-stu-id="a4231-126">It provides a central interface to encapsulate all the stepping that can be performed.</span></span>  
  
-   <span data-ttu-id="a4231-127">Proporciona una manera de cancelar prematuramente una operación de ejecución paso a paso.</span><span class="sxs-lookup"><span data-stu-id="a4231-127">It provides a way to prematurely cancel a stepping operation.</span></span>  
  
 <span data-ttu-id="a4231-128">Puede haber más de un paso a paso desencadene por subproceso.</span><span class="sxs-lookup"><span data-stu-id="a4231-128">There can be more than one stepper per thread.</span></span> <span data-ttu-id="a4231-129">Por ejemplo, puede ser alcanzado un punto de interrupción al avanzar a través de una función, y el usuario que desee iniciar una nueva operación de ejecución paso a paso dentro de esa función.</span><span class="sxs-lookup"><span data-stu-id="a4231-129">For example, a breakpoint may be hit while stepping over a function, and the user may wish to start a new stepping operation inside that function.</span></span> <span data-ttu-id="a4231-130">Es decisión del depurador para determinar cómo controlar esta situación.</span><span class="sxs-lookup"><span data-stu-id="a4231-130">It is up to the debugger to determine how to handle this situation.</span></span> <span data-ttu-id="a4231-131">El depurador puede cancelar la operación de ejecución paso a paso original o anidar las dos operaciones.</span><span class="sxs-lookup"><span data-stu-id="a4231-131">The debugger may want to cancel the original stepping operation or nest the two operations.</span></span> <span data-ttu-id="a4231-132">La `ICorDebugStepper` interfaz es compatible con ambas opciones.</span><span class="sxs-lookup"><span data-stu-id="a4231-132">The `ICorDebugStepper` interface supports both choices.</span></span>  
  
 <span data-ttu-id="a4231-133">Un paso a paso desencadene puede migrar entre subprocesos si common language runtime (CLR) realiza una llamada entre subprocesos, calcular las referencias.</span><span class="sxs-lookup"><span data-stu-id="a4231-133">A stepper may migrate between threads if the common language runtime (CLR) makes a cross-threaded, marshaled call.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4231-134">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="a4231-134">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4231-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a4231-135">Requirements</span></span>  
 <span data-ttu-id="a4231-136">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4231-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4231-137">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a4231-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a4231-138">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4231-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4231-139">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4231-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4231-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4231-140">See Also</span></span>  
 [<span data-ttu-id="a4231-141">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="a4231-141">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
