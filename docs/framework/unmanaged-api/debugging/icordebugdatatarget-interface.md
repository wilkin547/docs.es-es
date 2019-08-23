---
title: ICorDebugDataTarget (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget
helpviewer_keywords:
- ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: df5f05be-bed7-4f3c-bc89-dbb435d79a0b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c6a8ee1bcc65e640ef871e57acdeef21acd7896
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930833"
---
# <a name="icordebugdatatarget-interface"></a><span data-ttu-id="4d278-102">ICorDebugDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4d278-102">ICorDebugDataTarget Interface</span></span>
<span data-ttu-id="4d278-103">Proporciona una interfaz de devolución de llamada que brinda acceso a un proceso de destino determinado.</span><span class="sxs-lookup"><span data-stu-id="4d278-103">Provides a callback interface that provides access to a particular target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4d278-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="4d278-104">Methods</span></span>  
  
|<span data-ttu-id="4d278-105">Método</span><span class="sxs-lookup"><span data-stu-id="4d278-105">Method</span></span>|<span data-ttu-id="4d278-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4d278-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4d278-107">GetPlatform (método)</span><span class="sxs-lookup"><span data-stu-id="4d278-107">GetPlatform Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)|<span data-ttu-id="4d278-108">Proporciona información sobre la plataforma, incluida la arquitectura del procesador y el sistema operativo, en la que se ejecuta el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="4d278-108">Provides information about the platform, including processor architecture and operating system, on which the target process is running.</span></span>|  
|[<span data-ttu-id="4d278-109">ReadVirtual (método)</span><span class="sxs-lookup"><span data-stu-id="4d278-109">ReadVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-readvirtual-method.md)|<span data-ttu-id="4d278-110">Obtiene un bloque de memoria contigua que comienza en la dirección especificada y lo devuelve en el búfer proporcionado.</span><span class="sxs-lookup"><span data-stu-id="4d278-110">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>|  
|[<span data-ttu-id="4d278-111">GetThreadContext (método)</span><span class="sxs-lookup"><span data-stu-id="4d278-111">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getthreadcontext-method.md)|<span data-ttu-id="4d278-112">Solicita el contexto del subproceso actual para el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="4d278-112">Requests the current thread context for the specified thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d278-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4d278-113">Remarks</span></span>  
 <span data-ttu-id="4d278-114">`ICorDebugDataTarget`y sus métodos tienen las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="4d278-114">`ICorDebugDataTarget` and its methods have the following characteristics:</span></span>  
  
- <span data-ttu-id="4d278-115">Los servicios de depuración llaman a métodos en esta interfaz para tener acceso a la memoria y a otros datos en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="4d278-115">The debugging services call methods on this interface to access memory and other data in the target process.</span></span>  
  
- <span data-ttu-id="4d278-116">El cliente del depurador debe implementar esta interfaz según corresponda para el destino determinado (por ejemplo, un proceso activo o un volcado de memoria).</span><span class="sxs-lookup"><span data-stu-id="4d278-116">The debugger client must implement this interface as appropriate for the particular target (for example, a live process or a memory dump).</span></span>  
  
- <span data-ttu-id="4d278-117">Los `ICorDebugDataTarget` métodos solo se pueden invocar desde los métodos implementados en `ICorDebug*` otras interfaces.</span><span class="sxs-lookup"><span data-stu-id="4d278-117">The `ICorDebugDataTarget` methods can be invoked only from within methods implemented in other `ICorDebug*` interfaces.</span></span> <span data-ttu-id="4d278-118">Esto garantiza que el cliente del depurador tenga control sobre el subproceso en el que se invoca y cuándo.</span><span class="sxs-lookup"><span data-stu-id="4d278-118">This ensures that the debugger client has control over which thread it is invoked on, and when.</span></span>  
  
- <span data-ttu-id="4d278-119">La `ICorDebugDataTarget` implementación siempre debe devolver información actualizada sobre el destino.</span><span class="sxs-lookup"><span data-stu-id="4d278-119">The `ICorDebugDataTarget` implementation must always return up-to-date information about the target.</span></span>  
  
 <span data-ttu-id="4d278-120">El proceso de destino debe detenerse y no cambiarse de `ICorDebug*` ninguna manera mientras se `ICorDebugDataTarget` llama a las interfaces (y, por lo tanto, a los métodos).</span><span class="sxs-lookup"><span data-stu-id="4d278-120">The target process should be stopped and not changed in any way while `ICorDebug*` interfaces (and therefore `ICorDebugDataTarget` methods) are being called.</span></span> <span data-ttu-id="4d278-121">Si el destino es un proceso activo y su estado cambia, se debe llamar de nuevo al método [ICLRDebugging:: openvirtualprocess (](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) para proporcionar una instancia de ICorDebugProcess de reemplazo.</span><span class="sxs-lookup"><span data-stu-id="4d278-121">If the target is a live process and its state changes, the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method has to be called again to provide a replacement ICorDebugProcess instance.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4d278-122">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="4d278-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d278-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4d278-123">Requirements</span></span>  
 <span data-ttu-id="4d278-124">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d278-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d278-125">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="4d278-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d278-126">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d278-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d278-127">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d278-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d278-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d278-128">See also</span></span>

- [<span data-ttu-id="4d278-129">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="4d278-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="4d278-130">Depuración</span><span class="sxs-lookup"><span data-stu-id="4d278-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
