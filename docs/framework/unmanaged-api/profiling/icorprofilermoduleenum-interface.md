---
title: ICorProfilerModuleEnum (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerModuleEnum
api_location: mscorwks.cll
api_type: COM
f1_keywords: ICorProfilerModuleEnum
helpviewer_keywords: ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: 24d0fcfa-1601-4fba-868f-da8c97303467
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b337bc99f89b04145afb3994da840cff7e2c5c80
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilermoduleenum-interface"></a><span data-ttu-id="c4fae-102">ICorProfilerModuleEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c4fae-102">ICorProfilerModuleEnum Interface</span></span>
<span data-ttu-id="c4fae-103">Proporciona métodos para iterar secuencialmente por una colección de módulos cargados por la aplicación o por el generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="c4fae-103">Provides methods to sequentially iterate through a collection of modules loaded by the application or the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c4fae-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c4fae-104">Methods</span></span>  
  
|<span data-ttu-id="c4fae-105">Método</span><span class="sxs-lookup"><span data-stu-id="c4fae-105">Method</span></span>|<span data-ttu-id="c4fae-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c4fae-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c4fae-107">Clone (método)</span><span class="sxs-lookup"><span data-stu-id="c4fae-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-clone-method.md)|<span data-ttu-id="c4fae-108">Obtiene un puntero de interfaz a una copia de esta interfaz `ICorProfilerModuleEnum`.</span><span class="sxs-lookup"><span data-stu-id="c4fae-108">Gets an interface pointer to a copy of this `ICorProfilerModuleEnum` interface.</span></span>|  
|[<span data-ttu-id="c4fae-109">GetCount (método)</span><span class="sxs-lookup"><span data-stu-id="c4fae-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-getcount-method.md)|<span data-ttu-id="c4fae-110">Obtiene el número de módulos administrados que se cargaron en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c4fae-110">Gets the number of managed modules that were loaded into the application.</span></span>|  
|[<span data-ttu-id="c4fae-111">Next (método)</span><span class="sxs-lookup"><span data-stu-id="c4fae-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-next-method.md)|<span data-ttu-id="c4fae-112">Obtiene el número especificado de módulos contiguos de una colección secuencial de módulos, comenzando en la posición actual del enumerador en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="c4fae-112">Gets the specified number of contiguous modules from a sequential collection of objects, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="c4fae-113">Reset (método)</span><span class="sxs-lookup"><span data-stu-id="c4fae-113">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-reset-method.md)|<span data-ttu-id="c4fae-114">Mueve el cursor del enumerador a la posición inicial de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="c4fae-114">Moves the enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="c4fae-115">Skip (método)</span><span class="sxs-lookup"><span data-stu-id="c4fae-115">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-skip-method.md)|<span data-ttu-id="c4fae-116">Desplaza la posición del cursor del enumerador de manera que se omite el número especificado de elementos.</span><span class="sxs-lookup"><span data-stu-id="c4fae-116">Advances the position of the enumerator's cursor so that the specified number of elements are skipped.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4fae-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c4fae-117">Remarks</span></span>  
 <span data-ttu-id="c4fae-118">La interfaz `ICorProfilerModuleEnum` es un enumerador.</span><span class="sxs-lookup"><span data-stu-id="c4fae-118">The `ICorProfilerModuleEnum` interface is an enumerator.</span></span> <span data-ttu-id="c4fae-119">Permite al receptor de una matriz extraer los elementos del remitente a una velocidad que sea adecuada para el receptor.</span><span class="sxs-lookup"><span data-stu-id="c4fae-119">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="c4fae-120">En otras palabras, el receptor es capaz de controlar explícitamente el flujo de elementos de matriz, lo que evita los problemas asociados con pasar matrices de gran tamaño como parámetros de método.</span><span class="sxs-lookup"><span data-stu-id="c4fae-120">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems associated with passing large arrays as method parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4fae-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c4fae-121">Requirements</span></span>  
 <span data-ttu-id="c4fae-122">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4fae-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4fae-123">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c4fae-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c4fae-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4fae-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4fae-125">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4fae-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4fae-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4fae-126">See Also</span></span>  
 [<span data-ttu-id="c4fae-127">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c4fae-127">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="c4fae-128">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="c4fae-128">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="c4fae-129">EnumModules (método)</span><span class="sxs-lookup"><span data-stu-id="c4fae-129">EnumModules Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md)
