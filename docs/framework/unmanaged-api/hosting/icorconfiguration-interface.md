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
ms.openlocfilehash: fa8d15bc8e504a57d5cc87c170a3a5b022798add
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715789"
---
# <a name="icorconfiguration-interface"></a><span data-ttu-id="bf795-102">ICorConfiguration (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bf795-102">ICorConfiguration Interface</span></span>

<span data-ttu-id="bf795-103">Proporciona métodos para configurar el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="bf795-103">Provides methods for configuring the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bf795-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="bf795-104">Methods</span></span>  
  
|<span data-ttu-id="bf795-105">Método</span><span class="sxs-lookup"><span data-stu-id="bf795-105">Method</span></span>|<span data-ttu-id="bf795-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf795-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bf795-107">Método AddDebuggerSpecialThread</span><span class="sxs-lookup"><span data-stu-id="bf795-107">AddDebuggerSpecialThread Method</span></span>](icorconfiguration-adddebuggerspecialthread-method.md)|<span data-ttu-id="bf795-108">Indica a los servicios de depuración que se debe permitir que un subproceso determinado se siga ejecutando mientras el depurador tiene una aplicación detenida durante escenarios de depuración administrados o no administrados.</span><span class="sxs-lookup"><span data-stu-id="bf795-108">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>|  
|[<span data-ttu-id="bf795-109">Método SetDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="bf795-109">SetDebuggerThreadControl Method</span></span>](icorconfiguration-setdebuggerthreadcontrol-method.md)|<span data-ttu-id="bf795-110">Establece la interfaz de devolución de llamada a la que los servicios de depuración llamarán cuando los subprocesos CLR se bloquean y desbloquean para la depuración.</span><span class="sxs-lookup"><span data-stu-id="bf795-110">Sets the callback interface that the debugging services will call as CLR threads are blocked and unblocked for debugging.</span></span>|  
|[<span data-ttu-id="bf795-111">Método SetGCHostControl</span><span class="sxs-lookup"><span data-stu-id="bf795-111">SetGCHostControl Method</span></span>](icorconfiguration-setgchostcontrol-method.md)|<span data-ttu-id="bf795-112">Establece la interfaz de devolución de llamada que va a utilizar el recolector de elementos no utilizados para solicitar al host que cambie los límites de la memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="bf795-112">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>|  
|[<span data-ttu-id="bf795-113">Método SetGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="bf795-113">SetGCThreadControl Method</span></span>](icorconfiguration-setgcthreadcontrol-method.md)|<span data-ttu-id="bf795-114">Establece la interfaz de devolución de llamada para programar subprocesos para tareas no en tiempo de ejecución que, de lo contrario, se bloquearían para una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="bf795-114">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bf795-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bf795-115">Requirements</span></span>  

 <span data-ttu-id="bf795-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf795-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf795-117">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="bf795-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bf795-118">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bf795-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bf795-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf795-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf795-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bf795-120">See also</span></span>

- [<span data-ttu-id="bf795-121">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="bf795-121">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="bf795-122">CorRuntimeHost (Coclase)</span><span class="sxs-lookup"><span data-stu-id="bf795-122">CorRuntimeHost Coclass</span></span>](corruntimehost-coclass.md)
