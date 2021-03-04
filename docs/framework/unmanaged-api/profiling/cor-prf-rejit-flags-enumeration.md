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
ms.openlocfilehash: aad66285e9b31558a68b8ccdfc71f103d1772946
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102106922"
---
# <a name="cor_prf_rejit_flags-enumeration"></a><span data-ttu-id="ca692-103">COR_PRF_REJIT_FLAGS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="ca692-103">COR_PRF_REJIT_FLAGS Enumeration</span></span>

<span data-ttu-id="ca692-104">Contiene valores que indican cómo debe comportarse la API [ICorProfilerInfo10:: RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ca692-104">Contains values that indicate how the [ICorProfilerInfo10::RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md) API should behave.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca692-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ca692-105">Syntax</span></span>  
  
```cpp  
typedef enum  
{
    COR_PRF_REJIT_BLOCK_INLINING = 0x1,
    COR_PRF_REJIT_INLINING_CALLBACKS    = 0x2
} COR_PRF_REJIT_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="ca692-106">Members</span><span class="sxs-lookup"><span data-stu-id="ca692-106">Members</span></span>  
  
|<span data-ttu-id="ca692-107">Member</span><span class="sxs-lookup"><span data-stu-id="ca692-107">Member</span></span>|<span data-ttu-id="ca692-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="ca692-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_REJIT_BLOCK_INLINING`| <span data-ttu-id="ca692-109">Los métodos de ReJITted se bloquearán para que no se inlineen en otros métodos.</span><span class="sxs-lookup"><span data-stu-id="ca692-109">ReJITted methods will be blocked from being inlined in other methods.</span></span> |  
|`COR_PRF_REJIT_INLINING_CALLBACKS`| <span data-ttu-id="ca692-110">Recibir `GetFunctionParameters` devoluciones de llamada para los métodos que insertan los métodos solicitados para ser ReJITted.</span><span class="sxs-lookup"><span data-stu-id="ca692-110">Receive `GetFunctionParameters` callbacks for any methods that inline the methods requested to be ReJITted.</span></span> |  

## <a name="requirements"></a><span data-ttu-id="ca692-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ca692-111">Requirements</span></span>  

 <span data-ttu-id="ca692-112">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="ca692-112">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>  
  
 <span data-ttu-id="ca692-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ca692-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ca692-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca692-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca692-115">**.NET Framework versiones:**[!INCLUDE[net_core_30](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca692-115">**.NET Framework Versions:** [!INCLUDE[net_core_30](../../../../includes/net-core-30-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ca692-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ca692-116">See also</span></span>

- [<span data-ttu-id="ca692-117">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="ca692-117">Profiling Enumerations</span></span>](profiling-enumerations.md)
