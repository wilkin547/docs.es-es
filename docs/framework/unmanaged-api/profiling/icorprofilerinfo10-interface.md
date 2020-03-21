---
title: Interfaz ICorProfilerInfo10
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 4c5d553744008734037975d6e63e1b07b89cf886
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175075"
---
# <a name="icorprofilerinfo10-interface"></a><span data-ttu-id="62c29-102">Interfaz ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="62c29-102">ICorProfilerInfo10 Interface</span></span>

<span data-ttu-id="62c29-103">Subclase de [ICorProfilerInfo9](icorprofilerinfo9-interface.md) que proporciona métodos para modificar la función IL, consultar información del tiempo de ejecución y suspender y reanudar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="62c29-103">A subclass of [ICorProfilerInfo9](icorprofilerinfo9-interface.md) that provides methods to modify function IL, query information from the runtime, and suspend and resume the runtime.</span></span>

## <a name="methods"></a><span data-ttu-id="62c29-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="62c29-104">Methods</span></span>  

| <span data-ttu-id="62c29-105">Método</span><span class="sxs-lookup"><span data-stu-id="62c29-105">Method</span></span>|<span data-ttu-id="62c29-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="62c29-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="62c29-107">Método EnumerateObjectReferences</span><span class="sxs-lookup"><span data-stu-id="62c29-107">EnumerateObjectReferences Method</span></span>](icorprofilerinfo10-enumerateobjectreferences-method.md)|<span data-ttu-id="62c29-108">Dado un ObjectID, callback y clientData, enumera cada referencia de objeto (si existe).</span><span class="sxs-lookup"><span data-stu-id="62c29-108">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span> |
|[<span data-ttu-id="62c29-109">Método IsFrozenObject</span><span class="sxs-lookup"><span data-stu-id="62c29-109">IsFrozenObject Method</span></span>](icorprofilerinfo10-isfrozenobject-method.md)|<span data-ttu-id="62c29-110">Dado un ObjectID, determina si el objeto está en un segmento de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="62c29-110">Given an ObjectID, determines whether the object is in a read-only segment.</span></span> |
|[<span data-ttu-id="62c29-111">Método GetLOHObjectSizeThreshold</span><span class="sxs-lookup"><span data-stu-id="62c29-111">GetLOHObjectSizeThreshold Method</span></span>](icorprofilerinfo10-getlohobjectsizethreshold-method.md)|<span data-ttu-id="62c29-112">Obtiene el valor del umbral LOH configurado.</span><span class="sxs-lookup"><span data-stu-id="62c29-112">Gets the value of the configured LOH threshold.</span></span> |
|[<span data-ttu-id="62c29-113">Método RequestReJITWithInliners</span><span class="sxs-lookup"><span data-stu-id="62c29-113">RequestReJITWithInliners Method</span></span>](icorprofilerinfo10-requestrejitwithinliners-method.md)| <span data-ttu-id="62c29-114">ReJITs los métodos solicitados, así como cualquier inliners de los métodos solicitados.</span><span class="sxs-lookup"><span data-stu-id="62c29-114">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>  |
|[<span data-ttu-id="62c29-115">Método SuspendRuntime</span><span class="sxs-lookup"><span data-stu-id="62c29-115">SuspendRuntime Method</span></span>](icorprofilerinfo10-suspendruntime-method.md)| <span data-ttu-id="62c29-116">Suspende el tiempo de ejecución sin realizar un GC.</span><span class="sxs-lookup"><span data-stu-id="62c29-116">Suspends the runtime without performing a GC.</span></span> |
|[<span data-ttu-id="62c29-117">Método ResumeRuntime</span><span class="sxs-lookup"><span data-stu-id="62c29-117">ResumeRuntime Method</span></span>](icorprofilerinfo10-resumeruntime-method.md)| <span data-ttu-id="62c29-118">Reanuda el tiempo de ejecución sin realizar un GC.</span><span class="sxs-lookup"><span data-stu-id="62c29-118">Resumes the runtime without performing a GC.</span></span> |

## <a name="requirements"></a><span data-ttu-id="62c29-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="62c29-119">Requirements</span></span>  
<span data-ttu-id="62c29-120">**Plataformas:** Consulte [Sistemas operativos compatibles con .NET Core](../../../core/install/dependencies.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="62c29-120">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>  
<span data-ttu-id="62c29-121">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="62c29-121">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="62c29-122">**Versiones de .NET:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62c29-122">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="62c29-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="62c29-123">See also</span></span>

- [<span data-ttu-id="62c29-124">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="62c29-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
