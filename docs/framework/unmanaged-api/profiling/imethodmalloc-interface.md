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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6f5c21d329ed35f82e36c2d88ac911401799e820
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54596025"
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="c16c1-102">IMethodMalloc (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c16c1-102">IMethodMalloc Interface</span></span>
<span data-ttu-id="c16c1-103">Proporciona un método para asignar memoria para un nuevo cuerpo de función de lenguaje intermedio (MSIL) de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c16c1-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c16c1-104">El `IMethodMalloc` interfaz es un asignador de memoria simple.</span><span class="sxs-lookup"><span data-stu-id="c16c1-104">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="c16c1-105">Permite asignar memoria, pero no a lo libere.</span><span class="sxs-lookup"><span data-stu-id="c16c1-105">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c16c1-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="c16c1-106">Methods</span></span>  
  
|<span data-ttu-id="c16c1-107">Método</span><span class="sxs-lookup"><span data-stu-id="c16c1-107">Method</span></span>|<span data-ttu-id="c16c1-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="c16c1-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c16c1-109">Alloc (método)</span><span class="sxs-lookup"><span data-stu-id="c16c1-109">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|<span data-ttu-id="c16c1-110">Intenta asignar una cantidad de memoria especificada para un nuevo cuerpo de función MSIL.</span><span class="sxs-lookup"><span data-stu-id="c16c1-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c16c1-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c16c1-111">Remarks</span></span>  
 <span data-ttu-id="c16c1-112">Cada asignador es específico del módulo y garantiza que el cuerpo de la función estará en un desplazamiento positivo de la base del módulo.</span><span class="sxs-lookup"><span data-stu-id="c16c1-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="c16c1-113">Memoria por encima de la base de un módulo puede ser valioso, por lo que se debe usar el asignador para asignar memoria sólo para un cuerpo de función.</span><span class="sxs-lookup"><span data-stu-id="c16c1-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c16c1-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c16c1-114">Requirements</span></span>  
 <span data-ttu-id="c16c1-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c16c1-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c16c1-116">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c16c1-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c16c1-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c16c1-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c16c1-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c16c1-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c16c1-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="c16c1-119">See also</span></span>
- [<span data-ttu-id="c16c1-120">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="c16c1-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
