---
title: ICorConfiguration (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorConfiguration
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorConfiguration
helpviewer_keywords: ICorConfiguration interface [.NET Framework hosting]
ms.assetid: aaf96116-372b-4538-afb1-9e0fcdac1f98
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6bc66abf28e90d858d993bd62e9c67f840af137b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorconfiguration-interface"></a><span data-ttu-id="ede00-102">ICorConfiguration (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ede00-102">ICorConfiguration Interface</span></span>
<span data-ttu-id="ede00-103">Proporciona métodos para la configuración de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="ede00-103">Provides methods for configuring the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ede00-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="ede00-104">Methods</span></span>  
  
|<span data-ttu-id="ede00-105">Método</span><span class="sxs-lookup"><span data-stu-id="ede00-105">Method</span></span>|<span data-ttu-id="ede00-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ede00-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ede00-107">AddDebuggerSpecialThread (método)</span><span class="sxs-lookup"><span data-stu-id="ede00-107">AddDebuggerSpecialThread Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-adddebuggerspecialthread-method.md)|<span data-ttu-id="ede00-108">Indica a los servicios de depuración que se debe permitir un subproceso determinado continúe ejecutándose mientras el depurador tiene una aplicación detenida en escenarios de depuración administrados o no administrados.</span><span class="sxs-lookup"><span data-stu-id="ede00-108">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>|  
|[<span data-ttu-id="ede00-109">SetDebuggerThreadControl (método)</span><span class="sxs-lookup"><span data-stu-id="ede00-109">SetDebuggerThreadControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setdebuggerthreadcontrol-method.md)|<span data-ttu-id="ede00-110">Establece la interfaz de devolución de llamada que los servicios de depuración llamará como subprocesos CLR se bloqueen y desbloqueen para la depuración.</span><span class="sxs-lookup"><span data-stu-id="ede00-110">Sets the callback interface that the debugging services will call as CLR threads are blocked and unblocked for debugging.</span></span>|  
|[<span data-ttu-id="ede00-111">SetGCHostControl (método)</span><span class="sxs-lookup"><span data-stu-id="ede00-111">SetGCHostControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgchostcontrol-method.md)|<span data-ttu-id="ede00-112">Establece la interfaz de devolución de llamada para su uso por el recolector de elementos no utilizados para solicitar al host que cambie los límites de memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="ede00-112">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>|  
|[<span data-ttu-id="ede00-113">SetGCThreadControl (método)</span><span class="sxs-lookup"><span data-stu-id="ede00-113">SetGCThreadControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgcthreadcontrol-method.md)|<span data-ttu-id="ede00-114">Establece la interfaz de devolución de llamada para programar los subprocesos para tareas no en tiempo de ejecución que de lo contrario estarían bloqueados para una colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ede00-114">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ede00-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ede00-115">Requirements</span></span>  
 <span data-ttu-id="ede00-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ede00-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ede00-117">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ede00-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ede00-118">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ede00-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ede00-119">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ede00-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ede00-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="ede00-120">See Also</span></span>  
 [<span data-ttu-id="ede00-121">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="ede00-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="ede00-122">CorRuntimeHost (Coclase)</span><span class="sxs-lookup"><span data-stu-id="ede00-122">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
