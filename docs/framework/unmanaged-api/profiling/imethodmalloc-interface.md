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
ms.openlocfilehash: e9cbf4551c2f8b183e9e6c37a74b13aff3a19ec1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76860987"
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="4df5c-102">IMethodMalloc (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4df5c-102">IMethodMalloc Interface</span></span>
<span data-ttu-id="4df5c-103">Proporciona un método para asignar memoria para un nuevo cuerpo de la función del lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="4df5c-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4df5c-104">La interfaz de `IMethodMalloc` es un asignador de memoria simple.</span><span class="sxs-lookup"><span data-stu-id="4df5c-104">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="4df5c-105">Permite asignar memoria, pero no para liberarla.</span><span class="sxs-lookup"><span data-stu-id="4df5c-105">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4df5c-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="4df5c-106">Methods</span></span>  
  
|<span data-ttu-id="4df5c-107">Método</span><span class="sxs-lookup"><span data-stu-id="4df5c-107">Method</span></span>|<span data-ttu-id="4df5c-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="4df5c-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4df5c-109">Alloc (método)</span><span class="sxs-lookup"><span data-stu-id="4df5c-109">Alloc Method</span></span>](imethodmalloc-alloc-method.md)|<span data-ttu-id="4df5c-110">Intenta asignar una cantidad de memoria especificada para un nuevo cuerpo de función de MSIL.</span><span class="sxs-lookup"><span data-stu-id="4df5c-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4df5c-111">Notas</span><span class="sxs-lookup"><span data-stu-id="4df5c-111">Remarks</span></span>  
 <span data-ttu-id="4df5c-112">Cada asignador es específico del módulo y garantiza que el cuerpo de la función estará en un desplazamiento positivo de la base del módulo.</span><span class="sxs-lookup"><span data-stu-id="4df5c-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="4df5c-113">La memoria que está por encima de la base de un módulo puede ser precioso, por lo que se debe usar el asignador para asignar memoria solo para el cuerpo de una función.</span><span class="sxs-lookup"><span data-stu-id="4df5c-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4df5c-114">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="4df5c-114">Requirements</span></span>  
 <span data-ttu-id="4df5c-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4df5c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4df5c-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4df5c-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4df5c-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4df5c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4df5c-118">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4df5c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4df5c-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="4df5c-119">See also</span></span>

- [<span data-ttu-id="4df5c-120">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="4df5c-120">Profiling Interfaces</span></span>](profiling-interfaces.md)
