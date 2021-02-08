---
description: 'Más información acerca de: enumeración COR_PRF_REJIT_FLAGS'
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
ms.openlocfilehash: a27b6d90b51254560f25fbadb18ac95fe838ab2b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789026"
---
# <a name="cor_prf_rejit_flags-enumeration"></a><span data-ttu-id="33bf2-103">COR_PRF_REJIT_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="33bf2-103">COR_PRF_REJIT_FLAGS Enumeration</span></span>

<span data-ttu-id="33bf2-104">Contiene valores que indican cómo debe comportarse la API [ICorProfilerInfo10:: RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md) .</span><span class="sxs-lookup"><span data-stu-id="33bf2-104">Contains values that indicate how the [ICorProfilerInfo10::RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md) API should behave.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33bf2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33bf2-105">Syntax</span></span>  
  
```cpp  
typedef enum  
{
    COR_PRF_REJIT_BLOCK_INLINING = 0x1,
    COR_PRF_REJIT_INLINING_CALLBACKS    = 0x2
} COR_PRF_REJIT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="33bf2-106">Members</span><span class="sxs-lookup"><span data-stu-id="33bf2-106">Members</span></span>  
  
|<span data-ttu-id="33bf2-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="33bf2-107">Member</span></span>|<span data-ttu-id="33bf2-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="33bf2-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_REJIT_BLOCK_INLINING`| <span data-ttu-id="33bf2-109">Los métodos de ReJITted se bloquearán para que no se inlineen en otros métodos.</span><span class="sxs-lookup"><span data-stu-id="33bf2-109">ReJITted methods will be blocked from being inlined in other methods.</span></span> |  
|`COR_PRF_REJIT_INLINING_CALLBACKS`| <span data-ttu-id="33bf2-110">Recibir `GetFunctionParameters` devoluciones de llamada para los métodos que insertan los métodos solicitados para ser ReJITted.</span><span class="sxs-lookup"><span data-stu-id="33bf2-110">Receive `GetFunctionParameters` callbacks for any methods that inline the methods requested to be ReJITted.</span></span> |  

## <a name="requirements"></a><span data-ttu-id="33bf2-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="33bf2-111">Requirements</span></span>  

 <span data-ttu-id="33bf2-112">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="33bf2-112">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>  
  
 <span data-ttu-id="33bf2-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="33bf2-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="33bf2-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33bf2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33bf2-115">**.NET Framework versiones:**[!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33bf2-115">**.NET Framework Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="33bf2-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="33bf2-116">See also</span></span>

- [<span data-ttu-id="33bf2-117">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="33bf2-117">Profiling Enumerations</span></span>](profiling-enumerations.md)
