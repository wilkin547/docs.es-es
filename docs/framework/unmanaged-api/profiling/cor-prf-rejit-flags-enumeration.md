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
ms.openlocfilehash: 09349674e0cf80649cc948e25a1c476c6f8097e4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716374"
---
# <a name="cor_prf_rejit_flags-enumeration"></a><span data-ttu-id="8af0f-102">COR_PRF_REJIT_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="8af0f-102">COR_PRF_REJIT_FLAGS Enumeration</span></span>

<span data-ttu-id="8af0f-103">Contiene valores que indican cómo debe comportarse la API [ICorProfilerInfo10:: RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8af0f-103">Contains values that indicate how the [ICorProfilerInfo10::RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md) API should behave.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8af0f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8af0f-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{
    COR_PRF_REJIT_BLOCK_INLINING = 0x1,
    COR_PRF_REJIT_INLINING_CALLBACKS    = 0x2
} COR_PRF_REJIT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="8af0f-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="8af0f-105">Members</span></span>  
  
|<span data-ttu-id="8af0f-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="8af0f-106">Member</span></span>|<span data-ttu-id="8af0f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8af0f-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_REJIT_BLOCK_INLINING`| <span data-ttu-id="8af0f-108">Los métodos de ReJITted se bloquearán para que no se inlineen en otros métodos.</span><span class="sxs-lookup"><span data-stu-id="8af0f-108">ReJITted methods will be blocked from being inlined in other methods.</span></span> |  
|`COR_PRF_REJIT_INLINING_CALLBACKS`| <span data-ttu-id="8af0f-109">Recibir `GetFunctionParameters` devoluciones de llamada para los métodos que insertan los métodos solicitados para ser ReJITted.</span><span class="sxs-lookup"><span data-stu-id="8af0f-109">Receive `GetFunctionParameters` callbacks for any methods that inline the methods requested to be ReJITted.</span></span> |  

## <a name="requirements"></a><span data-ttu-id="8af0f-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8af0f-110">Requirements</span></span>  

 <span data-ttu-id="8af0f-111">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="8af0f-111">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>  
  
 <span data-ttu-id="8af0f-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8af0f-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8af0f-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8af0f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8af0f-114">**.NET Framework versiones:**[!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8af0f-114">**.NET Framework Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8af0f-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8af0f-115">See also</span></span>

- [<span data-ttu-id="8af0f-116">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="8af0f-116">Profiling Enumerations</span></span>](profiling-enumerations.md)
