---
title: Interfaz ICorProfilerInfo10
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 30179c7c198a343baa3fa01ae64f6d580a3f9e7e
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452206"
---
# <a name="icorprofilerinfo10-interface"></a><span data-ttu-id="69d0e-102">Interfaz ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="69d0e-102">ICorProfilerInfo10 Interface</span></span>

<span data-ttu-id="69d0e-103">Una subclase de [ICorProfilerInfo9](icorprofilerinfo9-interface.md) que proporciona métodos para modificar el Il de la función, consultar información del tiempo de ejecución y suspender y reanudar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="69d0e-103">A subclass of [ICorProfilerInfo9](icorprofilerinfo9-interface.md) that provides methods to modify function IL, query information from the runtime, and suspend and resume the runtime.</span></span>

## <a name="methods"></a><span data-ttu-id="69d0e-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="69d0e-104">Methods</span></span>  

| <span data-ttu-id="69d0e-105">Método</span><span class="sxs-lookup"><span data-stu-id="69d0e-105">Method</span></span>|<span data-ttu-id="69d0e-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="69d0e-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="69d0e-107">Método EnumerateObjectReferences</span><span class="sxs-lookup"><span data-stu-id="69d0e-107">EnumerateObjectReferences Method</span></span>](icorprofilerinfo10-enumerateobjectreferences-method.md)|<span data-ttu-id="69d0e-108">Dado un ObjectID, callback y clientData, enumera cada referencia de objeto (si existe).</span><span class="sxs-lookup"><span data-stu-id="69d0e-108">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span> |
|[<span data-ttu-id="69d0e-109">Método IsFrozenObject</span><span class="sxs-lookup"><span data-stu-id="69d0e-109">IsFrozenObject Method</span></span>](icorprofilerinfo10-isfrozenobject-method.md)|<span data-ttu-id="69d0e-110">Dado un ObjectID, determina si el objeto está en un segmento de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="69d0e-110">Given an ObjectID, determines whether the object is in a read-only segment.</span></span> |
|[<span data-ttu-id="69d0e-111">Método GetLOHObjectSizeThreshold</span><span class="sxs-lookup"><span data-stu-id="69d0e-111">GetLOHObjectSizeThreshold Method</span></span>](icorprofilerinfo10-getlohobjectsizethreshold-method.md)|<span data-ttu-id="69d0e-112">Obtiene el valor del umbral de montón configurado.</span><span class="sxs-lookup"><span data-stu-id="69d0e-112">Gets the value of the configured LOH threshold.</span></span> |
|[<span data-ttu-id="69d0e-113">Método RequestReJITWithInliners</span><span class="sxs-lookup"><span data-stu-id="69d0e-113">RequestReJITWithInliners Method</span></span>](icorprofilerinfo10-requestrejitwithinliners-method.md)| <span data-ttu-id="69d0e-114">ReJITs los métodos solicitados, así como los inlineers de los métodos solicitados.</span><span class="sxs-lookup"><span data-stu-id="69d0e-114">ReJITs the methods requested, as well as any inliners of the methods requested.</span></span>  |
|[<span data-ttu-id="69d0e-115">Método SuspendRuntime</span><span class="sxs-lookup"><span data-stu-id="69d0e-115">SuspendRuntime Method</span></span>](icorprofilerinfo10-suspendruntime-method.md)| <span data-ttu-id="69d0e-116">Suspende el tiempo de ejecución sin realizar un GC.</span><span class="sxs-lookup"><span data-stu-id="69d0e-116">Suspends the runtime without performing a GC.</span></span> |
|[<span data-ttu-id="69d0e-117">Método ResumeRuntime</span><span class="sxs-lookup"><span data-stu-id="69d0e-117">ResumeRuntime Method</span></span>](icorprofilerinfo10-resumeruntime-method.md)| <span data-ttu-id="69d0e-118">Reanuda el tiempo de ejecución sin realizar un GC.</span><span class="sxs-lookup"><span data-stu-id="69d0e-118">Resumes the runtime without performing a GC.</span></span> |

## <a name="requirements"></a><span data-ttu-id="69d0e-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="69d0e-119">Requirements</span></span>  
<span data-ttu-id="69d0e-120">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/dependencies.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="69d0e-120">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>  
<span data-ttu-id="69d0e-121">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="69d0e-121">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="69d0e-122">**Versiones de .net:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69d0e-122">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span> 

## <a name="see-also"></a><span data-ttu-id="69d0e-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="69d0e-123">See also</span></span>

- [<span data-ttu-id="69d0e-124">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="69d0e-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
