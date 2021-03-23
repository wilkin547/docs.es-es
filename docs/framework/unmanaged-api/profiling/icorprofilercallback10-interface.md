---
description: 'Más información acerca de: interfaz ICorProfilerCallback10'
title: Interfaz ICorProfilerCallback10
ms.date: 03/19/2021
api_name:
- ICorProfilerCallback10
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: d9091dc81307e2dcb83e74154a8217dffaa1e7a2
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805654"
---
# <a name="icorprofilercallback10-interface"></a><span data-ttu-id="26561-103">Interfaz ICorProfilerCallback10</span><span class="sxs-lookup"><span data-stu-id="26561-103">ICorProfilerCallback10 Interface</span></span>

 <span data-ttu-id="26561-104">Una subclase de [ICorProfilerCallback9](icorprofilercallback9-interface.md) que proporciona métodos de devolución de llamada para notificar al generador de perfiles que se han entregado eventos EventPipe a la sesión activa del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="26561-104">A subclass of [ICorProfilerCallback9](icorprofilercallback9-interface.md) that provides callback methods to notify the profiler that EventPipe events have been delivered to the profiler's currently active session.</span></span>
  
## <a name="methods"></a><span data-ttu-id="26561-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="26561-105">Methods</span></span>  
  
|<span data-ttu-id="26561-106">Método</span><span class="sxs-lookup"><span data-stu-id="26561-106">Method</span></span>|<span data-ttu-id="26561-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="26561-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="26561-108">Método EventPipeEventDelivered</span><span class="sxs-lookup"><span data-stu-id="26561-108">EventPipeEventDelivered Method</span></span>](icorprofilercallback10-eventpipeeventdelivered-method.md)|<span data-ttu-id="26561-109">Notifica al generador de perfiles que se ha entregado un evento EventPipe a la sesión que el generador de perfiles tiene abierto.</span><span class="sxs-lookup"><span data-stu-id="26561-109">Notifies the profiler that an EventPipe event has been delivered to the session that the profiler has open.</span></span>|
|[<span data-ttu-id="26561-110">Método EventPipeProviderCreated</span><span class="sxs-lookup"><span data-stu-id="26561-110">EventPipeProviderCreated Method</span></span>](icorprofilercallback10-eventpipeprovidercreated-method.md)|<span data-ttu-id="26561-111">Notifica al generador de perfiles que se ha creado un proveedor EventPipe, lo que permite al generador de perfiles agregar ese proveedor a su sesión.</span><span class="sxs-lookup"><span data-stu-id="26561-111">Notifies the profiler that an EventPipe provider has been created, allowing the profiler to add that provider the their session.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="26561-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="26561-112">Requirements</span></span>  

<span data-ttu-id="26561-113">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="26561-113">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>  
<span data-ttu-id="26561-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="26561-114">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="26561-115">**Versiones de .net:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26561-115">**.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="26561-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="26561-116">See also</span></span>

- [<span data-ttu-id="26561-117">Información general sobre EventPipe</span><span class="sxs-lookup"><span data-stu-id="26561-117">EventPipe Overview</span></span>](../../../core/diagnostics/eventpipe.md)
- [<span data-ttu-id="26561-118">EventProviders conocidos</span><span class="sxs-lookup"><span data-stu-id="26561-118">Well Known EventProviders</span></span>](../../../core/diagnostics/well-known-event-providers.md)
- [<span data-ttu-id="26561-119">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="26561-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="26561-120">Interfaz ICorProfilerInfo12</span><span class="sxs-lookup"><span data-stu-id="26561-120">ICorProfilerInfo12 Interface</span></span>](ICorProfilerInfo12-interface.md)
- [<span data-ttu-id="26561-121">ICorProfilerInfo12. EventPipeStartSession, método</span><span class="sxs-lookup"><span data-stu-id="26561-121">ICorProfilerInfo12.EventPipeStartSession method</span></span>](ICorProfilerInfo12-eventpipestartsession-method.md)
- [<span data-ttu-id="26561-122">ICorProfilerInfo12. EventPipeStopSession, método</span><span class="sxs-lookup"><span data-stu-id="26561-122">ICorProfilerInfo12.EventPipeStopSession method</span></span>](ICorProfilerInfo12-eventpipestopsession-method.md)
