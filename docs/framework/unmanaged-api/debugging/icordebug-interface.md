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
ms.openlocfilehash: 66b50bad0e8d2622922da96c213643ac3be83a9e
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895370"
---
# <a name="icordebug-interface"></a><span data-ttu-id="9868a-102">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9868a-102">ICorDebug Interface</span></span>
<span data-ttu-id="9868a-103">Proporciona métodos que permiten a los desarrolladores depurar aplicaciones en el entorno de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="9868a-103">Provides methods that allow developers to debug applications in the common language runtime (CLR) environment.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9868a-104">La depuración en modo mixto (código administrado y nativo) no se admite en Windows 95, Windows 98 ni Windows ME, ni en plataformas que no son x86 (como IA64 y AMD64).</span><span class="sxs-lookup"><span data-stu-id="9868a-104">Mixed-mode (managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA64 and AMD64).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9868a-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="9868a-105">Methods</span></span>  
  
|<span data-ttu-id="9868a-106">Método</span><span class="sxs-lookup"><span data-stu-id="9868a-106">Method</span></span>|<span data-ttu-id="9868a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9868a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9868a-108">Método CanLaunchOrAttach</span><span class="sxs-lookup"><span data-stu-id="9868a-108">CanLaunchOrAttach Method</span></span>](icordebug-canlaunchorattach-method.md)|<span data-ttu-id="9868a-109">Determina si el inicio de un nuevo proceso o la asociación al proceso dado es posible en el contexto del equipo actual y de la configuración en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9868a-109">Determines whether launching a new process or attaching to the given process is possible within the context of the current machine and runtime configuration.</span></span>|  
|[<span data-ttu-id="9868a-110">Método CreateProcess</span><span class="sxs-lookup"><span data-stu-id="9868a-110">CreateProcess Method</span></span>](icordebug-createprocess-method.md)|<span data-ttu-id="9868a-111">Inicia un proceso y su subproceso primario bajo el control del depurador.</span><span class="sxs-lookup"><span data-stu-id="9868a-111">Launches a process and its primary thread under the control of the debugger.</span></span>|  
|[<span data-ttu-id="9868a-112">Método DebugActiveProcess</span><span class="sxs-lookup"><span data-stu-id="9868a-112">DebugActiveProcess Method</span></span>](icordebug-debugactiveprocess-method.md)|<span data-ttu-id="9868a-113">Asocia el depurador a un proceso existente.</span><span class="sxs-lookup"><span data-stu-id="9868a-113">Attaches the debugger to an existing process.</span></span>|  
|[<span data-ttu-id="9868a-114">Método EnumerateProcesses</span><span class="sxs-lookup"><span data-stu-id="9868a-114">EnumerateProcesses Method</span></span>](icordebug-enumerateprocesses-method.md)|<span data-ttu-id="9868a-115">Obtiene un enumerador para los procesos que se están depurando.</span><span class="sxs-lookup"><span data-stu-id="9868a-115">Gets an enumerator for the processes that are being debugged.</span></span>|  
|[<span data-ttu-id="9868a-116">Método GetProcess</span><span class="sxs-lookup"><span data-stu-id="9868a-116">GetProcess Method</span></span>](icordebug-getprocess-method.md)|<span data-ttu-id="9868a-117">Devuelve el objeto "ICorDebugProcess" con el identificador de proceso especificado.</span><span class="sxs-lookup"><span data-stu-id="9868a-117">Returns the "ICorDebugProcess" object with the given process ID.</span></span>|  
|[<span data-ttu-id="9868a-118">Método Initialize</span><span class="sxs-lookup"><span data-stu-id="9868a-118">Initialize Method</span></span>](icordebug-initialize-method.md)|<span data-ttu-id="9868a-119">Inicializa el objeto `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="9868a-119">Initializes the `ICorDebug` object.</span></span>|  
|[<span data-ttu-id="9868a-120">Método SetManagedHandler</span><span class="sxs-lookup"><span data-stu-id="9868a-120">SetManagedHandler Method</span></span>](icordebug-setmanagedhandler-method.md)|<span data-ttu-id="9868a-121">Especifica el objeto de controlador de eventos para los eventos administrados.</span><span class="sxs-lookup"><span data-stu-id="9868a-121">Specifies the event handler object for managed events.</span></span>|  
|[<span data-ttu-id="9868a-122">Método SetUnmanagedHandler</span><span class="sxs-lookup"><span data-stu-id="9868a-122">SetUnmanagedHandler Method</span></span>](icordebug-setunmanagedhandler-method.md)|<span data-ttu-id="9868a-123">Especifica el objeto de controlador de eventos para los eventos no administrados.</span><span class="sxs-lookup"><span data-stu-id="9868a-123">Specifies the event handler object for unmanaged events.</span></span>|  
|[<span data-ttu-id="9868a-124">Terminate (Método)</span><span class="sxs-lookup"><span data-stu-id="9868a-124">Terminate Method</span></span>](icordebug-terminate-method.md)|<span data-ttu-id="9868a-125">Finaliza el `ICorDebug` objeto.</span><span class="sxs-lookup"><span data-stu-id="9868a-125">Terminates the `ICorDebug` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9868a-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9868a-126">Remarks</span></span>  
 <span data-ttu-id="9868a-127">`ICorDebug`representa un bucle de procesamiento de eventos para un proceso del depurador.</span><span class="sxs-lookup"><span data-stu-id="9868a-127">`ICorDebug` represents an event processing loop for a debugger process.</span></span> <span data-ttu-id="9868a-128">El depurador debe esperar a la devolución de llamada [ICorDebugManagedCallback:: ExitProcess](icordebugmanagedcallback-exitprocess-method.md) de todos los procesos que se están depurando antes de liberar esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="9868a-128">The debugger must wait for the [ICorDebugManagedCallback::ExitProcess](icordebugmanagedcallback-exitprocess-method.md) callback from all processes being debugged before releasing this interface.</span></span>  
  
 <span data-ttu-id="9868a-129">El `ICorDebug` objeto es el objeto inicial para controlar toda la depuración administrada.</span><span class="sxs-lookup"><span data-stu-id="9868a-129">The `ICorDebug` object is the initial object to control all further managed debugging.</span></span> <span data-ttu-id="9868a-130">En las versiones 1,0 y 1,1 de .NET Framework, este objeto era `CoClass` un objeto creado a partir de com.</span><span class="sxs-lookup"><span data-stu-id="9868a-130">In the .NET Framework versions 1.0 and 1.1, this object was a `CoClass` object created from COM.</span></span> <span data-ttu-id="9868a-131">En la versión .NET Framework 2,0, este objeto ya no es un `CoClass` objeto.</span><span class="sxs-lookup"><span data-stu-id="9868a-131">In the .NET Framework version 2.0, this object is no longer a `CoClass` object.</span></span> <span data-ttu-id="9868a-132">Debe crearse mediante la función [CreateDebuggingInterfaceFromVersion (](../hosting/createdebugginginterfacefromversion-function.md) , que es más compatible con la versión.</span><span class="sxs-lookup"><span data-stu-id="9868a-132">It must be created by the [CreateDebuggingInterfaceFromVersion](../hosting/createdebugginginterfacefromversion-function.md) function, which is more version-aware.</span></span> <span data-ttu-id="9868a-133">Esta nueva función de creación permite a los clientes obtener una implementación `ICorDebug`específica de, que también emula una versión específica de la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="9868a-133">This new creation function enables clients to get a specific implementation of `ICorDebug`, which also emulates a specific version of the debugging API.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9868a-134">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="9868a-134">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9868a-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9868a-135">Requirements</span></span>  
 <span data-ttu-id="9868a-136">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9868a-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9868a-137">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9868a-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9868a-138">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9868a-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9868a-139">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9868a-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9868a-140">Consulta también</span><span class="sxs-lookup"><span data-stu-id="9868a-140">See also</span></span>

- [<span data-ttu-id="9868a-141">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="9868a-141">Debugging Interfaces</span></span>](debugging-interfaces.md)
