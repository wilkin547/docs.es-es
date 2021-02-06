---
description: 'Más información acerca de: interfaz ICorConfiguration'
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
ms.openlocfilehash: f75e9e445c7fe4615abcae27756bcc420b5255b2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636694"
---
# <a name="icorconfiguration-interface"></a><span data-ttu-id="151a9-103">ICorConfiguration (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="151a9-103">ICorConfiguration Interface</span></span>

<span data-ttu-id="151a9-104">Proporciona métodos para configurar el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="151a9-104">Provides methods for configuring the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="151a9-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="151a9-105">Methods</span></span>  
  
|<span data-ttu-id="151a9-106">Método</span><span class="sxs-lookup"><span data-stu-id="151a9-106">Method</span></span>|<span data-ttu-id="151a9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="151a9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="151a9-108">Método AddDebuggerSpecialThread</span><span class="sxs-lookup"><span data-stu-id="151a9-108">AddDebuggerSpecialThread Method</span></span>](icorconfiguration-adddebuggerspecialthread-method.md)|<span data-ttu-id="151a9-109">Indica a los servicios de depuración que se debe permitir que un subproceso determinado se siga ejecutando mientras el depurador tiene una aplicación detenida durante escenarios de depuración administrados o no administrados.</span><span class="sxs-lookup"><span data-stu-id="151a9-109">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>|  
|[<span data-ttu-id="151a9-110">Método SetDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="151a9-110">SetDebuggerThreadControl Method</span></span>](icorconfiguration-setdebuggerthreadcontrol-method.md)|<span data-ttu-id="151a9-111">Establece la interfaz de devolución de llamada a la que los servicios de depuración llamarán cuando los subprocesos CLR se bloquean y desbloquean para la depuración.</span><span class="sxs-lookup"><span data-stu-id="151a9-111">Sets the callback interface that the debugging services will call as CLR threads are blocked and unblocked for debugging.</span></span>|  
|[<span data-ttu-id="151a9-112">Método SetGCHostControl</span><span class="sxs-lookup"><span data-stu-id="151a9-112">SetGCHostControl Method</span></span>](icorconfiguration-setgchostcontrol-method.md)|<span data-ttu-id="151a9-113">Establece la interfaz de devolución de llamada que va a utilizar el recolector de elementos no utilizados para solicitar al host que cambie los límites de la memoria virtual.</span><span class="sxs-lookup"><span data-stu-id="151a9-113">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>|  
|[<span data-ttu-id="151a9-114">Método SetGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="151a9-114">SetGCThreadControl Method</span></span>](icorconfiguration-setgcthreadcontrol-method.md)|<span data-ttu-id="151a9-115">Establece la interfaz de devolución de llamada para programar subprocesos para tareas no en tiempo de ejecución que, de lo contrario, se bloquearían para una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="151a9-115">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="151a9-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="151a9-116">Requirements</span></span>  

 <span data-ttu-id="151a9-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="151a9-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="151a9-118">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="151a9-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="151a9-119">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="151a9-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="151a9-120">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="151a9-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="151a9-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="151a9-121">See also</span></span>

- [<span data-ttu-id="151a9-122">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="151a9-122">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="151a9-123">CorRuntimeHost (Coclase)</span><span class="sxs-lookup"><span data-stu-id="151a9-123">CorRuntimeHost Coclass</span></span>](corruntimehost-coclass.md)
