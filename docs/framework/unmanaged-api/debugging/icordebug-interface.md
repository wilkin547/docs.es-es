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
ms.openlocfilehash: 193232ce1006a9cf209db9330343386404948440
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168290"
---
# <a name="icordebug-interface"></a><span data-ttu-id="6dfc5-102">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6dfc5-102">ICorDebug Interface</span></span>
<span data-ttu-id="6dfc5-103">Proporciona métodos que permiten a los desarrolladores depurar aplicaciones en el entorno de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="6dfc5-103">Provides methods that allow developers to debug applications in the common language runtime (CLR) environment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6dfc5-104">No se admite la depuración en modo mixto (código administrado y nativo) en Windows 95, Windows 98 o Windows Millennium Edition o en plataformas que no sean x86 (por ejemplo, IA64 y AMD64).</span><span class="sxs-lookup"><span data-stu-id="6dfc5-104">Mixed-mode (managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA64 and AMD64).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6dfc5-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="6dfc5-105">Methods</span></span>  
  
|<span data-ttu-id="6dfc5-106">Método</span><span class="sxs-lookup"><span data-stu-id="6dfc5-106">Method</span></span>|<span data-ttu-id="6dfc5-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="6dfc5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6dfc5-108">Método CanLaunchOrAttach</span><span class="sxs-lookup"><span data-stu-id="6dfc5-108">CanLaunchOrAttach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-canlaunchorattach-method.md)|<span data-ttu-id="6dfc5-109">Determina si inicia un proceso nuevo o asociar al proceso especificado es posible dentro del contexto de la configuración actual de la máquina y en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-109">Determines whether launching a new process or attaching to the given process is possible within the context of the current machine and runtime configuration.</span></span>|  
|[<span data-ttu-id="6dfc5-110">Método CreateProcess</span><span class="sxs-lookup"><span data-stu-id="6dfc5-110">CreateProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md)|<span data-ttu-id="6dfc5-111">Inicia un proceso y su subproceso principal bajo el control del depurador.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-111">Launches a process and its primary thread under the control of the debugger.</span></span>|  
|[<span data-ttu-id="6dfc5-112">Método DebugActiveProcess</span><span class="sxs-lookup"><span data-stu-id="6dfc5-112">DebugActiveProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md)|<span data-ttu-id="6dfc5-113">Asocia al depurador a un proceso existente.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-113">Attaches the debugger to an existing process.</span></span>|  
|[<span data-ttu-id="6dfc5-114">Método EnumerateProcesses</span><span class="sxs-lookup"><span data-stu-id="6dfc5-114">EnumerateProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-enumerateprocesses-method.md)|<span data-ttu-id="6dfc5-115">Obtiene un enumerador para los procesos que se están depurando.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-115">Gets an enumerator for the processes that are being debugged.</span></span>|  
|[<span data-ttu-id="6dfc5-116">Método GetProcess</span><span class="sxs-lookup"><span data-stu-id="6dfc5-116">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-getprocess-method.md)|<span data-ttu-id="6dfc5-117">Devuelve el objeto "ICorDebugProcess" con el identificador de proceso determinado.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-117">Returns the "ICorDebugProcess" object with the given process ID.</span></span>|  
|[<span data-ttu-id="6dfc5-118">Método Initialize</span><span class="sxs-lookup"><span data-stu-id="6dfc5-118">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md)|<span data-ttu-id="6dfc5-119">Inicializa el objeto `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-119">Initializes the `ICorDebug` object.</span></span>|  
|[<span data-ttu-id="6dfc5-120">Método SetManagedHandler</span><span class="sxs-lookup"><span data-stu-id="6dfc5-120">SetManagedHandler Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md)|<span data-ttu-id="6dfc5-121">Especifica el objeto de controlador de eventos para eventos administrados.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-121">Specifies the event handler object for managed events.</span></span>|  
|[<span data-ttu-id="6dfc5-122">Método SetUnmanagedHandler</span><span class="sxs-lookup"><span data-stu-id="6dfc5-122">SetUnmanagedHandler Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-setunmanagedhandler-method.md)|<span data-ttu-id="6dfc5-123">Especifica el objeto de controlador de eventos para eventos no administrados.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-123">Specifies the event handler object for unmanaged events.</span></span>|  
|[<span data-ttu-id="6dfc5-124">Método Terminate</span><span class="sxs-lookup"><span data-stu-id="6dfc5-124">Terminate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md)|<span data-ttu-id="6dfc5-125">Finaliza el `ICorDebug` objeto.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-125">Terminates the `ICorDebug` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6dfc5-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6dfc5-126">Remarks</span></span>  
 `ICorDebug` <span data-ttu-id="6dfc5-127">Representa un bucle de procesamiento de eventos para un proceso de depuración.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-127">represents an event processing loop for a debugger process.</span></span> <span data-ttu-id="6dfc5-128">El depurador debe esperar el [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) de todos los procesos que se está depurando antes de liberar esta interfaz de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-128">The debugger must wait for the [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback from all processes being debugged before releasing this interface.</span></span>  
  
 <span data-ttu-id="6dfc5-129">La `ICorDebug` objeto es el objeto inicial para controlar la depuración administrada todo aún más.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-129">The `ICorDebug` object is the initial object to control all further managed debugging.</span></span> <span data-ttu-id="6dfc5-130">En las versiones 1.0 y 1.1 de .NET Framework, este objeto era un `CoClass` objeto creado desde COM.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-130">In the .NET Framework versions 1.0 and 1.1, this object was a `CoClass` object created from COM.</span></span> <span data-ttu-id="6dfc5-131">En la versión 2.0 de .NET Framework, este objeto ya no es un `CoClass` objeto.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-131">In the .NET Framework version 2.0, this object is no longer a `CoClass` object.</span></span> <span data-ttu-id="6dfc5-132">Debe crearse mediante el [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) función, que es más consciente de versión.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-132">It must be created by the [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) function, which is more version-aware.</span></span> <span data-ttu-id="6dfc5-133">Esta nueva función de creación permite a los clientes obtener una implementación específica de `ICorDebug`, que también emula una versión específica de la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-133">This new creation function enables clients to get a specific implementation of `ICorDebug`, which also emulates a specific version of the debugging API.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6dfc5-134">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="6dfc5-134">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6dfc5-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6dfc5-135">Requirements</span></span>  
 <span data-ttu-id="6dfc5-136">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6dfc5-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6dfc5-137">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6dfc5-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6dfc5-138">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6dfc5-138">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="6dfc5-139">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="6dfc5-139">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6dfc5-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="6dfc5-140">See also</span></span>

- [<span data-ttu-id="6dfc5-141">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="6dfc5-141">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
