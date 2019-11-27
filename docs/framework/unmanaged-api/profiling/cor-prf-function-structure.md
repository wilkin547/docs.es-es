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
ms.openlocfilehash: 40698a49ac7012c4f67eb88b1ead04c80f3dea77
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428328"
---
# <a name="cor_prf_function-structure"></a><span data-ttu-id="98860-102">COR_PRF_FUNCTION (Estructura)</span><span class="sxs-lookup"><span data-stu-id="98860-102">COR_PRF_FUNCTION Structure</span></span>
<span data-ttu-id="98860-103">Proporciona una representación única de una función combinando su identificador con el identificador de la versión que se ha vuelto a compilar.</span><span class="sxs-lookup"><span data-stu-id="98860-103">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98860-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="98860-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION {    FunctionID functionId;    ReJITID    reJitId;} COR_PRF_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="98860-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="98860-105">Members</span></span>  
  
|<span data-ttu-id="98860-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="98860-106">Member</span></span>|<span data-ttu-id="98860-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="98860-107">Description</span></span>|  
|------------|-----------------|  
|`functionId`|<span data-ttu-id="98860-108">IDENTIFICADOR de la función.</span><span class="sxs-lookup"><span data-stu-id="98860-108">The ID of the function.</span></span>|  
|`reJitId`|<span data-ttu-id="98860-109">IDENTIFICADOR de la función recompilada.</span><span class="sxs-lookup"><span data-stu-id="98860-109">The ID of the recompiled function.</span></span> <span data-ttu-id="98860-110">Un valor de 0 (cero) representa la versión original de la función.</span><span class="sxs-lookup"><span data-stu-id="98860-110">A value of 0 (zero) represents the original version of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98860-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="98860-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98860-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="98860-112">Requirements</span></span>  
 <span data-ttu-id="98860-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98860-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98860-114">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="98860-114">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="98860-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98860-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98860-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98860-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98860-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="98860-117">See also</span></span>

- [<span data-ttu-id="98860-118">Estructuras para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="98860-118">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
