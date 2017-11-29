---
title: IMethodMalloc (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMethodMalloc
api_location: mscorwks.dll
api_type: COM
f1_keywords: IMethodMalloc
helpviewer_keywords: IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8c8ab5dc-557c-473a-82f2-6e403eca7dac
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d246f329f80a76d2c93190fd663c7362418385f7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="a7452-102">IMethodMalloc (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a7452-102">IMethodMalloc Interface</span></span>
<span data-ttu-id="a7452-103">Proporciona un método para asignar memoria para un nuevo cuerpo de función del lenguaje intermedio (MSIL) de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a7452-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a7452-104">La `IMethodMalloc` interfaz es un asignador de memoria simple.</span><span class="sxs-lookup"><span data-stu-id="a7452-104">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="a7452-105">Permite asignar memoria, pero no para liberarlo.</span><span class="sxs-lookup"><span data-stu-id="a7452-105">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a7452-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="a7452-106">Methods</span></span>  
  
|<span data-ttu-id="a7452-107">Método</span><span class="sxs-lookup"><span data-stu-id="a7452-107">Method</span></span>|<span data-ttu-id="a7452-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a7452-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a7452-109">Alloc (método)</span><span class="sxs-lookup"><span data-stu-id="a7452-109">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|<span data-ttu-id="a7452-110">Intenta asignar una cantidad específica de memoria para un nuevo cuerpo de función MSIL.</span><span class="sxs-lookup"><span data-stu-id="a7452-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7452-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a7452-111">Remarks</span></span>  
 <span data-ttu-id="a7452-112">Cada asignador es específico del módulo y garantiza que el cuerpo de función estará en un desplazamiento positivo de la base del módulo.</span><span class="sxs-lookup"><span data-stu-id="a7452-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="a7452-113">La memoria por encima de la base de un módulo puede ser muy valiosa, por lo que debe usarse el asignador para asignar memoria sólo para un cuerpo de función.</span><span class="sxs-lookup"><span data-stu-id="a7452-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7452-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a7452-114">Requirements</span></span>  
 <span data-ttu-id="a7452-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7452-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7452-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a7452-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a7452-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7452-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7452-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7452-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7452-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7452-119">See Also</span></span>  
 [<span data-ttu-id="a7452-120">Interfaces de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="a7452-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
