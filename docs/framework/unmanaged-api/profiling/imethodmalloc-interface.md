---
title: IMethodMalloc (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1941a46a60219d9dd56d162f89baf268f220c102
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="839a0-102">IMethodMalloc (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="839a0-102">IMethodMalloc Interface</span></span>
<span data-ttu-id="839a0-103">Proporciona un método para asignar memoria para un nuevo cuerpo de función del lenguaje intermedio (MSIL) de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="839a0-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="839a0-104">La `IMethodMalloc` interfaz es un asignador de memoria simple.</span><span class="sxs-lookup"><span data-stu-id="839a0-104">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="839a0-105">Permite asignar memoria, pero no para liberarlo.</span><span class="sxs-lookup"><span data-stu-id="839a0-105">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="839a0-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="839a0-106">Methods</span></span>  
  
|<span data-ttu-id="839a0-107">Método</span><span class="sxs-lookup"><span data-stu-id="839a0-107">Method</span></span>|<span data-ttu-id="839a0-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="839a0-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="839a0-109">Alloc (método)</span><span class="sxs-lookup"><span data-stu-id="839a0-109">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|<span data-ttu-id="839a0-110">Intenta asignar una cantidad específica de memoria para un nuevo cuerpo de función MSIL.</span><span class="sxs-lookup"><span data-stu-id="839a0-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="839a0-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="839a0-111">Remarks</span></span>  
 <span data-ttu-id="839a0-112">Cada asignador es específico del módulo y garantiza que el cuerpo de función estará en un desplazamiento positivo de la base del módulo.</span><span class="sxs-lookup"><span data-stu-id="839a0-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="839a0-113">La memoria por encima de la base de un módulo puede ser muy valiosa, por lo que debe usarse el asignador para asignar memoria sólo para un cuerpo de función.</span><span class="sxs-lookup"><span data-stu-id="839a0-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="839a0-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="839a0-114">Requirements</span></span>  
 <span data-ttu-id="839a0-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="839a0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="839a0-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="839a0-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="839a0-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="839a0-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="839a0-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="839a0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="839a0-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="839a0-119">See Also</span></span>  
 [<span data-ttu-id="839a0-120">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="839a0-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
