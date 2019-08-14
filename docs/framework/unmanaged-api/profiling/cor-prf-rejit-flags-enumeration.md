---
title: Enumeración COR_PRF_REJIT_FLAGS
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
ms.openlocfilehash: c616cb45eadab3a55aa76526d530cb2841e6d5fa
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "68974115"
---
# <a name="cor_prf_rejit_flags-enumeration"></a><span data-ttu-id="4d8fb-102">Enumeración COR_PRF_REJIT_FLAGS</span><span class="sxs-lookup"><span data-stu-id="4d8fb-102">COR_PRF_REJIT_FLAGS Enumeration</span></span>
<span data-ttu-id="4d8fb-103">Contiene valores que indican cómo debe comportarse la API [ICorProfilerInfo10:: RequestReJITWithInliners](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-requestrejitwithinliners-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4d8fb-103">Contains values that indicate how the [ICorProfilerInfo10::RequestReJITWithInliners](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-requestrejitwithinliners-method.md) API should behave.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d8fb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d8fb-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{      
    COR_PRF_REJIT_BLOCK_INLINING = 0x1,
    COR_PRF_REJIT_INLINING_CALLBACKS    = 0x2
} COR_PRF_REJIT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="4d8fb-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="4d8fb-105">Members</span></span>  
  
|<span data-ttu-id="4d8fb-106">Member</span><span class="sxs-lookup"><span data-stu-id="4d8fb-106">Member</span></span>|<span data-ttu-id="4d8fb-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4d8fb-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_REJIT_BLOCK_INLINING`| <span data-ttu-id="4d8fb-108">Los métodos de ReJITted se bloquearán para que no se inlineen en otros métodos.</span><span class="sxs-lookup"><span data-stu-id="4d8fb-108">ReJITted methods will be blocked from being inlined in other methods.</span></span> |  
|`COR_PRF_REJIT_INLINING_CALLBACKS`| <span data-ttu-id="4d8fb-109">Recibir `GetFunctionParameters` devoluciones de llamada para los métodos que insertan los métodos solicitados para ser ReJITted.</span><span class="sxs-lookup"><span data-stu-id="4d8fb-109">Receive `GetFunctionParameters` callbacks for any methods that inline the methods requested to be ReJITted.</span></span> |  

## <a name="requirements"></a><span data-ttu-id="4d8fb-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4d8fb-110">Requirements</span></span>  
 <span data-ttu-id="4d8fb-111">**Select** Consulte [sistemas operativos compatibles con .net Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="4d8fb-111">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
  
 <span data-ttu-id="4d8fb-112">**Encabezado**: Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="4d8fb-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4d8fb-113">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d8fb-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d8fb-114">**Versiones de .NET Framework:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d8fb-114">**.NET Framework Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4d8fb-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d8fb-115">See also</span></span>

- [<span data-ttu-id="4d8fb-116">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="4d8fb-116">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
