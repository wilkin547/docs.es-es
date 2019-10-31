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
ms.openlocfilehash: 80bb68486e555d6c96cf8ee56ed6d60e41c7c5c6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127802"
---
# <a name="icorconfiguration-interface"></a><span data-ttu-id="9b941-102">ICorConfiguration (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9b941-102">ICorConfiguration Interface</span></span>
<span data-ttu-id="9b941-103">Proporciona métodos para configurar el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="9b941-103">Provides methods for configuring the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9b941-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="9b941-104">Methods</span></span>  
  
|<span data-ttu-id="9b941-105">Método</span><span class="sxs-lookup"><span data-stu-id="9b941-105">Method</span></span>|<span data-ttu-id="9b941-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b941-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9b941-107">AddDebuggerSpecialThread (método)</span><span class="sxs-lookup"><span data-stu-id="9b941-107">AddDebuggerSpecialThread Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-adddebuggerspecialthread-method.md)|<span data-ttu-id="9b941-108">Indica a los servicios de depuración que se debe permitir que un subproceso determinado se siga ejecutando mientras el depurador tiene una aplicación detenida durante escenarios de depuración administrados o no administrados.</span><span class="sxs-lookup"><span data-stu-id="9b941-108">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>|  
|[<span data-ttu-id="9b941-109">SetDebuggerThreadControl (método)</span><span class="sxs-lookup"><span data-stu-id="9b941-109">SetDebuggerThreadControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setdebuggerthreadcontrol-method.md)|<span data-ttu-id="9b941-110">Establece la interfaz de devolución de llamada a la que los servicios de depuración llamarán cuando los subprocesos CLR se bloquean y desbloquean para la depuración.</span><span class="sxs-lookup"><span data-stu-id="9b941-110">Sets the callback interface that the debugging services will call as CLR threads are blocked and unblocked for debugging.</span></span>|  
|[<span data-ttu-id="9b941-111">SetGCHostControl (método)</span><span class="sxs-lookup"><span data-stu-id="9b941-111">SetGCHostControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgchostcontrol-method.md)|<span data-ttu-id="9b941-112">Establece la interfaz de devolución de llamada que va a utilizar el recolector de elementos no utilizados para solicitar al host que cambie los límites de la memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="9b941-112">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>|  
|[<span data-ttu-id="9b941-113">SetGCThreadControl (método)</span><span class="sxs-lookup"><span data-stu-id="9b941-113">SetGCThreadControl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgcthreadcontrol-method.md)|<span data-ttu-id="9b941-114">Establece la interfaz de devolución de llamada para programar subprocesos para tareas no en tiempo de ejecución que, de lo contrario, se bloquearían para una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="9b941-114">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9b941-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9b941-115">Requirements</span></span>  
 <span data-ttu-id="9b941-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b941-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b941-117">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9b941-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9b941-118">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9b941-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9b941-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b941-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b941-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b941-120">See also</span></span>

- [<span data-ttu-id="9b941-121">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="9b941-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="9b941-122">CorRuntimeHost (coclase)</span><span class="sxs-lookup"><span data-stu-id="9b941-122">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
