---
title: COR_PRF_SNAPSHOT_INFO (Enumeración)
ms.date: 03/30/2017
api_name:
- COR_PRF_SNAPSHOT_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_SNAPSHOT_INFO
helpviewer_keywords:
- COR_PRF_SNAPSHOT_INFO enumeration [.NET Framework profiling]
ms.assetid: a5906b2a-ad4a-4cc6-a421-2d7d8adf7468
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9d6713a7f54f6a6d8dbf261ad45304e6ddbe24c0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450722"
---
# <a name="corprfsnapshotinfo-enumeration"></a><span data-ttu-id="d006a-102">COR_PRF_SNAPSHOT_INFO (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d006a-102">COR_PRF_SNAPSHOT_INFO Enumeration</span></span>
<span data-ttu-id="d006a-103">Especifica cuánto datos se devolverán con una instantánea de pila en cada llamada al generador de perfiles [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="d006a-103">Specifies how much data to pass back with a stack snapshot in each call to the profiler's [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d006a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d006a-104">Syntax</span></span>  
  
```  
typedef enum _COR_PRF_SNAPSHOT_INFO {  
    COR_PRF_SNAPSHOT_DEFAULT = 0x0,  
    COR_PRF_SNAPSHOT_REGISTER_CONTEXT = 0x1,  
    COR_PRF_SNAPSHOT_X86_OPTIMIZED = 0X2  
} COR_PRF_SNAPSHOT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="d006a-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="d006a-105">Members</span></span>  
  
|<span data-ttu-id="d006a-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="d006a-106">Members</span></span>|<span data-ttu-id="d006a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d006a-107">Description</span></span>|  
|-------------|-----------------|  
|`COR_PRF_SNAPSHOT_DEFAULT`|<span data-ttu-id="d006a-108">Indica que se deben pasar valores para todos los `StackSnapshotCallback` parámetros, excepto el `context` parámetro.</span><span class="sxs-lookup"><span data-stu-id="d006a-108">Indicates that values must be passed for all `StackSnapshotCallback` parameters, except the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_REGISTER_CONTEXT`|<span data-ttu-id="d006a-109">Indica que se deben pasar valores para todos los `StackSnapshotCallback` parámetros, incluidos el `context` parámetro.</span><span class="sxs-lookup"><span data-stu-id="d006a-109">Indicates that values must be passed for all `StackSnapshotCallback` parameters, including the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_X86_OPTIMIZED`|<span data-ttu-id="d006a-110">Indica que se utilizará un algoritmo de recorrido de pila más sencillo, alternativo.</span><span class="sxs-lookup"><span data-stu-id="d006a-110">Indicates that a simpler, alternative stack-walking algorithm will be used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d006a-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d006a-111">Remarks</span></span>  
 <span data-ttu-id="d006a-112">Valores que se proporcionan con el `COR_PRF_SNAPSHOT_INFO` enumeración se pasan como parámetros a la [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="d006a-112">Values that are provided by the `COR_PRF_SNAPSHOT_INFO` enumeration are passed as parameters to the [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d006a-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d006a-113">Requirements</span></span>  
 <span data-ttu-id="d006a-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d006a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d006a-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d006a-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d006a-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d006a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d006a-117">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d006a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d006a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="d006a-118">See Also</span></span>  
 [<span data-ttu-id="d006a-119">DoStackSnapshot (método)</span><span class="sxs-lookup"><span data-stu-id="d006a-119">DoStackSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)  
 [<span data-ttu-id="d006a-120">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="d006a-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
