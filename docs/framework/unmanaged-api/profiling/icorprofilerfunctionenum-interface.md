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
ms.openlocfilehash: b69afa7676ad174725f13c1113ff3bd9972995f8
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503086"
---
# <a name="icorprofilerfunctionenum-interface"></a><span data-ttu-id="6ebfe-102">ICorProfilerFunctionEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6ebfe-102">ICorProfilerFunctionEnum Interface</span></span>
<span data-ttu-id="6ebfe-103">Proporciona métodos para iterar secuencialmente por una colección de funciones en Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="6ebfe-103">Provides methods to sequentially iterate through a collection of functions in the common language runtime.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6ebfe-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="6ebfe-104">Methods</span></span>  
  
|<span data-ttu-id="6ebfe-105">Método</span><span class="sxs-lookup"><span data-stu-id="6ebfe-105">Method</span></span>|<span data-ttu-id="6ebfe-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="6ebfe-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6ebfe-107">Método Clone</span><span class="sxs-lookup"><span data-stu-id="6ebfe-107">Clone Method</span></span>](icorprofilerfunctionenum-clone-method.md)|<span data-ttu-id="6ebfe-108">Obtiene un puntero de interfaz a una copia de esta interfaz `ICorProfilerFunctionEnum`.</span><span class="sxs-lookup"><span data-stu-id="6ebfe-108">Gets an interface pointer to a copy of this `ICorProfilerFunctionEnum` interface.</span></span>|  
|[<span data-ttu-id="6ebfe-109">Método GetCount</span><span class="sxs-lookup"><span data-stu-id="6ebfe-109">GetCount Method</span></span>](icorprofilerfunctionenum-getcount-method.md)|<span data-ttu-id="6ebfe-110">Obtiene el número de funciones que la aplicación cargó o que el generador de perfiles cargó forzosamente.</span><span class="sxs-lookup"><span data-stu-id="6ebfe-110">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>|  
|[<span data-ttu-id="6ebfe-111">Next (Método)</span><span class="sxs-lookup"><span data-stu-id="6ebfe-111">Next Method</span></span>](icorprofilerfunctionenum-next-method.md)|<span data-ttu-id="6ebfe-112">Obtiene el número especificado de funciones contiguas de una colección secuencial de funciones, comenzando en la posición actual del enumerador en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="6ebfe-112">Gets the specified number of contiguous functions from a sequential collection of functions, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="6ebfe-113">Reset (Método)</span><span class="sxs-lookup"><span data-stu-id="6ebfe-113">Reset Method</span></span>](icorprofilerfunctionenum-reset-method.md)|<span data-ttu-id="6ebfe-114">Mueve el cursor del enumerador a la posición inicial de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="6ebfe-114">Moves the enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="6ebfe-115">Método Skip</span><span class="sxs-lookup"><span data-stu-id="6ebfe-115">Skip Method</span></span>](icorprofilerfunctionenum-skip-method.md)|<span data-ttu-id="6ebfe-116">Desplaza el cursor del enumerador desde su posición actual de manera que se omita el número especificado de elementos.</span><span class="sxs-lookup"><span data-stu-id="6ebfe-116">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ebfe-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6ebfe-117">Remarks</span></span>  
 <span data-ttu-id="6ebfe-118">La interfaz `ICorProfilerFunctionEnum` es un enumerador.</span><span class="sxs-lookup"><span data-stu-id="6ebfe-118">The `ICorProfilerFunctionEnum` interface is an enumerator.</span></span> <span data-ttu-id="6ebfe-119">Permite al receptor de una matriz incorporar los cambios de los elementos del remitente a una velocidad que sea adecuada para el receptor.</span><span class="sxs-lookup"><span data-stu-id="6ebfe-119">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="6ebfe-120">En otras palabras, el receptor es capaz de controlar explícitamente el flujo de elementos de matriz, lo que evita los problemas asociados con pasar matrices de gran tamaño como parámetros de método.</span><span class="sxs-lookup"><span data-stu-id="6ebfe-120">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems associated with passing large arrays as method parameters.</span></span>  
  
 <span data-ttu-id="6ebfe-121">`ICorProfilerFunctionEnum` enumera las funciones que ya se han compilado con JIT, pero no incluye las funciones que se cargan desde imágenes nativas generadas con Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="6ebfe-121">`ICorProfilerFunctionEnum` enumerates over functions that have already been JIT-compiled, but does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ebfe-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6ebfe-122">Requirements</span></span>  
 <span data-ttu-id="6ebfe-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ebfe-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ebfe-124">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6ebfe-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6ebfe-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ebfe-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ebfe-126">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ebfe-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ebfe-127">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="6ebfe-127">See also</span></span>

- [<span data-ttu-id="6ebfe-128">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6ebfe-128">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="6ebfe-129">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="6ebfe-129">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="6ebfe-130">Método EnumJITedFunctions</span><span class="sxs-lookup"><span data-stu-id="6ebfe-130">EnumJITedFunctions Method</span></span>](icorprofilerinfo3-enumjitedfunctions-method.md)
