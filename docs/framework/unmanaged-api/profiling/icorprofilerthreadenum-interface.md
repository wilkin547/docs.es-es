---
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
ms.openlocfilehash: 147694431d2c378b856577ef5a60e8a8b4e9a7a7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721223"
---
# <a name="icorprofilerthreadenum-interface"></a><span data-ttu-id="46d44-102">ICorProfilerThreadEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="46d44-102">ICorProfilerThreadEnum Interface</span></span>

<span data-ttu-id="46d44-103">Proporciona métodos para iterar secuencialmente por una colección de subprocesos en Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="46d44-103">Provides methods to sequentially iterate through a collection of threads in the common language runtime.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="46d44-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="46d44-104">Methods</span></span>  
  
|<span data-ttu-id="46d44-105">Método</span><span class="sxs-lookup"><span data-stu-id="46d44-105">Method</span></span>|<span data-ttu-id="46d44-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="46d44-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="46d44-107">Clone (Método)</span><span class="sxs-lookup"><span data-stu-id="46d44-107">Clone Method</span></span>](icorprofilerthreadenum-clone-method.md)|<span data-ttu-id="46d44-108">Obtiene un puntero de interfaz a una copia de esta interfaz `ICorProfilerThreadEnum`.</span><span class="sxs-lookup"><span data-stu-id="46d44-108">Gets an interface pointer to a copy of this `ICorProfilerThreadEnum` interface.</span></span>|  
|[<span data-ttu-id="46d44-109">GetCount (Método)</span><span class="sxs-lookup"><span data-stu-id="46d44-109">GetCount Method</span></span>](icorprofilerthreadenum-getcount-method.md)|<span data-ttu-id="46d44-110">Obtiene el número de subprocesos utilizados por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="46d44-110">Gets the number of threads that are used by the application.</span></span>|  
|[<span data-ttu-id="46d44-111">Next (Método)</span><span class="sxs-lookup"><span data-stu-id="46d44-111">Next Method</span></span>](icorprofilerthreadenum-next-method.md)|<span data-ttu-id="46d44-112">Obtiene el número especificado de subprocesos contiguos de una colección secuencial de subprocesos, comenzando en la posición actual del enumerador en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="46d44-112">Gets the specified number of contiguous threads from a sequential collection of threads, starting at the enumerator's current position in the sequence.</span></span>|  
|[<span data-ttu-id="46d44-113">Reset (Método)</span><span class="sxs-lookup"><span data-stu-id="46d44-113">Reset Method</span></span>](icorprofilerthreadenum-reset-method.md)|<span data-ttu-id="46d44-114">Mueve el cursor del enumerador a la posición inicial de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="46d44-114">Moves the enumerator's cursor to the starting position of the sequence.</span></span>|  
|[<span data-ttu-id="46d44-115">Skip (Método)</span><span class="sxs-lookup"><span data-stu-id="46d44-115">Skip Method</span></span>](icorprofilerthreadenum-skip-method.md)|<span data-ttu-id="46d44-116">Desplaza el cursor del enumerador desde su posición actual para omitir el número especificado de elementos.</span><span class="sxs-lookup"><span data-stu-id="46d44-116">Advances the enumerator's cursor from its current position to skip the specified number of elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46d44-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="46d44-117">Remarks</span></span>  

 <span data-ttu-id="46d44-118">La interfaz `ICorProfilerThreadEnum` es un enumerador.</span><span class="sxs-lookup"><span data-stu-id="46d44-118">The `ICorProfilerThreadEnum` interface is an enumerator.</span></span> <span data-ttu-id="46d44-119">Permite al receptor de una matriz incorporar los cambios de los elementos del remitente a una velocidad que sea adecuada para el receptor.</span><span class="sxs-lookup"><span data-stu-id="46d44-119">It allows the receiver of an array to pull elements from the sender at a rate that is appropriate for the receiver.</span></span> <span data-ttu-id="46d44-120">En otras palabras, el receptor es capaz de controlar explícitamente el flujo de elementos de matriz, lo que evita los problemas asociados con pasar matrices de gran tamaño como parámetros de método.</span><span class="sxs-lookup"><span data-stu-id="46d44-120">In other words, the receiver is able to explicitly control the flow of array elements, thereby avoiding the problems associated with passing large arrays as method parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46d44-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="46d44-121">Requirements</span></span>  

 <span data-ttu-id="46d44-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46d44-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46d44-123">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="46d44-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="46d44-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46d44-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46d44-125">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46d44-125">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46d44-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="46d44-126">See also</span></span>

- [<span data-ttu-id="46d44-127">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="46d44-127">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="46d44-128">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="46d44-128">Profiling Interfaces</span></span>](profiling-interfaces.md)
