---
title: "COR_PRF_SNAPSHOT_INFO (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_SNAPSHOT_INFO
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_SNAPSHOT_INFO
helpviewer_keywords: COR_PRF_SNAPSHOT_INFO enumeration [.NET Framework profiling]
ms.assetid: a5906b2a-ad4a-4cc6-a421-2d7d8adf7468
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4573ec44253b1b0f26ae62591db149f0447d3935
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="corprfsnapshotinfo-enumeration"></a><span data-ttu-id="69bd7-102">COR_PRF_SNAPSHOT_INFO (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="69bd7-102">COR_PRF_SNAPSHOT_INFO Enumeration</span></span>
<span data-ttu-id="69bd7-103">Especifica cuánto datos se devolverán con una instantánea de pila en cada llamada al generador de perfiles [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="69bd7-103">Specifies how much data to pass back with a stack snapshot in each call to the profiler's [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69bd7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69bd7-104">Syntax</span></span>  
  
```  
typedef enum _COR_PRF_SNAPSHOT_INFO {  
    COR_PRF_SNAPSHOT_DEFAULT = 0x0,  
    COR_PRF_SNAPSHOT_REGISTER_CONTEXT = 0x1,  
    COR_PRF_SNAPSHOT_X86_OPTIMIZED = 0X2  
} COR_PRF_SNAPSHOT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="69bd7-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="69bd7-105">Members</span></span>  
  
|<span data-ttu-id="69bd7-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="69bd7-106">Members</span></span>|<span data-ttu-id="69bd7-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="69bd7-107">Description</span></span>|  
|-------------|-----------------|  
|`COR_PRF_SNAPSHOT_DEFAULT`|<span data-ttu-id="69bd7-108">Indica que se deben pasar valores para todos los `StackSnapshotCallback` parámetros, excepto el `context` parámetro.</span><span class="sxs-lookup"><span data-stu-id="69bd7-108">Indicates that values must be passed for all `StackSnapshotCallback` parameters, except the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_REGISTER_CONTEXT`|<span data-ttu-id="69bd7-109">Indica que se deben pasar valores para todos los `StackSnapshotCallback` parámetros, incluidos el `context` parámetro.</span><span class="sxs-lookup"><span data-stu-id="69bd7-109">Indicates that values must be passed for all `StackSnapshotCallback` parameters, including the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_X86_OPTIMIZED`|<span data-ttu-id="69bd7-110">Indica que se utilizará un algoritmo de recorrido de pila más sencillo, alternativo.</span><span class="sxs-lookup"><span data-stu-id="69bd7-110">Indicates that a simpler, alternative stack-walking algorithm will be used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69bd7-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="69bd7-111">Remarks</span></span>  
 <span data-ttu-id="69bd7-112">Valores que se proporcionan con el `COR_PRF_SNAPSHOT_INFO` enumeración se pasan como parámetros a la [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="69bd7-112">Values that are provided by the `COR_PRF_SNAPSHOT_INFO` enumeration are passed as parameters to the [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69bd7-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="69bd7-113">Requirements</span></span>  
 <span data-ttu-id="69bd7-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69bd7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69bd7-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="69bd7-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="69bd7-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69bd7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69bd7-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69bd7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69bd7-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="69bd7-118">See Also</span></span>  
 [<span data-ttu-id="69bd7-119">DoStackSnapshot (método)</span><span class="sxs-lookup"><span data-stu-id="69bd7-119">DoStackSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)  
 [<span data-ttu-id="69bd7-120">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="69bd7-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
