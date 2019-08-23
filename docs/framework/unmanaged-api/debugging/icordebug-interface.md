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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: afbf480d69e97662b5963706bb8c192aec0325a2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966288"
---
# <a name="icordebug-interface"></a><span data-ttu-id="78ec0-102">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="78ec0-102">ICorDebug Interface</span></span>
<span data-ttu-id="78ec0-103">Proporciona métodos que permiten a los desarrolladores depurar aplicaciones en el entorno de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="78ec0-103">Provides methods that allow developers to debug applications in the common language runtime (CLR) environment.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="78ec0-104">La depuración en modo mixto (código administrado y nativo) no se admite en Windows 95, Windows 98 ni Windows ME, ni en plataformas que no son x86 (como IA64 y AMD64).</span><span class="sxs-lookup"><span data-stu-id="78ec0-104">Mixed-mode (managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA64 and AMD64).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="78ec0-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="78ec0-105">Methods</span></span>  
  
|<span data-ttu-id="78ec0-106">Método</span><span class="sxs-lookup"><span data-stu-id="78ec0-106">Method</span></span>|<span data-ttu-id="78ec0-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="78ec0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="78ec0-108">CanLaunchOrAttach (método)</span><span class="sxs-lookup"><span data-stu-id="78ec0-108">CanLaunchOrAttach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-canlaunchorattach-method.md)|<span data-ttu-id="78ec0-109">Determina si el inicio de un nuevo proceso o la asociación al proceso dado es posible en el contexto del equipo actual y de la configuración en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="78ec0-109">Determines whether launching a new process or attaching to the given process is possible within the context of the current machine and runtime configuration.</span></span>|  
|[<span data-ttu-id="78ec0-110">CreateProcess (método)</span><span class="sxs-lookup"><span data-stu-id="78ec0-110">CreateProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md)|<span data-ttu-id="78ec0-111">Inicia un proceso y su subproceso primario bajo el control del depurador.</span><span class="sxs-lookup"><span data-stu-id="78ec0-111">Launches a process and its primary thread under the control of the debugger.</span></span>|  
|[<span data-ttu-id="78ec0-112">DebugActiveProcess (método)</span><span class="sxs-lookup"><span data-stu-id="78ec0-112">DebugActiveProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md)|<span data-ttu-id="78ec0-113">Asocia el depurador a un proceso existente.</span><span class="sxs-lookup"><span data-stu-id="78ec0-113">Attaches the debugger to an existing process.</span></span>|  
|[<span data-ttu-id="78ec0-114">EnumerateProcesses (método)</span><span class="sxs-lookup"><span data-stu-id="78ec0-114">EnumerateProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-enumerateprocesses-method.md)|<span data-ttu-id="78ec0-115">Obtiene un enumerador para los procesos que se están depurando.</span><span class="sxs-lookup"><span data-stu-id="78ec0-115">Gets an enumerator for the processes that are being debugged.</span></span>|  
|[<span data-ttu-id="78ec0-116">GetProcess (método)</span><span class="sxs-lookup"><span data-stu-id="78ec0-116">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-getprocess-method.md)|<span data-ttu-id="78ec0-117">Devuelve el objeto "ICorDebugProcess" con el identificador de proceso especificado.</span><span class="sxs-lookup"><span data-stu-id="78ec0-117">Returns the "ICorDebugProcess" object with the given process ID.</span></span>|  
|[<span data-ttu-id="78ec0-118">Initialize (método)</span><span class="sxs-lookup"><span data-stu-id="78ec0-118">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md)|<span data-ttu-id="78ec0-119">Inicializa el objeto `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="78ec0-119">Initializes the `ICorDebug` object.</span></span>|  
|[<span data-ttu-id="78ec0-120">SetManagedHandler (método)</span><span class="sxs-lookup"><span data-stu-id="78ec0-120">SetManagedHandler Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md)|<span data-ttu-id="78ec0-121">Especifica el objeto de controlador de eventos para los eventos administrados.</span><span class="sxs-lookup"><span data-stu-id="78ec0-121">Specifies the event handler object for managed events.</span></span>|  
|[<span data-ttu-id="78ec0-122">SetUnmanagedHandler (método)</span><span class="sxs-lookup"><span data-stu-id="78ec0-122">SetUnmanagedHandler Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-setunmanagedhandler-method.md)|<span data-ttu-id="78ec0-123">Especifica el objeto de controlador de eventos para los eventos no administrados.</span><span class="sxs-lookup"><span data-stu-id="78ec0-123">Specifies the event handler object for unmanaged events.</span></span>|  
|[<span data-ttu-id="78ec0-124">Terminate (método)</span><span class="sxs-lookup"><span data-stu-id="78ec0-124">Terminate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md)|<span data-ttu-id="78ec0-125">Finaliza el `ICorDebug` objeto.</span><span class="sxs-lookup"><span data-stu-id="78ec0-125">Terminates the `ICorDebug` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78ec0-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="78ec0-126">Remarks</span></span>  
 <span data-ttu-id="78ec0-127">`ICorDebug`representa un bucle de procesamiento de eventos para un proceso del depurador.</span><span class="sxs-lookup"><span data-stu-id="78ec0-127">`ICorDebug` represents an event processing loop for a debugger process.</span></span> <span data-ttu-id="78ec0-128">El depurador debe esperar a la devolución de llamada [ICorDebugManagedCallback:: ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) de todos los procesos que se están depurando antes de liberar esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="78ec0-128">The debugger must wait for the [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback from all processes being debugged before releasing this interface.</span></span>  
  
 <span data-ttu-id="78ec0-129">El `ICorDebug` objeto es el objeto inicial para controlar toda la depuración administrada.</span><span class="sxs-lookup"><span data-stu-id="78ec0-129">The `ICorDebug` object is the initial object to control all further managed debugging.</span></span> <span data-ttu-id="78ec0-130">En las versiones 1,0 y 1,1 de .NET Framework, este objeto era `CoClass` un objeto creado a partir de com.</span><span class="sxs-lookup"><span data-stu-id="78ec0-130">In the .NET Framework versions 1.0 and 1.1, this object was a `CoClass` object created from COM.</span></span> <span data-ttu-id="78ec0-131">En la versión .NET Framework 2,0, este objeto ya no es un `CoClass` objeto.</span><span class="sxs-lookup"><span data-stu-id="78ec0-131">In the .NET Framework version 2.0, this object is no longer a `CoClass` object.</span></span> <span data-ttu-id="78ec0-132">Debe crearse mediante la función [CreateDebuggingInterfaceFromVersion (](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) , que es más compatible con la versión.</span><span class="sxs-lookup"><span data-stu-id="78ec0-132">It must be created by the [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) function, which is more version-aware.</span></span> <span data-ttu-id="78ec0-133">Esta nueva función de creación permite a los clientes obtener una implementación `ICorDebug`específica de, que también emula una versión específica de la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="78ec0-133">This new creation function enables clients to get a specific implementation of `ICorDebug`, which also emulates a specific version of the debugging API.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="78ec0-134">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="78ec0-134">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78ec0-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="78ec0-135">Requirements</span></span>  
 <span data-ttu-id="78ec0-136">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78ec0-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78ec0-137">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="78ec0-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="78ec0-138">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="78ec0-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="78ec0-139">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78ec0-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78ec0-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="78ec0-140">See also</span></span>

- [<span data-ttu-id="78ec0-141">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="78ec0-141">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
