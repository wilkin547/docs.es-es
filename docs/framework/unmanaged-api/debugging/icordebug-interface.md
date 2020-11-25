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
ms.openlocfilehash: 21838bdd8ff45f8f74524dc4da52364fb032b396
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723407"
---
# <a name="icordebug-interface"></a><span data-ttu-id="dd359-102">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dd359-102">ICorDebug Interface</span></span>

<span data-ttu-id="dd359-103">Proporciona métodos que permiten a los desarrolladores depurar aplicaciones en el entorno de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="dd359-103">Provides methods that allow developers to debug applications in the common language runtime (CLR) environment.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dd359-104">La depuración en modo mixto (código administrado y nativo) no se admite en Windows 95, Windows 98 ni Windows ME, ni en plataformas que no son x86 (como IA64 y AMD64).</span><span class="sxs-lookup"><span data-stu-id="dd359-104">Mixed-mode (managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA64 and AMD64).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dd359-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="dd359-105">Methods</span></span>  
  
|<span data-ttu-id="dd359-106">Método</span><span class="sxs-lookup"><span data-stu-id="dd359-106">Method</span></span>|<span data-ttu-id="dd359-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="dd359-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dd359-108">Método CanLaunchOrAttach</span><span class="sxs-lookup"><span data-stu-id="dd359-108">CanLaunchOrAttach Method</span></span>](icordebug-canlaunchorattach-method.md)|<span data-ttu-id="dd359-109">Determina si el inicio de un nuevo proceso o la asociación al proceso dado es posible en el contexto del equipo actual y de la configuración en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="dd359-109">Determines whether launching a new process or attaching to the given process is possible within the context of the current machine and runtime configuration.</span></span>|  
|[<span data-ttu-id="dd359-110">Método CreateProcess</span><span class="sxs-lookup"><span data-stu-id="dd359-110">CreateProcess Method</span></span>](icordebug-createprocess-method.md)|<span data-ttu-id="dd359-111">Inicia un proceso y su subproceso primario bajo el control del depurador.</span><span class="sxs-lookup"><span data-stu-id="dd359-111">Launches a process and its primary thread under the control of the debugger.</span></span>|  
|[<span data-ttu-id="dd359-112">Método DebugActiveProcess</span><span class="sxs-lookup"><span data-stu-id="dd359-112">DebugActiveProcess Method</span></span>](icordebug-debugactiveprocess-method.md)|<span data-ttu-id="dd359-113">Asocia el depurador a un proceso existente.</span><span class="sxs-lookup"><span data-stu-id="dd359-113">Attaches the debugger to an existing process.</span></span>|  
|[<span data-ttu-id="dd359-114">Método EnumerateProcesses</span><span class="sxs-lookup"><span data-stu-id="dd359-114">EnumerateProcesses Method</span></span>](icordebug-enumerateprocesses-method.md)|<span data-ttu-id="dd359-115">Obtiene un enumerador para los procesos que se están depurando.</span><span class="sxs-lookup"><span data-stu-id="dd359-115">Gets an enumerator for the processes that are being debugged.</span></span>|  
|[<span data-ttu-id="dd359-116">Método GetProcess</span><span class="sxs-lookup"><span data-stu-id="dd359-116">GetProcess Method</span></span>](icordebug-getprocess-method.md)|<span data-ttu-id="dd359-117">Devuelve el objeto "ICorDebugProcess" con el identificador de proceso especificado.</span><span class="sxs-lookup"><span data-stu-id="dd359-117">Returns the "ICorDebugProcess" object with the given process ID.</span></span>|  
|[<span data-ttu-id="dd359-118">Initialize (Método)</span><span class="sxs-lookup"><span data-stu-id="dd359-118">Initialize Method</span></span>](icordebug-initialize-method.md)|<span data-ttu-id="dd359-119">Inicializa el objeto `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="dd359-119">Initializes the `ICorDebug` object.</span></span>|  
|[<span data-ttu-id="dd359-120">Método SetManagedHandler</span><span class="sxs-lookup"><span data-stu-id="dd359-120">SetManagedHandler Method</span></span>](icordebug-setmanagedhandler-method.md)|<span data-ttu-id="dd359-121">Especifica el objeto de controlador de eventos para los eventos administrados.</span><span class="sxs-lookup"><span data-stu-id="dd359-121">Specifies the event handler object for managed events.</span></span>|  
|[<span data-ttu-id="dd359-122">Método SetUnmanagedHandler</span><span class="sxs-lookup"><span data-stu-id="dd359-122">SetUnmanagedHandler Method</span></span>](icordebug-setunmanagedhandler-method.md)|<span data-ttu-id="dd359-123">Especifica el objeto de controlador de eventos para los eventos no administrados.</span><span class="sxs-lookup"><span data-stu-id="dd359-123">Specifies the event handler object for unmanaged events.</span></span>|  
|[<span data-ttu-id="dd359-124">Terminate (Método)</span><span class="sxs-lookup"><span data-stu-id="dd359-124">Terminate Method</span></span>](icordebug-terminate-method.md)|<span data-ttu-id="dd359-125">Finaliza el `ICorDebug` objeto.</span><span class="sxs-lookup"><span data-stu-id="dd359-125">Terminates the `ICorDebug` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd359-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dd359-126">Remarks</span></span>  

 <span data-ttu-id="dd359-127">`ICorDebug` representa un bucle de procesamiento de eventos para un proceso del depurador.</span><span class="sxs-lookup"><span data-stu-id="dd359-127">`ICorDebug` represents an event processing loop for a debugger process.</span></span> <span data-ttu-id="dd359-128">El depurador debe esperar a la devolución de llamada [ICorDebugManagedCallback:: ExitProcess](icordebugmanagedcallback-exitprocess-method.md) de todos los procesos que se están depurando antes de liberar esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="dd359-128">The debugger must wait for the [ICorDebugManagedCallback::ExitProcess](icordebugmanagedcallback-exitprocess-method.md) callback from all processes being debugged before releasing this interface.</span></span>  
  
 <span data-ttu-id="dd359-129">El `ICorDebug` objeto es el objeto inicial para controlar toda la depuración administrada.</span><span class="sxs-lookup"><span data-stu-id="dd359-129">The `ICorDebug` object is the initial object to control all further managed debugging.</span></span> <span data-ttu-id="dd359-130">En las versiones 1,0 y 1,1 de .NET Framework, este objeto era un `CoClass` objeto creado a partir de com.</span><span class="sxs-lookup"><span data-stu-id="dd359-130">In the .NET Framework versions 1.0 and 1.1, this object was a `CoClass` object created from COM.</span></span> <span data-ttu-id="dd359-131">En la versión .NET Framework 2,0, este objeto ya no es un `CoClass` objeto.</span><span class="sxs-lookup"><span data-stu-id="dd359-131">In the .NET Framework version 2.0, this object is no longer a `CoClass` object.</span></span> <span data-ttu-id="dd359-132">Debe crearse mediante la función [CreateDebuggingInterfaceFromVersion (](../hosting/createdebugginginterfacefromversion-function.md) , que es más compatible con la versión.</span><span class="sxs-lookup"><span data-stu-id="dd359-132">It must be created by the [CreateDebuggingInterfaceFromVersion](../hosting/createdebugginginterfacefromversion-function.md) function, which is more version-aware.</span></span> <span data-ttu-id="dd359-133">Esta nueva función de creación permite a los clientes obtener una implementación específica de `ICorDebug` , que también emula una versión específica de la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="dd359-133">This new creation function enables clients to get a specific implementation of `ICorDebug`, which also emulates a specific version of the debugging API.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dd359-134">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="dd359-134">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd359-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dd359-135">Requirements</span></span>  

 <span data-ttu-id="dd359-136">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd359-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd359-137">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dd359-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dd359-138">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd359-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd359-139">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd359-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd359-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dd359-140">See also</span></span>

- [<span data-ttu-id="dd359-141">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="dd359-141">Debugging Interfaces</span></span>](debugging-interfaces.md)
