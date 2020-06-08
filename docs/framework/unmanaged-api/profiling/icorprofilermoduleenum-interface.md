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
ms.openlocfilehash: fe11c0bbe273ae07cdae43f681a558e07a291ffb
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84494896"
---
# <a name="icorprofilermoduleenum-interface"></a><span data-ttu-id="4fabd-102">ICorProfilerModuleEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4fabd-102">ICorProfilerModuleEnum Interface</span></span>
<span data-ttu-id="4fabd-103">Proporciona métodos para iterar secuencialmente por una colección de módulos cargados por la aplicación o por el generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="4fabd-103">Provides methods to sequentially iterate through a collection of modules loaded by the application or the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4fabd-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="4fabd-104">Methods</span></span>  
  
|<span data-ttu-id="4fabd-105">Método</span><span class="sxs-lookup"><span data-stu-id="4fabd-105">Method</span></span>|<span data-ttu-id="4fabd-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="4fabd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4fabd-107">Método Clone</span><span class="sxs-lookup"><span data-stu-id="4fabd-107">Clone Method</span></span>](icorprofilermoduleenum-clone-method.md)|<span data-ttu-id="4fabd-108">Obtiene un puntero de interfaz a una copia de esta interfaz `ICorProfilerModuleEnum`.</span><span class="sxs-lookup"><span data-stu-id="4fabd-108">Gets an interface pointer to a copy of this `ICorProfilerModuleEnum` interface.</span></span>|  
|[<span data-ttu-id="4fabd-109">Método GetCount</span><span class="sxs-lookup"><span data-stu-id="4fabd-109">GetCount Method</span></span>](icorprofilermoduleenum-getcount-method.md)|<span data-ttu-id="4fabd-110">Obtiene el número de módulos administrados que se cargaron en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4fabd-110">Gets the number of managed modules that were loaded into the application.</span></span>|  
|[<span data-ttu-id="4fabd-111">Next (Método)</span><span class="sxs-lookup"><span data-stu-id="4fabd-111">Next Method</span></span>](icorprofilermoduleenum-next-method.md)|<span data-ttu-id="4fabd-112">Obtiene el número especificado de módulos contiguos de una colección secuencial de módulos, comenzando en la posición actual del enumerador en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="4fabd-112">Gets the specified number of contiguous modules from a sequential collection of objects, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="4fabd-113">Reset (Método)</span><span class="sxs-lookup"><span data-stu-id="4fabd-113">Reset Method</span></span>](icorprofilermoduleenum-reset-method.md)|<span data-ttu-id="4fabd-114">Mueve el cursor del enumerador a la posición inicial de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="4fabd-114">Moves the enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="4fabd-115">Método Skip</span><span class="sxs-lookup"><span data-stu-id="4fabd-115">Skip Method</span></span>](icorprofilermoduleenum-skip-method.md)|<span data-ttu-id="4fabd-116">Desplaza la posición del cursor del enumerador de manera que se omite el número especificado de elementos.</span><span class="sxs-lookup"><span data-stu-id="4fabd-116">Advances the position of the enumerator's cursor so that the specified number of elements are skipped.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4fabd-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4fabd-117">Remarks</span></span>  
 <span data-ttu-id="4fabd-118">La interfaz `ICorProfilerModuleEnum` es un enumerador.</span><span class="sxs-lookup"><span data-stu-id="4fabd-118">The `ICorProfilerModuleEnum` interface is an enumerator.</span></span> <span data-ttu-id="4fabd-119">Permite al receptor de una matriz incorporar los cambios de los elementos del remitente a una velocidad que sea adecuada para el receptor.</span><span class="sxs-lookup"><span data-stu-id="4fabd-119">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="4fabd-120">En otras palabras, el receptor es capaz de controlar explícitamente el flujo de elementos de matriz, lo que evita los problemas asociados con pasar matrices de gran tamaño como parámetros de método.</span><span class="sxs-lookup"><span data-stu-id="4fabd-120">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems associated with passing large arrays as method parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fabd-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4fabd-121">Requirements</span></span>  
 <span data-ttu-id="4fabd-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4fabd-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fabd-123">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4fabd-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4fabd-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4fabd-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4fabd-125">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fabd-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fabd-126">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="4fabd-126">See also</span></span>

- [<span data-ttu-id="4fabd-127">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4fabd-127">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="4fabd-128">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="4fabd-128">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="4fabd-129">Método EnumModules</span><span class="sxs-lookup"><span data-stu-id="4fabd-129">EnumModules Method</span></span>](icorprofilerinfo3-enummodules-method.md)
