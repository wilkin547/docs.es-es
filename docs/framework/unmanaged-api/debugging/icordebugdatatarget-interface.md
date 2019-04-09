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
ms.openlocfilehash: 480fc27bd41f7ca559ceee379b7f6f81c94da0ba
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59188713"
---
# <a name="icordebugdatatarget-interface"></a><span data-ttu-id="813f3-102">ICorDebugDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="813f3-102">ICorDebugDataTarget Interface</span></span>
<span data-ttu-id="813f3-103">Proporciona una interfaz de devolución de llamada que brinda acceso a un proceso de destino determinado.</span><span class="sxs-lookup"><span data-stu-id="813f3-103">Provides a callback interface that provides access to a particular target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="813f3-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="813f3-104">Methods</span></span>  
  
|<span data-ttu-id="813f3-105">Método</span><span class="sxs-lookup"><span data-stu-id="813f3-105">Method</span></span>|<span data-ttu-id="813f3-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="813f3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="813f3-107">Método GetPlatform</span><span class="sxs-lookup"><span data-stu-id="813f3-107">GetPlatform Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)|<span data-ttu-id="813f3-108">Proporciona información acerca de la plataforma, incluida la arquitectura de procesador y del sistema operativo, en el que se está ejecutando el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="813f3-108">Provides information about the platform, including processor architecture and operating system, on which the target process is running.</span></span>|  
|[<span data-ttu-id="813f3-109">Método ReadVirtual</span><span class="sxs-lookup"><span data-stu-id="813f3-109">ReadVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-readvirtual-method.md)|<span data-ttu-id="813f3-110">Obtiene un bloque de memoria contigua a partir de la dirección especificada y lo devuelve en el búfer proporcionado.</span><span class="sxs-lookup"><span data-stu-id="813f3-110">Gets a block of contiguous memory starting at the specified address, and returns it in the supplied buffer.</span></span>|  
|[<span data-ttu-id="813f3-111">Método GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="813f3-111">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getthreadcontext-method.md)|<span data-ttu-id="813f3-112">Solicita el contexto del subproceso actual para el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="813f3-112">Requests the current thread context for the specified thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="813f3-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="813f3-113">Remarks</span></span>  
 `ICorDebugDataTarget` <span data-ttu-id="813f3-114">y sus métodos tienen las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="813f3-114">and its methods have the following characteristics:</span></span>  
  
-   <span data-ttu-id="813f3-115">Los servicios de depuración, llamar a métodos en esta interfaz para tener acceso a memoria y otros datos en el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="813f3-115">The debugging services call methods on this interface to access memory and other data in the target process.</span></span>  
  
-   <span data-ttu-id="813f3-116">El cliente del depurador debe implementar esta interfaz según corresponda para el destino concreto (por ejemplo, un proceso activo o un volcado de memoria).</span><span class="sxs-lookup"><span data-stu-id="813f3-116">The debugger client must implement this interface as appropriate for the particular target (for example, a live process or a memory dump).</span></span>  
  
-   <span data-ttu-id="813f3-117">El `ICorDebugDataTarget` métodos pueden invocarse únicamente desde dentro de los métodos implementados en otra `ICorDebug*` interfaces.</span><span class="sxs-lookup"><span data-stu-id="813f3-117">The `ICorDebugDataTarget` methods can be invoked only from within methods implemented in other `ICorDebug*` interfaces.</span></span> <span data-ttu-id="813f3-118">Esto garantiza que el cliente del depurador tiene control sobre qué subproceso se invoca y cuándo.</span><span class="sxs-lookup"><span data-stu-id="813f3-118">This ensures that the debugger client has control over which thread it is invoked on, and when.</span></span>  
  
-   <span data-ttu-id="813f3-119">El `ICorDebugDataTarget` implementación siempre debe devolver información actualizada sobre el destino.</span><span class="sxs-lookup"><span data-stu-id="813f3-119">The `ICorDebugDataTarget` implementation must always return up-to-date information about the target.</span></span>  
  
 <span data-ttu-id="813f3-120">El proceso de destino debe ser detenido y no puede cambiar de ninguna manera al `ICorDebug*` interfaces (y, por tanto, `ICorDebugDataTarget` métodos) se llama a.</span><span class="sxs-lookup"><span data-stu-id="813f3-120">The target process should be stopped and not changed in any way while `ICorDebug*` interfaces (and therefore `ICorDebugDataTarget` methods) are being called.</span></span> <span data-ttu-id="813f3-121">Si el destino es un proceso activo y su estado cambia, el [ICLRDebugging:: OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) método debe llamarse para proporcionar una instancia de ICorDebugProcess de reemplazo.</span><span class="sxs-lookup"><span data-stu-id="813f3-121">If the target is a live process and its state changes, the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method has to be called again to provide a replacement ICorDebugProcess instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="813f3-122">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="813f3-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="813f3-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="813f3-123">Requirements</span></span>  
 <span data-ttu-id="813f3-124">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="813f3-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="813f3-125">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="813f3-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="813f3-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="813f3-126">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="813f3-127">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="813f3-127">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="813f3-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="813f3-128">See also</span></span>

- [<span data-ttu-id="813f3-129">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="813f3-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="813f3-130">Depuración</span><span class="sxs-lookup"><span data-stu-id="813f3-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
