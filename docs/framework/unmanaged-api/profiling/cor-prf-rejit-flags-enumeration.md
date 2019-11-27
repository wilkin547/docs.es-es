---
title: COR_PRF_REJIT_FLAGS (Enumeración)
ms.date: 08/06/2019
api_name:
- COR_PRF_REJIT_FLAGS Enumeration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_REJIT_FLAGS
helpviewer_keywords:
- COR_PRF_REJIT_FLAGS enumeration [.NET Framework profiling]
topic_type:
- apiref
author: davmason
ms.author: davmason
ms.openlocfilehash: 66933b3778807b40f1d39d8b4c565c334328812f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450401"
---
# <a name="cor_prf_rejit_flags-enumeration"></a><span data-ttu-id="e75ff-102">COR_PRF_REJIT_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="e75ff-102">COR_PRF_REJIT_FLAGS Enumeration</span></span>
<span data-ttu-id="e75ff-103">Contiene valores que indican cómo debe comportarse la API [ICorProfilerInfo10:: RequestReJITWithInliners](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-requestrejitwithinliners-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e75ff-103">Contains values that indicate how the [ICorProfilerInfo10::RequestReJITWithInliners](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-requestrejitwithinliners-method.md) API should behave.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e75ff-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e75ff-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{      
    COR_PRF_REJIT_BLOCK_INLINING = 0x1,
    COR_PRF_REJIT_INLINING_CALLBACKS    = 0x2
} COR_PRF_REJIT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="e75ff-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="e75ff-105">Members</span></span>  
  
|<span data-ttu-id="e75ff-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="e75ff-106">Member</span></span>|<span data-ttu-id="e75ff-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e75ff-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_REJIT_BLOCK_INLINING`| <span data-ttu-id="e75ff-108">Los métodos de ReJITted se bloquearán para que no se inlineen en otros métodos.</span><span class="sxs-lookup"><span data-stu-id="e75ff-108">ReJITted methods will be blocked from being inlined in other methods.</span></span> |  
|`COR_PRF_REJIT_INLINING_CALLBACKS`| <span data-ttu-id="e75ff-109">Reciba `GetFunctionParameters` devoluciones de llamada para los métodos que insertan los métodos solicitados para ser ReJITted.</span><span class="sxs-lookup"><span data-stu-id="e75ff-109">Receive `GetFunctionParameters` callbacks for any methods that inline the methods requested to be ReJITted.</span></span> |  

## <a name="requirements"></a><span data-ttu-id="e75ff-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e75ff-110">Requirements</span></span>  
 <span data-ttu-id="e75ff-111">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="e75ff-111">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>  
  
 <span data-ttu-id="e75ff-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e75ff-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e75ff-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e75ff-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e75ff-114">**Versiones de .NET Framework:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e75ff-114">**.NET Framework Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e75ff-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="e75ff-115">See also</span></span>

- [<span data-ttu-id="e75ff-116">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="e75ff-116">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
