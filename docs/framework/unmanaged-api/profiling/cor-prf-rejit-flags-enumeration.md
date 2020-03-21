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
ms.openlocfilehash: 8fc5f1a488826d8adc6aecb8ef122609bebbe813
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177097"
---
# <a name="cor_prf_rejit_flags-enumeration"></a><span data-ttu-id="c6e1e-102">COR_PRF_REJIT_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="c6e1e-102">COR_PRF_REJIT_FLAGS Enumeration</span></span>
<span data-ttu-id="c6e1e-103">Contiene valores que indican cómo debe comportarse la API [ICorProfilerInfo10::RequestReJITWithInliners.](icorprofilerinfo10-requestrejitwithinliners-method.md)</span><span class="sxs-lookup"><span data-stu-id="c6e1e-103">Contains values that indicate how the [ICorProfilerInfo10::RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md) API should behave.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6e1e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c6e1e-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{
    COR_PRF_REJIT_BLOCK_INLINING = 0x1,
    COR_PRF_REJIT_INLINING_CALLBACKS    = 0x2
} COR_PRF_REJIT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="c6e1e-105">Members</span><span class="sxs-lookup"><span data-stu-id="c6e1e-105">Members</span></span>  
  
|<span data-ttu-id="c6e1e-106">Member</span><span class="sxs-lookup"><span data-stu-id="c6e1e-106">Member</span></span>|<span data-ttu-id="c6e1e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c6e1e-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_REJIT_BLOCK_INLINING`| <span data-ttu-id="c6e1e-108">Los métodos ReJITted no se bloquearán para que no se inlineen en otros métodos.</span><span class="sxs-lookup"><span data-stu-id="c6e1e-108">ReJITted methods will be blocked from being inlined in other methods.</span></span> |  
|`COR_PRF_REJIT_INLINING_CALLBACKS`| <span data-ttu-id="c6e1e-109">Reciba `GetFunctionParameters` devoluciones de llamada para cualquier método que inlinee los métodos solicitados para ser ReJITted.</span><span class="sxs-lookup"><span data-stu-id="c6e1e-109">Receive `GetFunctionParameters` callbacks for any methods that inline the methods requested to be ReJITted.</span></span> |  

## <a name="requirements"></a><span data-ttu-id="c6e1e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c6e1e-110">Requirements</span></span>  
 <span data-ttu-id="c6e1e-111">**Plataformas:** Consulte [Sistemas operativos compatibles con .NET Core](../../../core/install/dependencies.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="c6e1e-111">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>  
  
 <span data-ttu-id="c6e1e-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c6e1e-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c6e1e-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6e1e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6e1e-114">**Versiones de .NET Framework:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6e1e-114">**.NET Framework Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c6e1e-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c6e1e-115">See also</span></span>

- [<span data-ttu-id="c6e1e-116">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="c6e1e-116">Profiling Enumerations</span></span>](profiling-enumerations.md)
