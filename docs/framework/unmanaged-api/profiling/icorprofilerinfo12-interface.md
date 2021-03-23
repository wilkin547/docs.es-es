---
description: 'Más información acerca de: interfaz ICorProfilerInfo12'
title: Interfaz ICorProfilerInfo12
ms.date: 03/19/2021
api_name:
- ICorProfilerInfo12
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: a8b91eba686478c3e825ae15d6ae95bd0ffad944
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805732"
---
# <a name="icorprofilerinfo12-interface"></a><span data-ttu-id="11e3e-103">Interfaz ICorProfilerInfo12</span><span class="sxs-lookup"><span data-stu-id="11e3e-103">ICorProfilerInfo12 Interface</span></span>

 <span data-ttu-id="11e3e-104">Una subclase de [ICorProfilerInfo11](icorprofilerinfo11-interface.md) que proporciona métodos para crear sesiones, eventos y proveedores de EventPipe.</span><span class="sxs-lookup"><span data-stu-id="11e3e-104">A subclass of [ICorProfilerInfo11](icorprofilerinfo11-interface.md) that provides methods to create EventPipe sessions, events, and providers.</span></span>
  
## <a name="methods"></a><span data-ttu-id="11e3e-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="11e3e-105">Methods</span></span>  
  
|<span data-ttu-id="11e3e-106">Método</span><span class="sxs-lookup"><span data-stu-id="11e3e-106">Method</span></span>|<span data-ttu-id="11e3e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="11e3e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="11e3e-108">Método EventPipeStartSession</span><span class="sxs-lookup"><span data-stu-id="11e3e-108">EventPipeStartSession Method</span></span>](icorprofilerinfo12-eventpipestartsession-method.md)|<span data-ttu-id="11e3e-109">Inicia una sesión de EventPipe del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="11e3e-109">Starts a profiler EventPipe session.</span></span>|
|[<span data-ttu-id="11e3e-110">Método EventPipeAddProviderToSession</span><span class="sxs-lookup"><span data-stu-id="11e3e-110">EventPipeAddProviderToSession Method</span></span>](icorprofilerinfo12-eventpipeaddprovidertosession-method.md)|<span data-ttu-id="11e3e-111">Agrega un proveedor a una sesión de EventPipe existente.</span><span class="sxs-lookup"><span data-stu-id="11e3e-111">Adds a provider to an existing EventPipe session.</span></span>|
|[<span data-ttu-id="11e3e-112">Método EventPipeStopSession</span><span class="sxs-lookup"><span data-stu-id="11e3e-112">EventPipeStopSession Method</span></span>](icorprofilerinfo12-eventpipestopsession-method.md)|<span data-ttu-id="11e3e-113">Detiene una sesión de EventPipe.</span><span class="sxs-lookup"><span data-stu-id="11e3e-113">Stops an EventPipe session.</span></span>|
|[<span data-ttu-id="11e3e-114">Método EventPipeCreateProvider</span><span class="sxs-lookup"><span data-stu-id="11e3e-114">EventPipeCreateProvider Method</span></span>](icorprofilerinfo12-eventpipecreateprovider-method.md)|<span data-ttu-id="11e3e-115">Crea un proveedor de EventPipe.</span><span class="sxs-lookup"><span data-stu-id="11e3e-115">Creates an EventPipe provider.</span></span>|  
|[<span data-ttu-id="11e3e-116">Método EventPipeGetProviderInfo</span><span class="sxs-lookup"><span data-stu-id="11e3e-116">EventPipeGetProviderInfo Method</span></span>](icorprofilerinfo12-eventpipegetproviderinfo-method.md)|<span data-ttu-id="11e3e-117">Obtiene el nombre de un proveedor EventPipe de su identificador.</span><span class="sxs-lookup"><span data-stu-id="11e3e-117">Gets the name of an EventPipe provider from its ID.</span></span>|
|[<span data-ttu-id="11e3e-118">Método EventPipeDefineEvent</span><span class="sxs-lookup"><span data-stu-id="11e3e-118">EventPipeDefineEvent Method</span></span>](icorprofilerinfo12-eventpipedefineevent-method.md)|<span data-ttu-id="11e3e-119">Define un evento en un proveedor de EventPipe existente.</span><span class="sxs-lookup"><span data-stu-id="11e3e-119">Defines an event on an existing EventPipe provider.</span></span>|  
|[<span data-ttu-id="11e3e-120">Método EventPipeWriteEvent</span><span class="sxs-lookup"><span data-stu-id="11e3e-120">EventPipeWriteEvent Method</span></span>](icorprofilerinfo12-eventpipewriteevent-method.md)|<span data-ttu-id="11e3e-121">Escribe un evento EventPipe.</span><span class="sxs-lookup"><span data-stu-id="11e3e-121">Writes an EventPipe event.</span></span>|
  
## <a name="requirements"></a><span data-ttu-id="11e3e-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="11e3e-122">Requirements</span></span>  

<span data-ttu-id="11e3e-123">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="11e3e-123">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>  
<span data-ttu-id="11e3e-124">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="11e3e-124">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="11e3e-125">**Versiones de .net:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11e3e-125">**.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="11e3e-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="11e3e-126">See also</span></span>

- [<span data-ttu-id="11e3e-127">Información general sobre EventPipe</span><span class="sxs-lookup"><span data-stu-id="11e3e-127">EventPipe Overview</span></span>](../../../core/diagnostics/eventpipe.md)
- [<span data-ttu-id="11e3e-128">EventProviders conocidos</span><span class="sxs-lookup"><span data-stu-id="11e3e-128">Well Known EventProviders</span></span>](../../../core/diagnostics/well-known-event-providers.md)
- [<span data-ttu-id="11e3e-129">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="11e3e-129">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="11e3e-130">Interfaz ICorProfilerCallback10</span><span class="sxs-lookup"><span data-stu-id="11e3e-130">ICorProfilerCallback10 Interface</span></span>](icorprofilercallback10-interface.md)
