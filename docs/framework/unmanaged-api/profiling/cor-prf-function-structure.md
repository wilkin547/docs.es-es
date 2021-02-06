---
description: 'Más información acerca de: estructura de COR_PRF_FUNCTION'
title: COR_PRF_FUNCTION (Estructura)
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION
helpviewer_keywords:
- COR_PRF_FUNCTION structure [.NET Framework profiling]
ms.assetid: 8bb5acf5-cf4b-4ccb-93f1-46db1f3f8bf3
topic_type:
- apiref
ms.openlocfilehash: 494f3cfe6d1e3641645ef0050c06014e67bf4475
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648979"
---
# <a name="cor_prf_function-structure"></a><span data-ttu-id="e7e07-103">COR_PRF_FUNCTION (Estructura)</span><span class="sxs-lookup"><span data-stu-id="e7e07-103">COR_PRF_FUNCTION Structure</span></span>

<span data-ttu-id="e7e07-104">Proporciona una representación única de una función combinando su identificador con el identificador de la versión que se ha vuelto a compilar.</span><span class="sxs-lookup"><span data-stu-id="e7e07-104">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7e07-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e7e07-105">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION {    FunctionID functionId;    ReJITID    reJitId;} COR_PRF_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="e7e07-106">Members</span><span class="sxs-lookup"><span data-stu-id="e7e07-106">Members</span></span>  
  
|<span data-ttu-id="e7e07-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="e7e07-107">Member</span></span>|<span data-ttu-id="e7e07-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7e07-108">Description</span></span>|  
|------------|-----------------|  
|`functionId`|<span data-ttu-id="e7e07-109">IDENTIFICADOR de la función.</span><span class="sxs-lookup"><span data-stu-id="e7e07-109">The ID of the function.</span></span>|  
|`reJitId`|<span data-ttu-id="e7e07-110">IDENTIFICADOR de la función recompilada.</span><span class="sxs-lookup"><span data-stu-id="e7e07-110">The ID of the recompiled function.</span></span> <span data-ttu-id="e7e07-111">Un valor de 0 (cero) representa la versión original de la función.</span><span class="sxs-lookup"><span data-stu-id="e7e07-111">A value of 0 (zero) represents the original version of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7e07-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e7e07-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7e07-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e7e07-113">Requirements</span></span>  

 <span data-ttu-id="e7e07-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7e07-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7e07-115">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="e7e07-115">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="e7e07-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7e07-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7e07-117">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7e07-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7e07-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7e07-118">See also</span></span>

- [<span data-ttu-id="e7e07-119">Estructuras para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="e7e07-119">Profiling Structures</span></span>](profiling-structures.md)
