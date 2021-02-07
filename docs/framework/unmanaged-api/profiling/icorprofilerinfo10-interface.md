---
description: 'Más información acerca de: interfaz ICorProfilerInfo10'
title: Interfaz ICorProfilerInfo10
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: fd24491cb1ca55ad48137522c63e78e6387d33e6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753294"
---
# <a name="icorprofilerinfo10-interface"></a><span data-ttu-id="1fe10-103">Interfaz ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="1fe10-103">ICorProfilerInfo10 Interface</span></span>

<span data-ttu-id="1fe10-104">Una subclase de [ICorProfilerInfo9](icorprofilerinfo9-interface.md) que proporciona métodos para modificar el Il de la función, consultar información del tiempo de ejecución y suspender y reanudar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1fe10-104">A subclass of [ICorProfilerInfo9](icorprofilerinfo9-interface.md) that provides methods to modify function IL, query information from the runtime, and suspend and resume the runtime.</span></span>

## <a name="methods"></a><span data-ttu-id="1fe10-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="1fe10-105">Methods</span></span>  

| <span data-ttu-id="1fe10-106">Método</span><span class="sxs-lookup"><span data-stu-id="1fe10-106">Method</span></span>|<span data-ttu-id="1fe10-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="1fe10-107">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="1fe10-108">Método EnumerateObjectReferences</span><span class="sxs-lookup"><span data-stu-id="1fe10-108">EnumerateObjectReferences Method</span></span>](icorprofilerinfo10-enumerateobjectreferences-method.md)|<span data-ttu-id="1fe10-109">Dado un ObjectID, callback y clientData, enumera cada referencia de objeto (si existe).</span><span class="sxs-lookup"><span data-stu-id="1fe10-109">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span> |
|[<span data-ttu-id="1fe10-110">Método IsFrozenObject</span><span class="sxs-lookup"><span data-stu-id="1fe10-110">IsFrozenObject Method</span></span>](icorprofilerinfo10-isfrozenobject-method.md)|<span data-ttu-id="1fe10-111">Dado un ObjectID, determina si el objeto está en un segmento de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="1fe10-111">Given an ObjectID, determines whether the object is in a read-only segment.</span></span> |
|[<span data-ttu-id="1fe10-112">Método GetLOHObjectSizeThreshold</span><span class="sxs-lookup"><span data-stu-id="1fe10-112">GetLOHObjectSizeThreshold Method</span></span>](icorprofilerinfo10-getlohobjectsizethreshold-method.md)|<span data-ttu-id="1fe10-113">Obtiene el valor del umbral de montón configurado.</span><span class="sxs-lookup"><span data-stu-id="1fe10-113">Gets the value of the configured LOH threshold.</span></span> |
|[<span data-ttu-id="1fe10-114">Método RequestReJITWithInliners</span><span class="sxs-lookup"><span data-stu-id="1fe10-114">RequestReJITWithInliners Method</span></span>](icorprofilerinfo10-requestrejitwithinliners-method.md)| <span data-ttu-id="1fe10-115">ReJITs los métodos solicitados, así como los inlineers de los métodos solicitados.</span><span class="sxs-lookup"><span data-stu-id="1fe10-115">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>  |
|[<span data-ttu-id="1fe10-116">Método SuspendRuntime</span><span class="sxs-lookup"><span data-stu-id="1fe10-116">SuspendRuntime Method</span></span>](icorprofilerinfo10-suspendruntime-method.md)| <span data-ttu-id="1fe10-117">Suspende el tiempo de ejecución sin realizar un GC.</span><span class="sxs-lookup"><span data-stu-id="1fe10-117">Suspends the runtime without performing a GC.</span></span> |
|[<span data-ttu-id="1fe10-118">Método ResumeRuntime</span><span class="sxs-lookup"><span data-stu-id="1fe10-118">ResumeRuntime Method</span></span>](icorprofilerinfo10-resumeruntime-method.md)| <span data-ttu-id="1fe10-119">Reanuda el tiempo de ejecución sin realizar un GC.</span><span class="sxs-lookup"><span data-stu-id="1fe10-119">Resumes the runtime without performing a GC.</span></span> |

## <a name="requirements"></a><span data-ttu-id="1fe10-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1fe10-120">Requirements</span></span>  

<span data-ttu-id="1fe10-121">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="1fe10-121">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>  
<span data-ttu-id="1fe10-122">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1fe10-122">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="1fe10-123">**Versiones de .net:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fe10-123">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="1fe10-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="1fe10-124">See also</span></span>

- [<span data-ttu-id="1fe10-125">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="1fe10-125">Profiling Interfaces</span></span>](profiling-interfaces.md)
