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
ms.openlocfilehash: b11cf0fadc9142ee291115cf9f0d84e6429834fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455122"
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="96f20-102">IMethodMalloc (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="96f20-102">IMethodMalloc Interface</span></span>
<span data-ttu-id="96f20-103">Proporciona un método para asignar memoria para un nuevo cuerpo de función del lenguaje intermedio (MSIL) de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="96f20-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96f20-104">La `IMethodMalloc` interfaz es un asignador de memoria simple.</span><span class="sxs-lookup"><span data-stu-id="96f20-104">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="96f20-105">Permite asignar memoria, pero no para liberarlo.</span><span class="sxs-lookup"><span data-stu-id="96f20-105">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="96f20-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="96f20-106">Methods</span></span>  
  
|<span data-ttu-id="96f20-107">Método</span><span class="sxs-lookup"><span data-stu-id="96f20-107">Method</span></span>|<span data-ttu-id="96f20-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="96f20-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="96f20-109">Alloc (método)</span><span class="sxs-lookup"><span data-stu-id="96f20-109">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|<span data-ttu-id="96f20-110">Intenta asignar una cantidad específica de memoria para un nuevo cuerpo de función MSIL.</span><span class="sxs-lookup"><span data-stu-id="96f20-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96f20-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="96f20-111">Remarks</span></span>  
 <span data-ttu-id="96f20-112">Cada asignador es específico del módulo y garantiza que el cuerpo de función estará en un desplazamiento positivo de la base del módulo.</span><span class="sxs-lookup"><span data-stu-id="96f20-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="96f20-113">La memoria por encima de la base de un módulo puede ser muy valiosa, por lo que debe usarse el asignador para asignar memoria sólo para un cuerpo de función.</span><span class="sxs-lookup"><span data-stu-id="96f20-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96f20-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="96f20-114">Requirements</span></span>  
 <span data-ttu-id="96f20-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96f20-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96f20-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="96f20-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="96f20-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96f20-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96f20-118">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96f20-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96f20-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="96f20-119">See Also</span></span>  
 [<span data-ttu-id="96f20-120">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="96f20-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
