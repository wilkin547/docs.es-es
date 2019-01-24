---
title: ICorConfiguration (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorConfiguration
helpviewer_keywords:
- ICorConfiguration interface [.NET Framework hosting]
ms.assetid: aaf96116-372b-4538-afb1-9e0fcdac1f98
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d7abd6b4ca97173cfecbabf1a8b90afcf3c48a1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554184"
---
# <a name="icorconfiguration-interface"></a><span data-ttu-id="ae9d3-102">ICorConfiguration (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ae9d3-102">ICorConfiguration Interface</span></span>
<span data-ttu-id="ae9d3-103">Proporciona métodos para la configuración de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="ae9d3-103">Provides methods for configuring the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ae9d3-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="ae9d3-104">Methods</span></span>  
  
|<span data-ttu-id="ae9d3-105">Método</span><span class="sxs-lookup"><span data-stu-id="ae9d3-105">Method</span></span>|<span data-ttu-id="ae9d3-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ae9d3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ae9d3-107">AddDebuggerSpecialThread (método)</span><span class="sxs-lookup"><span data-stu-id="ae9d3-107">AddDebuggerSpecialThread Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-adddebuggerspecialthread-method.md)|<span data-ttu-id="ae9d3-108">Indica a los servicios de depuración que un subproceso en particular debe permitirse seguirse ejecutando mientras el depurador tiene una aplicación detenida en escenarios de depuración administrados o no administrado.</span><span class="sxs-lookup"><span data-stu-id="ae9d3-108">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>|  
|[<span data-ttu-id="ae9d3-109">SetDebuggerThreadControl (método)</span><span class="sxs-lookup"><span data-stu-id="ae9d3-109">SetDebuggerThreadControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setdebuggerthreadcontrol-method.md)|<span data-ttu-id="ae9d3-110">Establece la interfaz de devolución de llamada que se llamará los servicios de depuración como subprocesos CLR se bloquea y desbloquea para la depuración.</span><span class="sxs-lookup"><span data-stu-id="ae9d3-110">Sets the callback interface that the debugging services will call as CLR threads are blocked and unblocked for debugging.</span></span>|  
|[<span data-ttu-id="ae9d3-111">SetGCHostControl (método)</span><span class="sxs-lookup"><span data-stu-id="ae9d3-111">SetGCHostControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgchostcontrol-method.md)|<span data-ttu-id="ae9d3-112">Establece la interfaz de devolución de llamada que se usará por el recolector de elementos no utilizados para solicitar al host que cambie los límites de memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="ae9d3-112">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>|  
|[<span data-ttu-id="ae9d3-113">SetGCThreadControl (método)</span><span class="sxs-lookup"><span data-stu-id="ae9d3-113">SetGCThreadControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgcthreadcontrol-method.md)|<span data-ttu-id="ae9d3-114">Establece la interfaz de devolución de llamada para la programación de subprocesos para tareas que no son de tiempo de ejecución que de lo contrario, se bloquearía para una colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ae9d3-114">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ae9d3-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ae9d3-115">Requirements</span></span>  
 <span data-ttu-id="ae9d3-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae9d3-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae9d3-117">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ae9d3-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ae9d3-118">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ae9d3-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ae9d3-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae9d3-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae9d3-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae9d3-120">See also</span></span>
- [<span data-ttu-id="ae9d3-121">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="ae9d3-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="ae9d3-122">CorRuntimeHost (coclase)</span><span class="sxs-lookup"><span data-stu-id="ae9d3-122">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
