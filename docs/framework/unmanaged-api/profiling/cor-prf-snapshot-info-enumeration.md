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
ms.openlocfilehash: 6168c5b27868a261871b292e17ca02b04ae89917
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500785"
---
# <a name="cor_prf_snapshot_info-enumeration"></a><span data-ttu-id="6197c-102">COR_PRF_SNAPSHOT_INFO (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="6197c-102">COR_PRF_SNAPSHOT_INFO Enumeration</span></span>
<span data-ttu-id="6197c-103">Especifica la cantidad de datos que se van a devolver con una instantánea de pila en cada llamada a la función [StackSnapshotCallback](stacksnapshotcallback-function.md) del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="6197c-103">Specifies how much data to pass back with a stack snapshot in each call to the profiler's [StackSnapshotCallback](stacksnapshotcallback-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6197c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6197c-104">Syntax</span></span>  
  
```cpp  
typedef enum _COR_PRF_SNAPSHOT_INFO {  
    COR_PRF_SNAPSHOT_DEFAULT = 0x0,  
    COR_PRF_SNAPSHOT_REGISTER_CONTEXT = 0x1,  
    COR_PRF_SNAPSHOT_X86_OPTIMIZED = 0X2  
} COR_PRF_SNAPSHOT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="6197c-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="6197c-105">Members</span></span>  
  
|<span data-ttu-id="6197c-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="6197c-106">Members</span></span>|<span data-ttu-id="6197c-107">Description</span><span class="sxs-lookup"><span data-stu-id="6197c-107">Description</span></span>|  
|-------------|-----------------|  
|`COR_PRF_SNAPSHOT_DEFAULT`|<span data-ttu-id="6197c-108">Indica que se deben pasar valores para todos los `StackSnapshotCallback` parámetros, excepto el `context` parámetro.</span><span class="sxs-lookup"><span data-stu-id="6197c-108">Indicates that values must be passed for all `StackSnapshotCallback` parameters, except the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_REGISTER_CONTEXT`|<span data-ttu-id="6197c-109">Indica que se deben pasar valores para todos los `StackSnapshotCallback` parámetros, incluido el `context` parámetro.</span><span class="sxs-lookup"><span data-stu-id="6197c-109">Indicates that values must be passed for all `StackSnapshotCallback` parameters, including the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_X86_OPTIMIZED`|<span data-ttu-id="6197c-110">Indica que se usará un algoritmo de recorrido de pila alternativo más sencillo.</span><span class="sxs-lookup"><span data-stu-id="6197c-110">Indicates that a simpler, alternative stack-walking algorithm will be used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6197c-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6197c-111">Remarks</span></span>  
 <span data-ttu-id="6197c-112">Los valores que proporciona la `COR_PRF_SNAPSHOT_INFO` enumeración se pasan como parámetros al método [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) .</span><span class="sxs-lookup"><span data-stu-id="6197c-112">Values that are provided by the `COR_PRF_SNAPSHOT_INFO` enumeration are passed as parameters to the [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6197c-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6197c-113">Requirements</span></span>  
 <span data-ttu-id="6197c-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6197c-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6197c-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6197c-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6197c-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6197c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6197c-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6197c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6197c-118">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="6197c-118">See also</span></span>

- [<span data-ttu-id="6197c-119">Método DoStackSnapshot</span><span class="sxs-lookup"><span data-stu-id="6197c-119">DoStackSnapshot Method</span></span>](icorprofilerinfo2-dostacksnapshot-method.md)
- [<span data-ttu-id="6197c-120">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="6197c-120">Profiling Enumerations</span></span>](profiling-enumerations.md)
