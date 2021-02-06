---
description: 'Más información acerca de: enumeración COR_PRF_JIT_CACHE'
title: COR_PRF_JIT_CACHE (Enumeración)
ms.date: 03/30/2017
api_name:
- COR_PRF_JIT_CACHE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_JIT_CACHE
helpviewer_keywords:
- COR_PRF_JIT_CACHE enumeration [.NET Framework profiling]
ms.assetid: e7b8f6b4-95bc-4ba5-b9eb-f5590a7326a4
topic_type:
- apiref
ms.openlocfilehash: 94b04b42504760be826f78cee0da3066f1936f32
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648758"
---
# <a name="cor_prf_jit_cache-enumeration"></a><span data-ttu-id="754d8-103">COR_PRF_JIT_CACHE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="754d8-103">COR_PRF_JIT_CACHE Enumeration</span></span>

<span data-ttu-id="754d8-104">Indica el resultado de una búsqueda de función en caché.</span><span class="sxs-lookup"><span data-stu-id="754d8-104">Indicates the result of a cached function search.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="754d8-105">`COR_PRF_CACHED_FUNCTION_FOUND` tiene un valor de cero, por lo que `COR_PRF_JIT_CACHE` no se puede usar como suplente booleano.</span><span class="sxs-lookup"><span data-stu-id="754d8-105">`COR_PRF_CACHED_FUNCTION_FOUND` has a value of zero, so `COR_PRF_JIT_CACHE` cannot be used as a Boolean surrogate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="754d8-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="754d8-106">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_CACHED_FUNCTION_FOUND,  
    COR_PRF_CACHED_FUNCTION_NOT_FOUND  
} COR_PRF_JIT_CACHE;  
```  
  
## <a name="members"></a><span data-ttu-id="754d8-107">Members</span><span class="sxs-lookup"><span data-stu-id="754d8-107">Members</span></span>  
  
|<span data-ttu-id="754d8-108">Miembro</span><span class="sxs-lookup"><span data-stu-id="754d8-108">Member</span></span>|<span data-ttu-id="754d8-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="754d8-109">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FUNCTION_FOUND`|<span data-ttu-id="754d8-110">La búsqueda encontró la función.</span><span class="sxs-lookup"><span data-stu-id="754d8-110">The search found the function.</span></span>|  
|`COR_PRF_FUNCTION_NOT_FOUND`|<span data-ttu-id="754d8-111">La búsqueda no encontró la función.</span><span class="sxs-lookup"><span data-stu-id="754d8-111">The search did not find the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="754d8-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="754d8-112">Requirements</span></span>  

 <span data-ttu-id="754d8-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="754d8-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="754d8-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="754d8-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="754d8-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="754d8-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="754d8-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="754d8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="754d8-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="754d8-117">See also</span></span>

- [<span data-ttu-id="754d8-118">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="754d8-118">Profiling Enumerations</span></span>](profiling-enumerations.md)
