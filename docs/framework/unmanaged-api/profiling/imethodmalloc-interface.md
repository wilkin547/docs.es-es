---
description: 'Más información acerca de: interfaz IMethodMalloc'
title: IMethodMalloc (Interfaz)
ms.date: 03/30/2017
api_name:
- IMethodMalloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc
helpviewer_keywords:
- IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8c8ab5dc-557c-473a-82f2-6e403eca7dac
topic_type:
- apiref
ms.openlocfilehash: 6b84ac0ddb49718d24b2cad174613bc311dc509b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736965"
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="a861a-103">IMethodMalloc (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a861a-103">IMethodMalloc Interface</span></span>

<span data-ttu-id="a861a-104">Proporciona un método para asignar memoria para un nuevo cuerpo de la función del lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="a861a-104">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a861a-105">La `IMethodMalloc` interfaz es un asignador de memoria simple.</span><span class="sxs-lookup"><span data-stu-id="a861a-105">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="a861a-106">Permite asignar memoria, pero no para liberarla.</span><span class="sxs-lookup"><span data-stu-id="a861a-106">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a861a-107">Métodos</span><span class="sxs-lookup"><span data-stu-id="a861a-107">Methods</span></span>  
  
|<span data-ttu-id="a861a-108">Método</span><span class="sxs-lookup"><span data-stu-id="a861a-108">Method</span></span>|<span data-ttu-id="a861a-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="a861a-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a861a-110">Alloc (Método)</span><span class="sxs-lookup"><span data-stu-id="a861a-110">Alloc Method</span></span>](imethodmalloc-alloc-method.md)|<span data-ttu-id="a861a-111">Intenta asignar una cantidad de memoria especificada para un nuevo cuerpo de función de MSIL.</span><span class="sxs-lookup"><span data-stu-id="a861a-111">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a861a-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a861a-112">Remarks</span></span>  

 <span data-ttu-id="a861a-113">Cada asignador es específico del módulo y garantiza que el cuerpo de la función estará en un desplazamiento positivo de la base del módulo.</span><span class="sxs-lookup"><span data-stu-id="a861a-113">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="a861a-114">La memoria que está por encima de la base de un módulo puede ser precioso, por lo que se debe usar el asignador para asignar memoria solo para el cuerpo de una función.</span><span class="sxs-lookup"><span data-stu-id="a861a-114">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a861a-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a861a-115">Requirements</span></span>  

 <span data-ttu-id="a861a-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a861a-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a861a-117">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a861a-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a861a-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a861a-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a861a-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a861a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a861a-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="a861a-120">See also</span></span>

- [<span data-ttu-id="a861a-121">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="a861a-121">Profiling Interfaces</span></span>](profiling-interfaces.md)
