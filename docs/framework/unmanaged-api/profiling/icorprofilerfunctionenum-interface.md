---
description: 'Más información acerca de: ICorProfilerFunctionEnum (interfaz)'
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
ms.openlocfilehash: 0a9437ee1f5c481c2c2d1fd46361da6e938dd179
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737602"
---
# <a name="icorprofilerfunctionenum-interface"></a><span data-ttu-id="1ee04-103">ICorProfilerFunctionEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1ee04-103">ICorProfilerFunctionEnum Interface</span></span>

<span data-ttu-id="1ee04-104">Proporciona métodos para iterar secuencialmente por una colección de funciones en Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="1ee04-104">Provides methods to sequentially iterate through a collection of functions in the common language runtime.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1ee04-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="1ee04-105">Methods</span></span>  
  
|<span data-ttu-id="1ee04-106">Método</span><span class="sxs-lookup"><span data-stu-id="1ee04-106">Method</span></span>|<span data-ttu-id="1ee04-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="1ee04-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1ee04-108">Método Clone</span><span class="sxs-lookup"><span data-stu-id="1ee04-108">Clone Method</span></span>](icorprofilerfunctionenum-clone-method.md)|<span data-ttu-id="1ee04-109">Obtiene un puntero de interfaz a una copia de esta interfaz `ICorProfilerFunctionEnum`.</span><span class="sxs-lookup"><span data-stu-id="1ee04-109">Gets an interface pointer to a copy of this `ICorProfilerFunctionEnum` interface.</span></span>|  
|[<span data-ttu-id="1ee04-110">Método GetCount</span><span class="sxs-lookup"><span data-stu-id="1ee04-110">GetCount Method</span></span>](icorprofilerfunctionenum-getcount-method.md)|<span data-ttu-id="1ee04-111">Obtiene el número de funciones que la aplicación cargó o que el generador de perfiles cargó forzosamente.</span><span class="sxs-lookup"><span data-stu-id="1ee04-111">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>|  
|[<span data-ttu-id="1ee04-112">Next (método)</span><span class="sxs-lookup"><span data-stu-id="1ee04-112">Next Method</span></span>](icorprofilerfunctionenum-next-method.md)|<span data-ttu-id="1ee04-113">Obtiene el número especificado de funciones contiguas de una colección secuencial de funciones, comenzando en la posición actual del enumerador en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="1ee04-113">Gets the specified number of contiguous functions from a sequential collection of functions, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="1ee04-114">Reset (Método)</span><span class="sxs-lookup"><span data-stu-id="1ee04-114">Reset Method</span></span>](icorprofilerfunctionenum-reset-method.md)|<span data-ttu-id="1ee04-115">Mueve el cursor del enumerador a la posición inicial de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="1ee04-115">Moves the enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="1ee04-116">Método Skip</span><span class="sxs-lookup"><span data-stu-id="1ee04-116">Skip Method</span></span>](icorprofilerfunctionenum-skip-method.md)|<span data-ttu-id="1ee04-117">Desplaza el cursor del enumerador desde su posición actual de manera que se omita el número especificado de elementos.</span><span class="sxs-lookup"><span data-stu-id="1ee04-117">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ee04-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1ee04-118">Remarks</span></span>  

 <span data-ttu-id="1ee04-119">La interfaz `ICorProfilerFunctionEnum` es un enumerador.</span><span class="sxs-lookup"><span data-stu-id="1ee04-119">The `ICorProfilerFunctionEnum` interface is an enumerator.</span></span> <span data-ttu-id="1ee04-120">Permite al receptor de una matriz incorporar los cambios de los elementos del remitente a una velocidad que sea adecuada para el receptor.</span><span class="sxs-lookup"><span data-stu-id="1ee04-120">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="1ee04-121">En otras palabras, el receptor es capaz de controlar explícitamente el flujo de elementos de matriz, lo que evita los problemas asociados con pasar matrices de gran tamaño como parámetros de método.</span><span class="sxs-lookup"><span data-stu-id="1ee04-121">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems associated with passing large arrays as method parameters.</span></span>  
  
 <span data-ttu-id="1ee04-122">`ICorProfilerFunctionEnum` enumera las funciones que ya se han compilado con JIT, pero no incluye las funciones que se cargan desde imágenes nativas generadas con Ngen.exe.</span><span class="sxs-lookup"><span data-stu-id="1ee04-122">`ICorProfilerFunctionEnum` enumerates over functions that have already been JIT-compiled, but does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ee04-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1ee04-123">Requirements</span></span>  

 <span data-ttu-id="1ee04-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ee04-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ee04-125">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1ee04-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1ee04-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ee04-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ee04-127">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ee04-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ee04-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ee04-128">See also</span></span>

- [<span data-ttu-id="1ee04-129">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1ee04-129">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="1ee04-130">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="1ee04-130">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="1ee04-131">Método EnumJITedFunctions</span><span class="sxs-lookup"><span data-stu-id="1ee04-131">EnumJITedFunctions Method</span></span>](icorprofilerinfo3-enumjitedfunctions-method.md)
