---
title: ICorProfilerFunctionEnum (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum
helpviewer_keywords:
- ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0a1d4a38-cd0b-4231-91df-13646218ae72
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0e77ec9de198b673bb3b5fc4dad3cd1b0316f07c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092076"
---
# <a name="icorprofilerfunctionenum-interface"></a><span data-ttu-id="e18be-102">ICorProfilerFunctionEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e18be-102">ICorProfilerFunctionEnum Interface</span></span>
<span data-ttu-id="e18be-103">Proporciona métodos para iterar secuencialmente por una colección de funciones en Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="e18be-103">Provides methods to sequentially iterate through a collection of functions in the common language runtime.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e18be-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="e18be-104">Methods</span></span>  
  
|<span data-ttu-id="e18be-105">Método</span><span class="sxs-lookup"><span data-stu-id="e18be-105">Method</span></span>|<span data-ttu-id="e18be-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e18be-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e18be-107">Método Clone</span><span class="sxs-lookup"><span data-stu-id="e18be-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-clone-method.md)|<span data-ttu-id="e18be-108">Obtiene un puntero de interfaz a una copia de esta interfaz `ICorProfilerFunctionEnum`.</span><span class="sxs-lookup"><span data-stu-id="e18be-108">Gets an interface pointer to a copy of this `ICorProfilerFunctionEnum` interface.</span></span>|  
|[<span data-ttu-id="e18be-109">Método GetCount</span><span class="sxs-lookup"><span data-stu-id="e18be-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-getcount-method.md)|<span data-ttu-id="e18be-110">Obtiene el número de funciones que la aplicación cargó o que el generador de perfiles cargó forzosamente.</span><span class="sxs-lookup"><span data-stu-id="e18be-110">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>|  
|[<span data-ttu-id="e18be-111">Método Next</span><span class="sxs-lookup"><span data-stu-id="e18be-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-next-method.md)|<span data-ttu-id="e18be-112">Obtiene el número especificado de funciones contiguas de una colección secuencial de funciones, comenzando en la posición actual del enumerador en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="e18be-112">Gets the specified number of contiguous functions from a sequential collection of functions, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="e18be-113">Método Reset</span><span class="sxs-lookup"><span data-stu-id="e18be-113">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-reset-method.md)|<span data-ttu-id="e18be-114">Mueve el cursor del enumerador a la posición inicial de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="e18be-114">Moves the enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="e18be-115">Método Skip</span><span class="sxs-lookup"><span data-stu-id="e18be-115">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-skip-method.md)|<span data-ttu-id="e18be-116">Desplaza el cursor del enumerador desde su posición actual de manera que se omita el número especificado de elementos.</span><span class="sxs-lookup"><span data-stu-id="e18be-116">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e18be-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e18be-117">Remarks</span></span>  
 <span data-ttu-id="e18be-118">La interfaz `ICorProfilerFunctionEnum` es un enumerador.</span><span class="sxs-lookup"><span data-stu-id="e18be-118">The `ICorProfilerFunctionEnum` interface is an enumerator.</span></span> <span data-ttu-id="e18be-119">Permite al receptor de una matriz incorporar los cambios de los elementos del remitente a una velocidad que sea adecuada para el receptor.</span><span class="sxs-lookup"><span data-stu-id="e18be-119">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="e18be-120">En otras palabras, el receptor es capaz de controlar explícitamente el flujo de elementos de matriz, lo que evita los problemas asociados con pasar matrices de gran tamaño como parámetros de método.</span><span class="sxs-lookup"><span data-stu-id="e18be-120">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems associated with passing large arrays as method parameters.</span></span>  
  
 `ICorProfilerFunctionEnum` <span data-ttu-id="e18be-121">Enumera las funciones que ya se han compilado JIT, pero no incluyen funciones que se cargan desde imágenes nativas generadas con Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="e18be-121">enumerates over functions that have already been JIT-compiled, but does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e18be-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e18be-122">Requirements</span></span>  
 <span data-ttu-id="e18be-123">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e18be-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e18be-124">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e18be-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e18be-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e18be-125">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e18be-126">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e18be-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e18be-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="e18be-127">See also</span></span>

- [<span data-ttu-id="e18be-128">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e18be-128">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="e18be-129">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="e18be-129">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="e18be-130">Método EnumJITedFunctions</span><span class="sxs-lookup"><span data-stu-id="e18be-130">EnumJITedFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)
