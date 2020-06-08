---
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
ms.openlocfilehash: 12b97b28383eb7c39f20ee0e88f55d48e60ad956
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84494116"
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="f982b-102">IMethodMalloc (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f982b-102">IMethodMalloc Interface</span></span>
<span data-ttu-id="f982b-103">Proporciona un método para asignar memoria para un nuevo cuerpo de la función del lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="f982b-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f982b-104">La `IMethodMalloc` interfaz es un asignador de memoria simple.</span><span class="sxs-lookup"><span data-stu-id="f982b-104">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="f982b-105">Permite asignar memoria, pero no para liberarla.</span><span class="sxs-lookup"><span data-stu-id="f982b-105">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f982b-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="f982b-106">Methods</span></span>  
  
|<span data-ttu-id="f982b-107">Método</span><span class="sxs-lookup"><span data-stu-id="f982b-107">Method</span></span>|<span data-ttu-id="f982b-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="f982b-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f982b-109">Alloc (Método)</span><span class="sxs-lookup"><span data-stu-id="f982b-109">Alloc Method</span></span>](imethodmalloc-alloc-method.md)|<span data-ttu-id="f982b-110">Intenta asignar una cantidad de memoria especificada para un nuevo cuerpo de función de MSIL.</span><span class="sxs-lookup"><span data-stu-id="f982b-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f982b-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f982b-111">Remarks</span></span>  
 <span data-ttu-id="f982b-112">Cada asignador es específico del módulo y garantiza que el cuerpo de la función estará en un desplazamiento positivo de la base del módulo.</span><span class="sxs-lookup"><span data-stu-id="f982b-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="f982b-113">La memoria que está por encima de la base de un módulo puede ser precioso, por lo que se debe usar el asignador para asignar memoria solo para el cuerpo de una función.</span><span class="sxs-lookup"><span data-stu-id="f982b-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f982b-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f982b-114">Requirements</span></span>  
 <span data-ttu-id="f982b-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f982b-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f982b-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f982b-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f982b-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f982b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f982b-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f982b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f982b-119">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="f982b-119">See also</span></span>

- [<span data-ttu-id="f982b-120">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="f982b-120">Profiling Interfaces</span></span>](profiling-interfaces.md)
