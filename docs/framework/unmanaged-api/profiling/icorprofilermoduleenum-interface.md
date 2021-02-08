---
description: 'Más información sobre: ICorProfilerModuleEnum (interfaz)'
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
ms.openlocfilehash: 195379e9ad6bce94fc93465fe5e1418c5d8c076d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783825"
---
# <a name="icorprofilermoduleenum-interface"></a><span data-ttu-id="298da-103">ICorProfilerModuleEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="298da-103">ICorProfilerModuleEnum Interface</span></span>

<span data-ttu-id="298da-104">Proporciona métodos para iterar secuencialmente por una colección de módulos cargados por la aplicación o por el generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="298da-104">Provides methods to sequentially iterate through a collection of modules loaded by the application or the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="298da-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="298da-105">Methods</span></span>  
  
|<span data-ttu-id="298da-106">Método</span><span class="sxs-lookup"><span data-stu-id="298da-106">Method</span></span>|<span data-ttu-id="298da-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="298da-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="298da-108">Método Clone</span><span class="sxs-lookup"><span data-stu-id="298da-108">Clone Method</span></span>](icorprofilermoduleenum-clone-method.md)|<span data-ttu-id="298da-109">Obtiene un puntero de interfaz a una copia de esta interfaz `ICorProfilerModuleEnum`.</span><span class="sxs-lookup"><span data-stu-id="298da-109">Gets an interface pointer to a copy of this `ICorProfilerModuleEnum` interface.</span></span>|  
|[<span data-ttu-id="298da-110">Método GetCount</span><span class="sxs-lookup"><span data-stu-id="298da-110">GetCount Method</span></span>](icorprofilermoduleenum-getcount-method.md)|<span data-ttu-id="298da-111">Obtiene el número de módulos administrados que se cargaron en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="298da-111">Gets the number of managed modules that were loaded into the application.</span></span>|  
|[<span data-ttu-id="298da-112">Next (método)</span><span class="sxs-lookup"><span data-stu-id="298da-112">Next Method</span></span>](icorprofilermoduleenum-next-method.md)|<span data-ttu-id="298da-113">Obtiene el número especificado de módulos contiguos de una colección secuencial de módulos, comenzando en la posición actual del enumerador en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="298da-113">Gets the specified number of contiguous modules from a sequential collection of objects, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="298da-114">Reset (Método)</span><span class="sxs-lookup"><span data-stu-id="298da-114">Reset Method</span></span>](icorprofilermoduleenum-reset-method.md)|<span data-ttu-id="298da-115">Mueve el cursor del enumerador a la posición inicial de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="298da-115">Moves the enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="298da-116">Método Skip</span><span class="sxs-lookup"><span data-stu-id="298da-116">Skip Method</span></span>](icorprofilermoduleenum-skip-method.md)|<span data-ttu-id="298da-117">Desplaza la posición del cursor del enumerador de manera que se omite el número especificado de elementos.</span><span class="sxs-lookup"><span data-stu-id="298da-117">Advances the position of the enumerator's cursor so that the specified number of elements are skipped.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="298da-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="298da-118">Remarks</span></span>  

 <span data-ttu-id="298da-119">La interfaz `ICorProfilerModuleEnum` es un enumerador.</span><span class="sxs-lookup"><span data-stu-id="298da-119">The `ICorProfilerModuleEnum` interface is an enumerator.</span></span> <span data-ttu-id="298da-120">Permite al receptor de una matriz incorporar los cambios de los elementos del remitente a una velocidad que sea adecuada para el receptor.</span><span class="sxs-lookup"><span data-stu-id="298da-120">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="298da-121">En otras palabras, el receptor es capaz de controlar explícitamente el flujo de elementos de matriz, lo que evita los problemas asociados con pasar matrices de gran tamaño como parámetros de método.</span><span class="sxs-lookup"><span data-stu-id="298da-121">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems associated with passing large arrays as method parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="298da-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="298da-122">Requirements</span></span>  

 <span data-ttu-id="298da-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="298da-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="298da-124">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="298da-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="298da-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="298da-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="298da-126">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="298da-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="298da-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="298da-127">See also</span></span>

- [<span data-ttu-id="298da-128">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="298da-128">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="298da-129">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="298da-129">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="298da-130">Método EnumModules</span><span class="sxs-lookup"><span data-stu-id="298da-130">EnumModules Method</span></span>](icorprofilerinfo3-enummodules-method.md)
