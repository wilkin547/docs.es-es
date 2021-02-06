---
description: 'Más información acerca de: interfaz ICorProfilerThreadEnum'
title: ICorProfilerThreadEnum (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum
helpviewer_keywords:
- ICorProfilerThreadEnum interface [.NET Framework profiling]
ms.assetid: 1e35031b-e095-4c14-9644-8deeb3081e0b
topic_type:
- apiref
ms.openlocfilehash: 035296412aabf20503588a558c8e8ccc1338210e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636398"
---
# <a name="icorprofilerthreadenum-interface"></a><span data-ttu-id="8a059-103">ICorProfilerThreadEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8a059-103">ICorProfilerThreadEnum Interface</span></span>

<span data-ttu-id="8a059-104">Proporciona métodos para iterar secuencialmente por una colección de subprocesos en Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="8a059-104">Provides methods to sequentially iterate through a collection of threads in the common language runtime.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8a059-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="8a059-105">Methods</span></span>  
  
|<span data-ttu-id="8a059-106">Método</span><span class="sxs-lookup"><span data-stu-id="8a059-106">Method</span></span>|<span data-ttu-id="8a059-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a059-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8a059-108">Método Clone</span><span class="sxs-lookup"><span data-stu-id="8a059-108">Clone Method</span></span>](icorprofilerthreadenum-clone-method.md)|<span data-ttu-id="8a059-109">Obtiene un puntero de interfaz a una copia de esta interfaz `ICorProfilerThreadEnum`.</span><span class="sxs-lookup"><span data-stu-id="8a059-109">Gets an interface pointer to a copy of this `ICorProfilerThreadEnum` interface.</span></span>|  
|[<span data-ttu-id="8a059-110">Método GetCount</span><span class="sxs-lookup"><span data-stu-id="8a059-110">GetCount Method</span></span>](icorprofilerthreadenum-getcount-method.md)|<span data-ttu-id="8a059-111">Obtiene el número de subprocesos utilizados por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8a059-111">Gets the number of threads that are used by the application.</span></span>|  
|[<span data-ttu-id="8a059-112">Next (método)</span><span class="sxs-lookup"><span data-stu-id="8a059-112">Next Method</span></span>](icorprofilerthreadenum-next-method.md)|<span data-ttu-id="8a059-113">Obtiene el número especificado de subprocesos contiguos de una colección secuencial de subprocesos, comenzando en la posición actual del enumerador en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="8a059-113">Gets the specified number of contiguous threads from a sequential collection of threads, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="8a059-114">Reset (Método)</span><span class="sxs-lookup"><span data-stu-id="8a059-114">Reset Method</span></span>](icorprofilerthreadenum-reset-method.md)|<span data-ttu-id="8a059-115">Mueve el cursor del enumerador a la posición inicial de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="8a059-115">Moves the enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="8a059-116">Método Skip</span><span class="sxs-lookup"><span data-stu-id="8a059-116">Skip Method</span></span>](icorprofilerthreadenum-skip-method.md)|<span data-ttu-id="8a059-117">Desplaza el cursor del enumerador desde su posición actual para omitir el número especificado de elementos.</span><span class="sxs-lookup"><span data-stu-id="8a059-117">Advances the enumerator's cursor from its current position to skip the specified number of elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a059-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8a059-118">Remarks</span></span>  

 <span data-ttu-id="8a059-119">La interfaz `ICorProfilerThreadEnum` es un enumerador.</span><span class="sxs-lookup"><span data-stu-id="8a059-119">The `ICorProfilerThreadEnum` interface is an enumerator.</span></span> <span data-ttu-id="8a059-120">Permite al receptor de una matriz incorporar los cambios de los elementos del remitente a una velocidad que sea adecuada para el receptor.</span><span class="sxs-lookup"><span data-stu-id="8a059-120">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="8a059-121">En otras palabras, el receptor es capaz de controlar explícitamente el flujo de elementos de matriz, lo que evita los problemas asociados con pasar matrices de gran tamaño como parámetros de método.</span><span class="sxs-lookup"><span data-stu-id="8a059-121">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems associated with passing large arrays as method parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a059-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8a059-122">Requirements</span></span>  

 <span data-ttu-id="8a059-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a059-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a059-124">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8a059-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8a059-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a059-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a059-126">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a059-126">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a059-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a059-127">See also</span></span>

- [<span data-ttu-id="8a059-128">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8a059-128">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="8a059-129">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="8a059-129">Profiling Interfaces</span></span>](profiling-interfaces.md)
