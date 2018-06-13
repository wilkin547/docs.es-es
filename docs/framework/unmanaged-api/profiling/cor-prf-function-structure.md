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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1bc8d588641163ccf98054fdf1930a72a04c770c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452067"
---
# <a name="corprffunction-structure"></a><span data-ttu-id="aa863-102">COR_PRF_FUNCTION (Estructura)</span><span class="sxs-lookup"><span data-stu-id="aa863-102">COR_PRF_FUNCTION Structure</span></span>
<span data-ttu-id="aa863-103">Proporciona una representación única de una función combinando su identificador con el identificador de la versión que se ha vuelto a compilar.</span><span class="sxs-lookup"><span data-stu-id="aa863-103">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa863-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aa863-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION {    FunctionID functionId;    ReJITID    reJitId;} COR_PRF_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="aa863-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="aa863-105">Members</span></span>  
  
|<span data-ttu-id="aa863-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="aa863-106">Member</span></span>|<span data-ttu-id="aa863-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="aa863-107">Description</span></span>|  
|------------|-----------------|  
|`functionId`|<span data-ttu-id="aa863-108">El identificador de la función.</span><span class="sxs-lookup"><span data-stu-id="aa863-108">The ID of the function.</span></span>|  
|`reJitId`|<span data-ttu-id="aa863-109">El identificador de la función ha vuelto a compilar.</span><span class="sxs-lookup"><span data-stu-id="aa863-109">The ID of the recompiled function.</span></span> <span data-ttu-id="aa863-110">Un valor de 0 (cero) representa la versión original de la función.</span><span class="sxs-lookup"><span data-stu-id="aa863-110">A value of 0 (zero) represents the original version of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa863-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="aa863-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa863-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aa863-112">Requirements</span></span>  
 <span data-ttu-id="aa863-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa863-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa863-114">**Encabezado:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="aa863-114">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="aa863-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa863-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa863-116">**Versiones de .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa863-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa863-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa863-117">See Also</span></span>  
 [<span data-ttu-id="aa863-118">Estructuras para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="aa863-118">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
