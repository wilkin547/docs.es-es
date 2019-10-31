---
title: ICorDebug (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebug
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug
helpviewer_keywords:
- ICorDebug interface [.NET Framework debugging]
ms.assetid: 33f431d7-ab1a-494d-8af2-20ab15aba194
topic_type:
- apiref
ms.openlocfilehash: ee6bcbc9f3377735ed289d52afddb6efa755b16d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134075"
---
# <a name="icordebug-interface"></a><span data-ttu-id="2d3c9-102">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2d3c9-102">ICorDebug Interface</span></span>
<span data-ttu-id="2d3c9-103">Proporciona métodos que permiten a los desarrolladores depurar aplicaciones en el entorno de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="2d3c9-103">Provides methods that allow developers to debug applications in the common language runtime (CLR) environment.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2d3c9-104">La depuración en modo mixto (código administrado y nativo) no se admite en Windows 95, Windows 98 ni Windows ME, ni en plataformas que no son x86 (como IA64 y AMD64).</span><span class="sxs-lookup"><span data-stu-id="2d3c9-104">Mixed-mode (managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA64 and AMD64).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2d3c9-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="2d3c9-105">Methods</span></span>  
  
|<span data-ttu-id="2d3c9-106">Método</span><span class="sxs-lookup"><span data-stu-id="2d3c9-106">Method</span></span>|<span data-ttu-id="2d3c9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="2d3c9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2d3c9-108">CanLaunchOrAttach (método)</span><span class="sxs-lookup"><span data-stu-id="2d3c9-108">CanLaunchOrAttach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-canlaunchorattach-method.md)|<span data-ttu-id="2d3c9-109">Determina si el inicio de un nuevo proceso o la asociación al proceso dado es posible en el contexto del equipo actual y de la configuración en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2d3c9-109">Determines whether launching a new process or attaching to the given process is possible within the context of the current machine and runtime configuration.</span></span>|  
|[<span data-ttu-id="2d3c9-110">CreateProcess (método)</span><span class="sxs-lookup"><span data-stu-id="2d3c9-110">CreateProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md)|<span data-ttu-id="2d3c9-111">Inicia un proceso y su subproceso primario bajo el control del depurador.</span><span class="sxs-lookup"><span data-stu-id="2d3c9-111">Launches a process and its primary thread under the control of the debugger.</span></span>|  
|[<span data-ttu-id="2d3c9-112">DebugActiveProcess (método)</span><span class="sxs-lookup"><span data-stu-id="2d3c9-112">DebugActiveProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md)|<span data-ttu-id="2d3c9-113">Asocia el depurador a un proceso existente.</span><span class="sxs-lookup"><span data-stu-id="2d3c9-113">Attaches the debugger to an existing process.</span></span>|  
|[<span data-ttu-id="2d3c9-114">EnumerateProcesses (método)</span><span class="sxs-lookup"><span data-stu-id="2d3c9-114">EnumerateProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-enumerateprocesses-method.md)|<span data-ttu-id="2d3c9-115">Obtiene un enumerador para los procesos que se están depurando.</span><span class="sxs-lookup"><span data-stu-id="2d3c9-115">Gets an enumerator for the processes that are being debugged.</span></span>|  
|[<span data-ttu-id="2d3c9-116">GetProcess (método)</span><span class="sxs-lookup"><span data-stu-id="2d3c9-116">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-getprocess-method.md)|<span data-ttu-id="2d3c9-117">Devuelve el objeto "ICorDebugProcess" con el identificador de proceso especificado.</span><span class="sxs-lookup"><span data-stu-id="2d3c9-117">Returns the "ICorDebugProcess" object with the given process ID.</span></span>|  
|[<span data-ttu-id="2d3c9-118">Initialize (método)</span><span class="sxs-lookup"><span data-stu-id="2d3c9-118">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md)|<span data-ttu-id="2d3c9-119">Inicializa el objeto `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="2d3c9-119">Initializes the `ICorDebug` object.</span></span>|  
|[<span data-ttu-id="2d3c9-120">SetManagedHandler (método)</span><span class="sxs-lookup"><span data-stu-id="2d3c9-120">SetManagedHandler Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md)|<span data-ttu-id="2d3c9-121">Especifica el objeto de controlador de eventos para los eventos administrados.</span><span class="sxs-lookup"><span data-stu-id="2d3c9-121">Specifies the event handler object for managed events.</span></span>|  
|[<span data-ttu-id="2d3c9-122">SetUnmanagedHandler (método)</span><span class="sxs-lookup"><span data-stu-id="2d3c9-122">SetUnmanagedHandler Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-setunmanagedhandler-method.md)|<span data-ttu-id="2d3c9-123">Especifica el objeto de controlador de eventos para los eventos no administrados.</span><span class="sxs-lookup"><span data-stu-id="2d3c9-123">Specifies the event handler object for unmanaged events.</span></span>|  
|[<span data-ttu-id="2d3c9-124">Terminate (método)</span><span class="sxs-lookup"><span data-stu-id="2d3c9-124">Terminate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md)|<span data-ttu-id="2d3c9-125">Finaliza el objeto `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="2d3c9-125">Terminates the `ICorDebug` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d3c9-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2d3c9-126">Remarks</span></span>  
 <span data-ttu-id="2d3c9-127">`ICorDebug` representa un bucle de procesamiento de eventos para un proceso del depurador.</span><span class="sxs-lookup"><span data-stu-id="2d3c9-127">`ICorDebug` represents an event processing loop for a debugger process.</span></span> <span data-ttu-id="2d3c9-128">El depurador debe esperar a la devolución de llamada [ICorDebugManagedCallback:: ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) de todos los procesos que se están depurando antes de liberar esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="2d3c9-128">The debugger must wait for the [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback from all processes being debugged before releasing this interface.</span></span>  
  
 <span data-ttu-id="2d3c9-129">El objeto `ICorDebug` es el objeto inicial para controlar toda la depuración administrada.</span><span class="sxs-lookup"><span data-stu-id="2d3c9-129">The `ICorDebug` object is the initial object to control all further managed debugging.</span></span> <span data-ttu-id="2d3c9-130">En las versiones 1,0 y 1,1 de .NET Framework, este objeto era un objeto `CoClass` creado a partir de COM.</span><span class="sxs-lookup"><span data-stu-id="2d3c9-130">In the .NET Framework versions 1.0 and 1.1, this object was a `CoClass` object created from COM.</span></span> <span data-ttu-id="2d3c9-131">En la versión .NET Framework 2,0, este objeto ya no es un objeto `CoClass`.</span><span class="sxs-lookup"><span data-stu-id="2d3c9-131">In the .NET Framework version 2.0, this object is no longer a `CoClass` object.</span></span> <span data-ttu-id="2d3c9-132">Debe crearse mediante la función [CreateDebuggingInterfaceFromVersion (](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) , que es más compatible con la versión.</span><span class="sxs-lookup"><span data-stu-id="2d3c9-132">It must be created by the [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) function, which is more version-aware.</span></span> <span data-ttu-id="2d3c9-133">Esta nueva función de creación permite a los clientes obtener una implementación específica de `ICorDebug`, que también emula una versión específica de la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="2d3c9-133">This new creation function enables clients to get a specific implementation of `ICorDebug`, which also emulates a specific version of the debugging API.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2d3c9-134">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="2d3c9-134">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d3c9-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2d3c9-135">Requirements</span></span>  
 <span data-ttu-id="2d3c9-136">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d3c9-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d3c9-137">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2d3c9-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2d3c9-138">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d3c9-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d3c9-139">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d3c9-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d3c9-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d3c9-140">See also</span></span>

- [<span data-ttu-id="2d3c9-141">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="2d3c9-141">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
