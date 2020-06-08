---
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
ms.openlocfilehash: 856e01c7934709a17556aa53851204bf6a917de8
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500941"
---
# <a name="cor_prf_function-structure"></a><span data-ttu-id="39bd6-102">COR_PRF_FUNCTION (Estructura)</span><span class="sxs-lookup"><span data-stu-id="39bd6-102">COR_PRF_FUNCTION Structure</span></span>
<span data-ttu-id="39bd6-103">Proporciona una representación única de una función combinando su identificador con el identificador de la versión que se ha vuelto a compilar.</span><span class="sxs-lookup"><span data-stu-id="39bd6-103">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39bd6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="39bd6-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION {    FunctionID functionId;    ReJITID    reJitId;} COR_PRF_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="39bd6-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="39bd6-105">Members</span></span>  
  
|<span data-ttu-id="39bd6-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="39bd6-106">Member</span></span>|<span data-ttu-id="39bd6-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="39bd6-107">Description</span></span>|  
|------------|-----------------|  
|`functionId`|<span data-ttu-id="39bd6-108">IDENTIFICADOR de la función.</span><span class="sxs-lookup"><span data-stu-id="39bd6-108">The ID of the function.</span></span>|  
|`reJitId`|<span data-ttu-id="39bd6-109">IDENTIFICADOR de la función recompilada.</span><span class="sxs-lookup"><span data-stu-id="39bd6-109">The ID of the recompiled function.</span></span> <span data-ttu-id="39bd6-110">Un valor de 0 (cero) representa la versión original de la función.</span><span class="sxs-lookup"><span data-stu-id="39bd6-110">A value of 0 (zero) represents the original version of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39bd6-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="39bd6-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39bd6-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="39bd6-112">Requirements</span></span>  
 <span data-ttu-id="39bd6-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39bd6-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39bd6-114">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="39bd6-114">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="39bd6-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39bd6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39bd6-116">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39bd6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39bd6-117">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="39bd6-117">See also</span></span>

- [<span data-ttu-id="39bd6-118">Estructuras para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="39bd6-118">Profiling Structures</span></span>](profiling-structures.md)
