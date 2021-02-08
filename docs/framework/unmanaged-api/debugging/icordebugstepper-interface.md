---
description: 'Más información acerca de: ICorDebugStepper (interfaz)'
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
ms.openlocfilehash: a16df9d25b4d87b0638448c1fdf8fec4759261d3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803599"
---
# <a name="icordebugstepper-interface"></a><span data-ttu-id="90420-103">Interfaz ICorDebugStepper</span><span class="sxs-lookup"><span data-stu-id="90420-103">ICorDebugStepper Interface</span></span>

<span data-ttu-id="90420-104">Representa un paso en la ejecución del código realizado por un depurador, actúa como identificador entre la emisión y la finalización de un comando, y proporciona un modo de cancelar un paso.</span><span class="sxs-lookup"><span data-stu-id="90420-104">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="90420-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="90420-105">Methods</span></span>  
  
|<span data-ttu-id="90420-106">Método</span><span class="sxs-lookup"><span data-stu-id="90420-106">Method</span></span>|<span data-ttu-id="90420-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="90420-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="90420-108">Método Deactivate</span><span class="sxs-lookup"><span data-stu-id="90420-108">Deactivate Method</span></span>](icordebugstepper-deactivate-method.md)|<span data-ttu-id="90420-109">Hace que se `ICorDebugStepper` cancele el último comando de paso que se ha recibido.</span><span class="sxs-lookup"><span data-stu-id="90420-109">Causes this `ICorDebugStepper` to cancel the last step command it received.</span></span>|  
|[<span data-ttu-id="90420-110">IsActive (Método)</span><span class="sxs-lookup"><span data-stu-id="90420-110">IsActive Method</span></span>](icordebugstepper-isactive-method.md)|<span data-ttu-id="90420-111">Obtiene un valor que indica si este `ICorDebugStepper` está ejecutando actualmente un paso.</span><span class="sxs-lookup"><span data-stu-id="90420-111">Gets a value that indicates whether this `ICorDebugStepper` is currently executing a step.</span></span>|  
|[<span data-ttu-id="90420-112">Método SetInterceptMask</span><span class="sxs-lookup"><span data-stu-id="90420-112">SetInterceptMask Method</span></span>](icordebugstepper-setinterceptmask-method.md)|<span data-ttu-id="90420-113">Establece un valor Cordebugintercept (que especifica los tipos de código a los que se van a recorrer.</span><span class="sxs-lookup"><span data-stu-id="90420-113">Sets a CorDebugIntercept value that specifies the types of code that are stepped into.</span></span>|  
|[<span data-ttu-id="90420-114">Método SetRangeIL</span><span class="sxs-lookup"><span data-stu-id="90420-114">SetRangeIL Method</span></span>](icordebugstepper-setrangeil-method.md)|<span data-ttu-id="90420-115">Establece un valor que indica si las llamadas a [ICorDebugStepper:: steprange (](icordebugstepper-steprange-method.md) pasan valores de argumento en relación con el código nativo o con el código del lenguaje intermedio de Microsoft (MSIL) del método que se va a recorrer.</span><span class="sxs-lookup"><span data-stu-id="90420-115">Sets a value that indicates whether calls to [ICorDebugStepper::StepRange](icordebugstepper-steprange-method.md) pass argument values relative to the native code or to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>|  
|[<span data-ttu-id="90420-116">Método SetUnmappedStopMask</span><span class="sxs-lookup"><span data-stu-id="90420-116">SetUnmappedStopMask Method</span></span>](icordebugstepper-setunmappedstopmask-method.md)|<span data-ttu-id="90420-117">Establece un valor de Cordebugunmappedstop (que especifica el tipo de código no asignado en el que se detendrá la ejecución.</span><span class="sxs-lookup"><span data-stu-id="90420-117">Sets a CorDebugUnmappedStop value that specifies the type of unmapped code in which execution will halt.</span></span>|  
|[<span data-ttu-id="90420-118">Método Step</span><span class="sxs-lookup"><span data-stu-id="90420-118">Step Method</span></span>](icordebugstepper-step-method.md)|<span data-ttu-id="90420-119">Hace que esto pase `ICorDebugStepper` de un solo paso a través de su subproceso contenedor y, opcionalmente, para continuar con la ejecución paso a paso de las funciones a las que se llama en el subproceso.</span><span class="sxs-lookup"><span data-stu-id="90420-119">Causes this `ICorDebugStepper` to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>|  
|[<span data-ttu-id="90420-120">Método StepOut</span><span class="sxs-lookup"><span data-stu-id="90420-120">StepOut Method</span></span>](icordebugstepper-stepout-method.md)|<span data-ttu-id="90420-121">Hace que esto `ICorDebugStepper` se lleve a cabo de un solo paso a través de su subproceso contenedor y que se complete cuando el fotograma actual devuelva el control al marco que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="90420-121">Causes this `ICorDebugStepper` to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>|  
|[<span data-ttu-id="90420-122">Método StepRange</span><span class="sxs-lookup"><span data-stu-id="90420-122">StepRange Method</span></span>](icordebugstepper-steprange-method.md)|<span data-ttu-id="90420-123">Hace que esto `ICorDebugStepper` pase de un solo paso a través de su subproceso contenedor y que devuelva cuando llegue al código más allá del último de los intervalos especificados.</span><span class="sxs-lookup"><span data-stu-id="90420-123">Causes this `ICorDebugStepper` to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90420-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="90420-124">Remarks</span></span>  

 <span data-ttu-id="90420-125">La `ICorDebugStepper` interfaz sirve para los siguientes fines:</span><span class="sxs-lookup"><span data-stu-id="90420-125">The `ICorDebugStepper` interface serves the following purposes:</span></span>  
  
- <span data-ttu-id="90420-126">Actúa como un identificador entre un comando Step que se emite y la finalización de ese comando.</span><span class="sxs-lookup"><span data-stu-id="90420-126">It acts as an identifier between a step command that is issued and the completion of that command.</span></span>  
  
- <span data-ttu-id="90420-127">Proporciona una interfaz central para encapsular todo el paso que se puede realizar.</span><span class="sxs-lookup"><span data-stu-id="90420-127">It provides a central interface to encapsulate all the stepping that can be performed.</span></span>  
  
- <span data-ttu-id="90420-128">Proporciona una manera de cancelar prematuramente una operación de ejecución paso a paso.</span><span class="sxs-lookup"><span data-stu-id="90420-128">It provides a way to prematurely cancel a stepping operation.</span></span>  
  
 <span data-ttu-id="90420-129">Puede haber más de un stepper por subproceso.</span><span class="sxs-lookup"><span data-stu-id="90420-129">There can be more than one stepper per thread.</span></span> <span data-ttu-id="90420-130">Por ejemplo, se puede tener acceso a un punto de interrupción mientras se realiza la ejecución paso a paso por procedimientos y el usuario puede iniciar una nueva operación de ejecución paso a paso dentro de esa función.</span><span class="sxs-lookup"><span data-stu-id="90420-130">For example, a breakpoint may be hit while stepping over a function, and the user may wish to start a new stepping operation inside that function.</span></span> <span data-ttu-id="90420-131">Depende del depurador determinar cómo tratar esta situación.</span><span class="sxs-lookup"><span data-stu-id="90420-131">It is up to the debugger to determine how to handle this situation.</span></span> <span data-ttu-id="90420-132">Es posible que el depurador desee cancelar la operación de ejecución paso a paso original o anidar las dos operaciones.</span><span class="sxs-lookup"><span data-stu-id="90420-132">The debugger may want to cancel the original stepping operation or nest the two operations.</span></span> <span data-ttu-id="90420-133">La `ICorDebugStepper` interfaz admite ambas opciones.</span><span class="sxs-lookup"><span data-stu-id="90420-133">The `ICorDebugStepper` interface supports both choices.</span></span>  
  
 <span data-ttu-id="90420-134">Un stepper se puede migrar entre subprocesos si el Common Language Runtime (CLR) realiza una llamada entre subprocesos y con referencias calculadas.</span><span class="sxs-lookup"><span data-stu-id="90420-134">A stepper may migrate between threads if the common language runtime (CLR) makes a cross-threaded, marshaled call.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="90420-135">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="90420-135">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90420-136">Requisitos</span><span class="sxs-lookup"><span data-stu-id="90420-136">Requirements</span></span>  

 <span data-ttu-id="90420-137">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90420-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90420-138">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="90420-138">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="90420-139">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90420-139">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90420-140">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90420-140">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90420-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="90420-141">See also</span></span>

- [<span data-ttu-id="90420-142">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="90420-142">Debugging Interfaces</span></span>](debugging-interfaces.md)
