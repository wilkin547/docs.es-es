---
title: ICorProfilerModuleEnum (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum
api_location:
- mscorwks.cll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum
helpviewer_keywords:
- ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: 24d0fcfa-1601-4fba-868f-da8c97303467
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 99db173aa7c6064d9f635412d539cc2d4509b24a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59124662"
---
# <a name="icorprofilermoduleenum-interface"></a><span data-ttu-id="d7830-102">ICorProfilerModuleEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d7830-102">ICorProfilerModuleEnum Interface</span></span>
<span data-ttu-id="d7830-103">Proporciona métodos para iterar secuencialmente por una colección de módulos cargados por la aplicación o por el generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="d7830-103">Provides methods to sequentially iterate through a collection of modules loaded by the application or the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d7830-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="d7830-104">Methods</span></span>  
  
|<span data-ttu-id="d7830-105">Método</span><span class="sxs-lookup"><span data-stu-id="d7830-105">Method</span></span>|<span data-ttu-id="d7830-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="d7830-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d7830-107">Método Clone</span><span class="sxs-lookup"><span data-stu-id="d7830-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-clone-method.md)|<span data-ttu-id="d7830-108">Obtiene un puntero de interfaz a una copia de esta interfaz `ICorProfilerModuleEnum`.</span><span class="sxs-lookup"><span data-stu-id="d7830-108">Gets an interface pointer to a copy of this `ICorProfilerModuleEnum` interface.</span></span>|  
|[<span data-ttu-id="d7830-109">Método GetCount</span><span class="sxs-lookup"><span data-stu-id="d7830-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-getcount-method.md)|<span data-ttu-id="d7830-110">Obtiene el número de módulos administrados que se cargaron en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d7830-110">Gets the number of managed modules that were loaded into the application.</span></span>|  
|[<span data-ttu-id="d7830-111">Método Next</span><span class="sxs-lookup"><span data-stu-id="d7830-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-next-method.md)|<span data-ttu-id="d7830-112">Obtiene el número especificado de módulos contiguos de una colección secuencial de módulos, comenzando en la posición actual del enumerador en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="d7830-112">Gets the specified number of contiguous modules from a sequential collection of objects, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="d7830-113">Método Reset</span><span class="sxs-lookup"><span data-stu-id="d7830-113">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-reset-method.md)|<span data-ttu-id="d7830-114">Mueve el cursor del enumerador a la posición inicial de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="d7830-114">Moves the enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="d7830-115">Método Skip</span><span class="sxs-lookup"><span data-stu-id="d7830-115">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-skip-method.md)|<span data-ttu-id="d7830-116">Desplaza la posición del cursor del enumerador de manera que se omite el número especificado de elementos.</span><span class="sxs-lookup"><span data-stu-id="d7830-116">Advances the position of the enumerator's cursor so that the specified number of elements are skipped.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7830-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d7830-117">Remarks</span></span>  
 <span data-ttu-id="d7830-118">La interfaz `ICorProfilerModuleEnum` es un enumerador.</span><span class="sxs-lookup"><span data-stu-id="d7830-118">The `ICorProfilerModuleEnum` interface is an enumerator.</span></span> <span data-ttu-id="d7830-119">Permite al receptor de una matriz incorporar los cambios de los elementos del remitente a una velocidad que sea adecuada para el receptor.</span><span class="sxs-lookup"><span data-stu-id="d7830-119">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="d7830-120">En otras palabras, el receptor es capaz de controlar explícitamente el flujo de elementos de matriz, lo que evita los problemas asociados con pasar matrices de gran tamaño como parámetros de método.</span><span class="sxs-lookup"><span data-stu-id="d7830-120">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems associated with passing large arrays as method parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7830-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d7830-121">Requirements</span></span>  
 <span data-ttu-id="d7830-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7830-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7830-123">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d7830-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d7830-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7830-124">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d7830-125">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d7830-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d7830-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7830-126">See also</span></span>

- [<span data-ttu-id="d7830-127">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d7830-127">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="d7830-128">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="d7830-128">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="d7830-129">Método EnumModules</span><span class="sxs-lookup"><span data-stu-id="d7830-129">EnumModules Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md)
