---
title: Interfaz ICorProfilerInfo10
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 7e483bae9b7898e25c376fa92d0449fc49c6f9ee
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548691"
---
# <a name="icorprofilerinfo10-interface"></a><span data-ttu-id="5cf01-102">Interfaz ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="5cf01-102">ICorProfilerInfo10 Interface</span></span>

<span data-ttu-id="5cf01-103">Una subclase de [ICorProfilerInfo9](icorprofilerinfo9-interface.md) que proporciona métodos para modificar el Il de la función, consultar información del tiempo de ejecución y suspender y reanudar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5cf01-103">A subclass of [ICorProfilerInfo9](icorprofilerinfo9-interface.md) that provides methods to modify function IL, query information from the runtime, and suspend and resume the runtime.</span></span>

## <a name="methods"></a><span data-ttu-id="5cf01-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="5cf01-104">Methods</span></span>  

| <span data-ttu-id="5cf01-105">Método</span><span class="sxs-lookup"><span data-stu-id="5cf01-105">Method</span></span>|<span data-ttu-id="5cf01-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="5cf01-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="5cf01-107">Método EnumerateObjectReferences</span><span class="sxs-lookup"><span data-stu-id="5cf01-107">EnumerateObjectReferences Method</span></span>](icorprofilerinfo10-enumerateobjectreferences-method.md)|<span data-ttu-id="5cf01-108">Dado un ObjectID, callback y clientData, enumera cada referencia de objeto (si existe).</span><span class="sxs-lookup"><span data-stu-id="5cf01-108">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span> |
|[<span data-ttu-id="5cf01-109">Método IsFrozenObject</span><span class="sxs-lookup"><span data-stu-id="5cf01-109">IsFrozenObject Method</span></span>](icorprofilerinfo10-isfrozenobject-method.md)|<span data-ttu-id="5cf01-110">Dado un ObjectID, determina si el objeto está en un segmento de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="5cf01-110">Given an ObjectID, determines whether the object is in a read-only segment.</span></span> |
|[<span data-ttu-id="5cf01-111">Método GetLOHObjectSizeThreshold</span><span class="sxs-lookup"><span data-stu-id="5cf01-111">GetLOHObjectSizeThreshold Method</span></span>](icorprofilerinfo10-getlohobjectsizethreshold-method.md)|<span data-ttu-id="5cf01-112">Obtiene el valor del umbral de montón configurado.</span><span class="sxs-lookup"><span data-stu-id="5cf01-112">Gets the value of the configured LOH threshold.</span></span> |
|[<span data-ttu-id="5cf01-113">Método RequestReJITWithInliners</span><span class="sxs-lookup"><span data-stu-id="5cf01-113">RequestReJITWithInliners Method</span></span>](icorprofilerinfo10-requestrejitwithinliners-method.md)| <span data-ttu-id="5cf01-114">ReJITs los métodos solicitados, así como los inlineers de los métodos solicitados.</span><span class="sxs-lookup"><span data-stu-id="5cf01-114">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>  |
|[<span data-ttu-id="5cf01-115">Método SuspendRuntime</span><span class="sxs-lookup"><span data-stu-id="5cf01-115">SuspendRuntime Method</span></span>](icorprofilerinfo10-suspendruntime-method.md)| <span data-ttu-id="5cf01-116">Suspende el tiempo de ejecución sin realizar un GC.</span><span class="sxs-lookup"><span data-stu-id="5cf01-116">Suspends the runtime without performing a GC.</span></span> |
|[<span data-ttu-id="5cf01-117">Método ResumeRuntime</span><span class="sxs-lookup"><span data-stu-id="5cf01-117">ResumeRuntime Method</span></span>](icorprofilerinfo10-resumeruntime-method.md)| <span data-ttu-id="5cf01-118">Reanuda el tiempo de ejecución sin realizar un GC.</span><span class="sxs-lookup"><span data-stu-id="5cf01-118">Resumes the runtime without performing a GC.</span></span> |

## <a name="requirements"></a><span data-ttu-id="5cf01-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5cf01-119">Requirements</span></span>  
<span data-ttu-id="5cf01-120">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="5cf01-120">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>  
<span data-ttu-id="5cf01-121">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5cf01-121">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="5cf01-122">**Versiones de .net:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cf01-122">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5cf01-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="5cf01-123">See also</span></span>

- [<span data-ttu-id="5cf01-124">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="5cf01-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
